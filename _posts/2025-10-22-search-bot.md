---
layout: post
title: Interactive Windows Search Bot
subtitle: A fun and improved way of searching network drives on Windows
author: Bradley Turner
categories: Coding
banner:
  # video: https://vjs.zencdn.net/v/oceans.mp4
  # loop: true
  # volume: 0.8
  # start_at: 8.5
  image: /assets/images/topics/banners/searchbot.jpg # renders a screenshot of the bot in the ide with behind it.
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
  top: 1
tags: [Design, Tech, Code]
---
At my day job, we are constantly accessing files on a server. Windows doesn't index server drives so searching for files is painfully slow. It could take up to 10 minutes to find a file, and if a file didn't exist, it would take even longer to say the file does not exist. I wanted to fix this cause it was wasting hours a week of work time.

# Text file

I started by creating a simple batch file that generated a .txt file per server drive. I then dropped these on the servers so people could open them in text edit and ctrl+f to ty and find what they were looking for, they then copy pasted the path into the navbar in explorer. I ran this batch script weekly as it took a few hours, but this was a very manual process and it didn't work for people working on active projects.

If this method would still work for you, the batch script looked like this:

```bat
@echo off
setlocal enabledelayedexpansion

:: Create index folder if it doesn't exist
if not exist "C:\index" (
    mkdir "C:\index"
)

:: Loop through all drives
for %%D in (A B C D E F G H I J K L M N O P Q R S T U V W X Y Z) do (
    if exist "%%D:\" (
        echo Indexing %%D: drive...
        dir "%%D:\" /s /b > "C:\index\%%D.txt"
    ) else (
        echo Failed to index %%D: drive
    )
)

echo Indexing complete.
pause

```

# Godot Engine Search Bot

So, Why did I choose to use Godot? A few reasons. One, I needed software that could be portable for both the IDE and the finished bot. I also wanted to start learning GDScript as it's cross platform and I do intent to use it in virtual reality development at some point. And my manager asked multiple times about having an assistant to look though his files when he needed something, so I thought it would be funny if I made a virtual assistant, and a game engine seems like the best way to do this.

I created a super simple UI, and coded the ability to index and then search that locally stored index. It still saves a txt file locally, and loads it on program launch. It indexed our specific network drives at work and when you click on a link, it opens the file

## Beta 1

Beta 1 stripped out all the companies internal branding and made it so it will try to scan every drive on the computer, both physical and network drives.

## Beta 2

Beta 2 was a lot of optimisation. A lot of people at work wanted the ability to open the file location, which I implemented by letting the user ctrl+click on a link to open the file location with the file selected. I also started using multiple threads so the program didn't lock-up/crash when indexing, and I intend to let the user search while they are running a new index.

![Current UI Layout on windows](/portfolio/assets/images/topics/content/searchbot.jpg)

# Source Code

The full source code and newest release can be found [HERE >>](https://github.com/algebuckina/WindowsDriveSearchBot). It is still very work in progress so please keep that in mind. If you find any bugs or would like to request any features, post it in the GitHub Issue section and I will respond to it.