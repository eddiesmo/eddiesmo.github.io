---

layout: post
title: "Automation project: download, read and summarize bank PDF emails"
comments: false
tags:
  - project

---

## The problem
Every day or two I get a message from the bank:

> **Subject:** Mail Notification from Discount Bank (Reference: 220237434)
>
> Hello,
>
> You have a new message from Discount Bank Mail Service.
>
> To view it, click \[here].
>
> We are pleased to inform you that starting from **November 18, 2024**, you will be able to view your mail notifications by clicking the link, which will direct you to the secure site. These notifications will be displayed there, and entering the site will be done with your bank website login credentials.
>
> Always at your service,
>
> **Discount Bank**

And here’s the process I need to do:
1. Click the link
2. Enter my password (using a password manager - can be autofilled)
3. Download a PDF from a list, to my `Downloads` folder
4. Open the PDF
5. Read the PDF that’s written in small letters and corporate speak
6. Go back and archive the corresponding email (sometimes I have to double check that it’s the same email)

### New flow building the bot:
1. I get an email from the bank
2. The bot logs in to the secure website, downloads the file, reads it, summarizes it with GPT, and replies to the original email thread with a summary and the attached PDF.

All that is left for me to do is quickly scan the reply summary and archive the email.

## How to set this up
I tried orchestrating the task with two services: Zapier and n8n. Each had their weaknesses and neither was perfect.

| Steps                                                                             | Zapier                                                                                       | n8n                                                                                                                                                   |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Email trigger – start the automation for any email that matches a search criteria | Easy                                                                                         | Easy                                                                                                                                                  |
| Extract link URL from the email                                                   | Easy                                                                                         | Easy                                                                                                                                                  |
| Browser automation (open URL, enter password, click)                              | Requires external tool: supports [axiom.ai](http://axiom.ai) (\$50 / month) and HTTP request | Requires external tool: HTTP request                                                                                                                  |
| Extract text from PDF                                                             | Requires external tool: supports [pdf.co](http://pdf.co) (\$10 / month)                      | Easy                                                                                                                                                  |
| Summarize text with GPT                                                           | Easy                                                                                         | Easy                                                                                                                                                  |
| Reply to the same email thread with the summary and file                          | Easy                                                                                         | 👎👎 Can’t reply to the same thread without having the bank in the `To:` field; had to write custom code to construct and send the full email payload |
| Price                                                                             | \$29 / month                                                                                 | \$27 / month                                                                                                                                          |
| Summary                                                                           | Easy to set up a no-code automation; overall cost: \$90 / month                              | Can’t set up a no-code automation; overall cost: \$27 / month                                                                                         |

### Setting up the browser automation
| Option        | Use axiom.ai                                                                          | Spin up your own server and run Puppeteer                                                                                                                                          |
| ------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cost          | \$50 / month                                                                          | Free                                                                                                                                                                               |
| Setup process | 👍👍 Minutes: no code—just click selectors; files download straight into Google Drive | 👎 Hours: generate server and Puppeteer code via GPT; deploy on Render; debug until working                                                                                        |
| Limitations   | Limited “actions” (but sufficient for this use case)                                  | Need to maintain the server; Render’s free tier spins down after inactivity causing \~3-minute cold starts, so you must build retry logic (e.g., wait 5 minutes and retry the job) |


<iframe src="https://eddiesmo.notion.site/ebd/21bf918b21298061994bc8f77009137f" width="100%" height="600" frameborder="0" allowfullscreen />


### Bugs and issues
1. In Zapier I got flooded by hundreds of replies to an incoming email from the bank. The reason? Each time my automation replied, it also triggered the automation again.
   1. **Solution:** add a “flood protection” mechanic—e.g. throw an error if more than 10 activations per day. I would expect this to be implemented within Zapier/n8n, but it’s not, so you need to add a node that does that.
