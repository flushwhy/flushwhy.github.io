+++
title = "How I Think About Design"
date = "2025-08-01T09:12:43-04:00"

#
# description is optional
#
# description = "As a solo dev, I struggled with game design and code architecture for my first Android game, BlockRush. Learn how I moved from a single-file prototype to a clean, maintainable manager-based system and my biggest lessons learned."

tags = []
+++

Whether it's a game, an API, or a website, I always find myself wrestling with the same question: What's the best way to break down a prototype into a clean, maintainable structure of classes and files? Even after years of doing this, I still question the 'how' and 'if' of it all. This constant struggle became incredibly real during my most recent project: an Android game I built on Unity.

## First Some Backstory

I've always wanted to build an Android game, not for money—although my game does have ads—but to see if I had the passion for it. Turns out, I do, but the skills? Not so much, lol. The game I'm talking about is **BlockRush**. For the past six months, I've been working on it on and off, figuring out everything from in-game currency and cloud backups to saving data and implementing in-app purchases (IAPs).

So who am I? I'm Ryan, or rather, Flushwhy, a software engineer who mainly works with C/C++ and Python—often on broken or outdated build systems (partly joking). My passion isn't like the 100th person saying they want to start a business to get rich. I just wanted to create a game because I think they are cool. This is my first-ever solo game project, and before this, I had only done SFX sounds for game jams and other similar projects.

## Getting To The First Release

Believe it or not, I built the first playable version of **BlockRush** in about 48 hours. It was a single-file prototype, just the core game with no managers, no start menu—nothing fancy. The next few days were a blur as I worked to get it on the Play Store, adding a start menu and a ton of backend systems to make it more maintainable. I added Play Services, messed it up, and had to re-add them. I also tried to integrate LevelPlay (around the time Unity acquired IronSource), which was an absolute nightmare to add. My `AdsManager` was a mess, but I finally got it working a few months ago. I also added Unity's IAP SDK for in-game purchases and I'm currently working on a customization system where you can buy or earn items to personalize the game.

If you're on the fence about building an app or game for Google or iOS, I promise you, just do it. It's a nightmare to understand all the systems, what you need to pass review, and what can be worked on later, but it is so worth it. The first time is the hardest; the next time, it will be easier and faster.

The backend of that first release was a complete mess. I built the systems out twice and reverted back because I didn't like how I had done it. I would get Ads working, and GPGS (Google Play Games Services) would break. Then I would fix GPGS, and Ads would break. It was a constant cycle of chaos. This is when I started thinking deeply about how I wanted to build my managers and what should be shared state versus local state. I'll go into what that means to me later on. 

## Rework And Stuff. 

I spent a lot of time thinking about game state, ad state, UI state, and all the other states. My goal was to manage each one in a single, dedicated location, ideally within its own file. This led to a huge rework for version 0.11, where I moved everything into dedicated manager files. The only things shared between managers were simple booleans and values, with functions acting as the primary drivers of logic.

One of the hardest things I had to reason with was where to put logic for events like **Player Death** or **Player Initialization**. When a player dies, for example, you're not just updating one state; you're often updating the UI, the game state, and potentially rolling an ad. I called this a **'shared state'** because the player's death depends on multiple managers. I was okay with the Player Death function calling into other parts of the code, like the `AdsManager`, `UIManager`, and `GameStateManager`.

However, I did move the actual 'death' call from the player's script to the `GameManager`. My reasoning was that the player script should only handle its own core logic, like **HP**, **movement**, and **inventory**. The `GameManager`, on the other hand, should be responsible for orchestrating the overall game flow, like loading the player's inventory, preparing a new level, and ensuring all the other managers are in the correct order.

Ultimately, the managers should do exactly what their names suggest: manage their respective systems. For instance, if I need something related to an ad, I should go to the `AdsManager`, and if I'm looking for a UI component, the `UIManager` is the logical place to start.

## Conclusion

**Reinventing the wheel** isn't always a bad thing. Sometimes, you need to rebuild your code to create a better foundation. But the cycle of adding one thing and having to rework everything else is frustrating and inefficient. I began to notice that I had too much logic crammed into a single manager file. Once I started to respect the purpose of each manager and give it a clear, single responsibility, I found myself wanting to rewrite the entire codebase less and less. This shift in thinking was the key to finally making real progress.