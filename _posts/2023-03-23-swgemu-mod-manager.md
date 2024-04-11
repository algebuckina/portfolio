---
layout: post
title: SWGEmu Mod Manager
subtitle: My 1st step into releasing open source software
author: Bradley Turner
categories: Coding
banner:
  # video: https://vjs.zencdn.net/v/oceans.mp4
  # loop: true
  # volume: 0.8
  # start_at: 8.5
  image: assets/images/topics/banners/modmanager.jpg # Find another way of highlighting the program, as well as VSStudio for the main image. Maybe the 2 screens like https://devlopr.netlify.app/#/
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: [Design, Code, MTG]
---
I’ve been a community manager and content creator at [Mod the Galaxy](https://modthegalaxy.com/index.php?resources/&creator_id=5766) for many years now, and throughout my time there, I’ve always needed to tell people how to install mods, and a mod manager would fix this. So naturally I chose to write one myself. I hadn’t written software since year 9 in high school, so it took some time to get back into it, but I was able to get a WinForms project started and the UI done in a few afternoons, taking the colours from the in-game UI, and making my own custom buttons based on it too. I started working on button functionality and got stuck on trying to load and change information in the game files so the project sat on the back burner for about a year.

Throughout this year, a SWGEmu staff member started hinting that I should finish work on it to get it to a functional state. This went on for a while till he said the SWGEmu project was nearing its end, and a content creator would be needed on the team once they move to a full play server and someone who made a mod manager would be looked upon favourably for this position ‘wink wink’. So I dove back into the project and, with some research, got the manager functional and released it to the public. And a few months later, I was accepted onto the SWGEmu team as an event and quest coordinator.

![Mod Manager Screenshot](/portfolio/assets/images/topics/content/mod.png)

# What is Star Wars Galaxies

Star Wars Galaxies is a massively multi-player online role playing game introduced by Sony Online Entertainment in the year 2003. It is the game this project focuses to recreate at a specific milestone referred to as Pre-CU, or Pre-Combat Upgrade. The Combat Upgrade was a set of game changes which radically changed the game-play, to the dislike of thousands of players. These changes led to the founding of the project, in an attempt to "recreate" the game as it was during the Pre-CU era. At SWGEmu, Emulator refers to the software the SWGEmu team is building. The Emulator is meant to imitate Sony Online Entertainment's server-side software, which hosted the galaxies of Star Wars Galaxies during the Pre-CU era.

# Features
### Current
* Easily enables, disables and reorganises mods and their order
* Imports mods to a designated 'mod' folder
* Reads and makes changes to the swgemu_live.cfg file
* Makes a standalone mods.cfg file
* Works as a SWGEmu Launcher

### Planned
* Packing loose mods into tre files
* List available mods to download from the MTG website
* Remembering mod settings

# Source Code

Although I want to rewrite the mod manager in .NET Maui, the WinForms version is still up for download with all its source code [HERE >>](https://github.com/algebuckina/mtg-mod-manager)