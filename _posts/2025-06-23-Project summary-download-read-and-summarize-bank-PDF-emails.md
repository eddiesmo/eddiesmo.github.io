---
layout: post
title: "Project summary: download, read and summarize bank PDF emails"
comments: false
tags: 
  - project

---

### The problem

Every day or two I get a message from the bank:

> **Subject:** Mail Notification from Discount Bank (Reference: 220237434)
> 
> 
> Hello,
> 
> You have a new message from Discount Bank Mail Service.
> 
> To view it, click [here].
> 
> We are pleased to inform you that starting from **November 18, 2024**, you will be able to view your mail notifications by clicking the link, which will direct you to the secure site. These notifications will be displayed there, and entering the site will be done with your bank website login credentials.
> 
> As before, a notification summary will also be sent to you via SMS or as a voice message to your updated phone number in our system.
> 
> Always at your service,
> 
> **Discount Bank**
> 

And here’s the process I need to do:

1. Click the link
2. Enter my password (using a password manager)
    1. Can be autofilled
3. Download a PDF from a list, to my `Downloads` folder
4. Open the PDF
5. Read the PDF that’s written in small letters and corporate speak
6. Go back and archive the corresponding email (sometimes I have to double check that it’s the same email)

### New result after building the bot:

1. I get an email
2. The bot logs in to the secure website, downloads the file, reads it, summarizes it with GPT, and replies to the original email thread with a summary and the attached PDF.

All that is left for me to do is quickly scan the reply summary and archive the email.

# How to set this up

I tried orchestrating the task with two services: Zapier and n8n. Each had their weaknesses and neither was perfect.

| Steps | Zapier | n8n |
| --- | --- | --- |
| Email trigger - start the automation for any email that matches a search criteria | Easy | Easy |
| Extract link URL from the email | Easy | Easy |
| Browser automation: Open the URL, enter the password, click the website | Requires external tool.
- Supports [axiom.ai](http://axiom.ai) 
($50 monthly)
- Supports http request | Requires external tool.
~~- Supports axiom.ai~~
- Supports http request |
| Extract the text from PDF | Requires external tool.
- supports [pdf.co](http://pdf.co) 
($10 monthly) | Easy |
| Summarize the text with GPT | Easy | Easy |
| Reply to the same email thread with the summary and file | Easy | 👎👎
- Can’t reply to the same thread without having the bank in the `To:`  field
- Had to work with GPT (hours) to write code that creates the full email payload and sends the email via an http request |
| Price | $29 per month | $27 per month |
| Summary | Easy to set up a no-code automation. 
Overall cost: $90 per month. | Can’t set up a no-code automation
Overall cost: $27 per month |

## Setting up the browser automation

|  | Use axiom.ai | Spin up your own server and run Puppetter |
| --- | --- | --- |
| Cost | $50 per month | Free |
| Set up process | 👍👍 [minutes]
No code, just click the selectors that you want auto-clicked on the website and axiom handles the rest. The file can be download straight into your Google Drive. | 👎 [hours]
1. Have GPT write the code for both the server and Puppeteer
2. Use Render to spin up a free server
3. Debug until works (depends on your level) |
| Limitations | Has limited “actions” it can do (but was enough for this use case) | - Need to maintain the server yourself
- On the free tier, Render spins down the server, so each activation requires a ~3 minute “cold start”. So if the automation doesn’t work on the first try, I set it up to retry after 5 minutes before giving up. |

## Bugs and issues

1. In Zapier I got flooded by hundreds of reply to an incoming email from the bank. The reason? Each time my automation replied, it also triggered the automation again.
    1. Solution: add a “flood protection” mechanic - e.g. throw an error if more than 10 activations per day. 
        1. I would expect this to be implemented within Zapier/n8n, but it’s not, so need to add a node that does that.

