---
layout: post
title: Visualizing Unix Directory Trees with Gource
---

I use Git and Github to keep all of my Ph.D. research in version control. This allows me to keep track of every change to the files and even pull out specific file versions from years ago (perhaps a presentation given at a certain conference). It also functions as a cloud backup in case something happens to your workstation or laptop. If you're at the beginning of your Ph.D., I strongly, *strongly* recommend using a version control system. If you don't want to pay for a private repository out of pocket, talk with your IT department, perhaps they already pay for Github hosting and can set you up with a private repo (thanks, G!).

Let's say you've been using Git for quite a while now (for me it's been about four years now) and you want to visualize your progress. Well, you're in luck because someone developed the exact software for you! It's called [Gource](https://gource.io/) ([Github link](https://github.com/acaudwell/Gource)). Gource works out of the box for Git, Mercurial, Bazaar, and SVN. Visualizing Git repos is a snap with Gource. But what if you don't use a version control software?

One of my friends saw one of my recent visualizations and was interested in generating a Gource visualization for their work. However, they don't use version control software for their research. Gource has the option of visualizing a custom log that you point it to. It just needs to be formatted a certain way.

Version control software keeps track of nearly everything that you do with your files, but the main things you're interested in for a Gource visualization are the time the file was created/modified, the path to the file, and the filename. If you're on Windows, you can access the time that the file was created, but you're out of luck if you run Unix. Modification time is universal across OSes, though only the last time the file was modified will be the modification time.

It was relatively straightforward to write a Python script which traverses a given directory tree, finds the modification time and path/filename, and writes the custom log format in the correct order. Here's a [link to the script](). This script was written for 2.7, but will run on 2.6.6 (the version on SUPERIOR).

I ran it on my Github directory tree, but the resulting output didn't match the normal Gource visualization due to some weird modification dates of some software in the tree. This code will work best on a directory tree where the oldest files are in the root directory and become newer the further from the root you go. The problem lies with the log starting somewhere that is not the root. Ideally, the log will start with files at the root. That is what the code is designed to do.

Thankfully, it works perfectly at the root directory of my high-performance computing (HPC) storage on SUPERIOR, Michigan Tech's HPC cluster. This is the usecase for which this code was really meant for.

For my friends/colleagues who may be reading this, **you should start a qlogin session before you run the code.** I don't think it is computationally intense, but it's better to be cautious all the same. You don't want to be the person who crashes the login node. To start a qlogin session, simply type "qlogin" without quotes and hit enter. The prompt should turn green, indicating that it is now safe to run things.

Place the Gource_Custom_Log_Creator.py file at the root of your research directory on SUPERIOR (or other HPC cluster). Next, you will need to change a couple lines in the code to match your information. First, you will need to change the root_dir string to match the path of your research directory. Second, you will need to change the username string to match your username. Lastly, save the file and run it using "python Gource_Custom_Log_Creator.py" without quotes. You should see a flurry of text fly past your screen. The code is printing each file it finds and its corresponding modification time. At the very end, if all went well, you should see "your_custom_log.log has been written to (your root directory here)". Go ahead and view it using less, vi/vim, or your favorite text editor. You should see lines with a large number at the beginning followed by your username followed by an M followed by the path and filename. Now you can point Gource to this log file.

Download Gource onto your machine and unzip it somewhere. Download your newly created log file and save it somewhere close to where you put Gource. Then, in a terminal or command prompt window, run "Gource ../pathtologfile/your_custom_log.log" (Unix) or "Gource ..\pathtologfile\your_custom_log.log" (Windows). There are more options that you can add, but that will tell you if it worked. You should see a window pop up with the visualization. If you see a little figure zipping around and zapping clusters of dots into existence, congratulations! It worked!

For reference, here is what my SUPERIOR timeline looks like.

<video width="1024" height=768" controls>
    <source src="https://pisanifamily.info/will/videos/SUPERIOR_Will_Pisani_Timeline.mp4" type="video/mp4"/>
Your browser does not support the video tag.
</video>
