+++
title = "Languages Elitism and Social Media"
date = "2025-12-28T03:25:11-05:00"
tags = ["devblog","opinion"]
+++

I have a gooper account on TikTok[^1], and I have been in the trenches fighting the good fight—the freedom for people to use whatever language they want to. That is what I am going to talk about. I want to make the language selection less about picking a tribe, and more about what makes it easier for you to learn.

## What, how, and why to pick a language

When I first started to learn programming as a teen in the mid-2010s, I started with the C programming language, because the book was the cheapest. C is actually a really simple language. I think that most of the complexity comes from the libraries like Boost or others that rewrite the std, or other core libraries that make memory handling harder to read[^2]. One of the biggest failures of that language is not knowing what is going to be on the stack and what is on the heap. That is because the stack is managed by the CPU at a microcode level for memory (for the most part), while the heap is the Wild West.

After a while I wasn't able to learn like I wanted to. I was trying to learn CMake/Make, GCC/Clang, VS Code/Vim, and the language. I couldn't add the libraries I wanted to use, and it just wasn't a good match for me.

I moved to Python, because of the free learning on YouTube. That, paired with the ease of adding a library and the inability to shoot yourself in the foot, were also big factors. While I said C wasn't complex, it is when you’re new. I think the first version of Python I used was either 3.1 or 3.2. Yeah, I am that old lol.

My take on picking a language for learning is that you should pick one that you can either read and understand the docs really well, vibe with tutorials on YouTube with, and have the ability to read and understand the code written in that language. Outside of that is knowing the setup of projects—an editor, debugger, and so on are also really important. The most important thing to remember is to not give up, and if that language doesn't match the vibe, change it. I jump from C to Go to Python to C# to others all the time.

There is no starter language, only languages that hide complexity. For example, look at something like Lua. Lua doesn't have OOP or async in the core library. That's one reason the language is so simple, and why it's loved so much. Lua is also hard to setup, but easy to use.

Some languages that follow this:

- Lua

- Python

- JavaScript/TypeScript

- C# (Kinda, it is OOP but easier than Java)

- Kotlin (The way you add packages/libraries isn't noob friendly)

Some niche languages that are kinda like that:

- Crystal (It's like Python, but compiled)

- Odin

I am sure I forgot someone's language, and will be hearing about it somewhere online.

Find the language you vibe with the most, and use it. The goal is to get you to want to come back and write code, and learn new things—not just to build the "most fastest" thing to ever exist.

## Social Media and Elitism

One of the biggest things I dislike about social media is the elitism people have. I have had people tell me C is trash because they didn't add bools until C23, when they were actually added in the C99 standard. People want to act better and bigger than they are, and you can see that if you try to talk in-depth with them on something. I have only had 2 "fights" on social media that I would count as productive. I am saying this to say: don't use Rust or Linux because some TikTok comments are telling you to use them. Use them because you want to. Don't let someone bully you out of something you like because they want to shill something.

I promise the OS you use and the language you use doesn't really matter, until it does[^3].

## The End
Like I have repeated on my gooper account hundreds of times at this point: the issue isn't the language, or OS, or editor—the issue is the learning. The access to good, updated info—from secure coding on the web to storing keys at runtime—is hard to find and understand a lot of the time for a lot of languages. The fact that multithreading is still a taboo topic for some languages is truly sad. I think more time and investment needs to be put into these fields—like secure code and cybersecurity for apps, as well as multithreading, GUI/TUI, and so on.

One of the big issues with YouTube-based tutorials is we start a project, learn a thing or two, and start a new project for a new cycle. Books break this by starting one project and ending with an app that has multiple versions and revisions. Not everyone can buy a $50–$70 book, and they aren't always on the latest version of the language or framework. The same can be said for Udemy and other sites that sell courses.

If you are someone who has read this far and want to figure out how to change this, here is a simple idea. If you want to do YouTube videos, make them fun and simple while building a foundation in programming—not just the language, but programming as a whole. Think of your tutorial as a book, and end each chapter with something the learner can play with or use. That way they understand why and what needs to be added. Assume a little knowledge in programming, and make mistakes that you quickly fix and explain how to. Don't script these mistakes; let them happen like they normally would. This isn't a college; this is on-the-job training where you can't see what the other person is doing or have any idea who they are.

[^1]: A gooper is a person or group that goops; lames would say it's a troll. 

[^2]: I say harder to read because it's not the standard way the language does it, not because the library is harder or easier. 

[^3]: By "does," I mean for things like trying to write iOS apps on Windows, and stuff like that. Niche languages like OCaml work better on Linux/Mac, and C# IMO works better on Windows. Other than that, it doesn't matter.