+++
title = "The Direction I Am Going With Fe"
date = "2025-08-22T18:53:00-04:00"

description = "This is my plans and ideas I am doing for my project fe. For the rest of the year hopefully."

tags = ["fe", "devlog"]
+++

If you live under a rock, or somehow found this without knowing my project [fe](https://github.com/flushwhy/fe) first. Fe is a cli tool I am making for gamedev that allows you do things like create packed textures, init new projects (for things like raylib, SFML, and so on), and transcode audio files from something like _mp4_ to _ogg_. 

I started the project to learn about CLI tools, and to help aid in exporting projects to platfroms like _Itch io_. Fe stands for Flush's Exporter after all. I want to talk about where I am going with it, and my idea behind my madess.  

---

## Ideas

---

### The Init Command

One of the main things I want to work on is the `init` command. The idea is making it easier to init game projects for frameworks like raylib, SFML, and so on. I love creating new projects, but I often jump around with languages, and trying to find templates for raylib binds is like dry eye, a pain in the a-.

I thought alot about how to do this, and I wanted to make sure I didn't have to push updates to be able to go from raylib 5 to 5.5 or something. So I created a repo that will hold all the project template files, and the top level will be the template the command finds and returns what is created and what is not. In the long term I was going to add the ability to add more template repos in the future form others who may have a different way of setting up their projects. 

In the [submod](https://github.com/flushwhy/fe-templates) project repo. The idea is to have folders like `cpp-raylib5-cmake`. That will hold the _cpp Raylib-5 Cmake_ template. This is how _reactapp init_ command basically works. I like the idea alot, and to me it a way to keep filesize down within the app. File size is important because I want to make sure build minutes aren't wasted on a bunch of bytes that your not going to use. You won't be initializing a project in a GitHub action, so including all of these templates would be a waste of disk space, time, and money. I was thinking about adding the opition for caching templates for people without stable access to the internet. This is important for people in areas like Africa, and lesser developed areas of the world(Including places in the US). This would allow them to precache the temples so that if the connection fails they wouldn't a half compete project or wrost. This would be something I would have to learn. Since I think it would be different on Linux, MacOS, and Windows. Maybe I would store them in the same directory as the tool itself and check that directory before pulling from the list. 

Right now the Submod is just a repo with a license, and a empty readme. That will change in the future ofc. I am probably going to start with `c` and `cpp` project template, then move on from that. 

---

### Go Tests 

I have fought with the idea of just removing them from the project, since most of my time is being spent on writing test that catch errors, and check for things like incorrect commands formatting and so on. This is 100% a _skill issue_ has the kids would say. I have never fully learned testing or testing frameworks. So I am having to now. Gemini has been a big help in writing, and helping me update my go tests, but it does fall short(it removes the test and adds a print statement sometimes).

For now go tests are safe and are tested during every push, merge, and PR.

---

### Updater

I do plan on adding something that checks on run for newer versions of the CLI tool, and auto downloads, and installs them for you.

That will probably be ramdomly added in something like 0.5 or 0.6.

---

### Adding Docker and github actions imgs

I have been in the works of adding these, has well has to linux package managers, Homebrew, and winget/choco. I just want to make sure it fits into the Gitactions and autobuilds.


---

### The TUI And What It Will Do

 The TUI or Terminal User Interface is going to add to the setup of the config, and aid in more help infomantion formatting among other things. I think this choice will aid in tool being able to be used by a larger userbase, and add a ton of vaule. I have Dyslexia, and if something is poorly formated it makes it almost imposible to read, or understand. While I can't control the environment it's displayed in. I can control the my program reacts to that environment. Bubbles Tea from Charm almost the standard TUI library in the go eco system. It uses the ELM model, and I really enjoy that fact!

 It will have things like the displaying the fe.yaml file in the project, more interactive commands, and more. 

---
---

## What's The Direction I Am Going with?

Right now I am working on getting a working a TUI up and running with bubbles Tea, and other charm parts, and working on getting templates in the submods on my freetime. Other than that I am not really going doing anything more of the project. If you have something added just email me, start an issue in the repo, or reach out to me on discord.

I will probably add the docker, github actions imgs along with the updater and package managers all in one go. Since I want them to all be on the same version and update at the sametime.

So yea thanks for reading my small little update, and hope you enjoy my CLI tool or other projects!

---