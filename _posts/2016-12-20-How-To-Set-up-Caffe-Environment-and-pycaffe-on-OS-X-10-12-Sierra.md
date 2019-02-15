
---
layout: post
title: How To: Set up Caffe Environment and pycaffe on OS X 10.12 Sierra
comments: false
Categories: Computer Vision

---

Recently at work, our research team has started working on a deep learning project and for technical reasons we’ve decided to go with the Caffe framework by BVLC. For some of us the installation process went smoothly. For others… not so much. While installing the framework on linux and AWS servers was relatively straightforward, many things broke down when trying to install it on my personal Macbook Pro. Following is a post I put in our internal confluence Research space – may it help others find inner peace.

tl;dr The installation process for Caffe on OS X can be extremely frustrating, especially if things don’t go right. Here’s what worked for me.


Introduction
The official installation instructions are out of date and incomplete. If you are very good with installations on Mac, go ahead and use them and fill in the blanks yourself. If you’re not – this page is for you.

Most of the guides I’ve encountered are for installing Caffe on OS X 10.10, while I was working on 10.12 Sierra. Apparently, in 10.11 there was a big security update that screwed up some of the steps in existing guides.

The installation involves installing various prerequisites and then downgrading some of them to the versions that Caffe works with. Then you configure a `makefile.config`, tinker with some files and run make commands and tests.

Try as I might, I couldn’t get Caffe to work with Anaconda and opencv3. I might take another stab at it now that I’ve managed to finish the process once, but I’ll need a god damned vacation first.

Managing expectations
Set aside at least an entire day for the installation process. If all goes well – you’ll be done in a couple of hours. If it doesn’t – well, just look at the wall of frustration below – you’re in good company.

It took me almost 3 days of tinkering, following ~6 different guides, solving several different errors using google searches, to finally be able to get “import caffe” to run without errors. Admittedly, in this case I’m probably an outlier and the average installation process should be easier.

The working guide to install caffe on OS X 10.12 Sierra
Uninstall anaconda completely if you have it
Uninstall brew python if you have it
Follow the instructions in the only (almost) working guide I found: https://gist.github.com/doctorpangloss/f8463bddce2a91b949639522ea1dcbe4 (also coppied in the appendix below)
In my case, I installed OpenBLAS
For the python installation, I Installed virtualenv and virtualenvwrapper
There is a bug with virtualenvwrapper installation since el capitan.
Error and solution: https://github.com/pypa/pip/issues/3165
Other Errors and Solutions I Encountered
make pytest doesn’t work!! Veclib issue:
“ld: framework not found vecLib”
Solved by reinstalling xcode command line tools
import caffe doesn’t work! Due to a Malloc error. This is a leveldb issue.
Almost solution: https://github.com/BVLC/caffe/issues/4783
Compiling without leveldb broke the basic mnist example from the caffe website, so not the best solution
He suggests installing leveldb 1.9 (not trivial!), which still doesn’t solve it.
True solution: https://github.com/wbolster/plyvel/issues/54
Install a fixed version of leveldb: https://gist.github.com/hellysmile/ffd665fb1bd1bf978bc99cb7f57250c9
Install via brew with url by pressing the “raw” button:
brew install https://gist.githubusercontent.com/hellysmile/ffd665fb1bd1bf978bc99cb7f57250c9/raw/c0a06f1b98388333955f49e30e01dfdde2d82526/leveldb.rb
Wall of Frustration
At some point I started collecting dispirited quotes from the various guides I’ve encountered along the way. Here are some snippets:

“For the past couple of days, I struggled to get Caffe to work on my macbook.” – 
http://hoondy.com/2015/04/03/how-to-install-caffe-on-mac-os-x-10-10-for-dummies-like-me/
“Our goal is to run python -c “import caffe” without crashing. For anyone who doesn’t spend most of their time with build systems, getting to this point can be extremely difficult on OS X.”
https://gist.github.com/kylemcdonald/0698c7749e483cd43a0e
Comment: “DYLD_LIBRARY_PATH is ignored in 10.11 because of system integrity protection, so this guide is as “wrong” as nearly every other guide you’ll find.”
“However, it is not an easy task to get a working Caffe environment for a standard user. Of course, there are plenty of online documentation and some very nice guides but I didn’t find any for a Mac OS X 10.11.4 version working out of the box,…”
http://www.megastormsystems.com/news/how-to-install-caffe-on-mac-os-x-10-11
https://gist.github.com/doctorpangloss/f8463bddce2a91b949639522ea1dcbe4
“#   Do not install python through brew. Only misery lies there
#   We’ll use the versions repository to get the right version of boost and boost-python
#   We’ll also explicitly upgrade libpng because it’s out of date”
“Re: renaming _caffe.dylib, yep, just pretty much ignore what other people say, they basically never follow their own steps on clean machines, so files are found in all sorts of places and they think stuff works when it really does not. Also, I believe this does not use CMAKE, while that PR does.”
Appendix
Resources
Official installation instructions:
http://caffe.berkeleyvision.org/installation.html
Support:
https://groups.google.com/forum/#!forum/caffe-users
http://installing-caffe-the-right-way.wikidot.com/start
http://davidstutz.de/pycaffe-tools-examples-and-resources/
https://haduonght.wordpress.com/2015/02/21/install-caffe-on-mac-os-x-10-10/, Based on:
https://gist.github.com/yusuketomoto/da4ab182c1693fc3995e
http://smrmkt.hatenablog.jp/entry/2015/02/11/195213
https://portal.rc.fas.harvard.edu/apps/modules/Caffe
http://hoondy.com/2015/04/03/how-to-install-caffe-on-mac-os-x-10-10-for-dummies-like-me/
https://gist.github.com/kylemcdonald/0698c7749e483cd43a0e
https://gist.github.com/doctorpangloss/f8463bddce2a91b949639522ea1dcbe4
http://www.megastormsystems.com/news/how-to-install-caffe-on-mac-os-x-10-11
Original Guide
Saved here in case it disappears / changes: Source: https://gist.github.com/doctorpangloss/f8463bddce2a91b949639522ea1dcbe4

