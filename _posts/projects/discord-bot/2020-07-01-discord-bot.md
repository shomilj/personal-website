---
title: Building MDBot - an intelligent Discord bot for MDB
date: 2020-07-01 12:00:00 +07:00
modified: 2020-07-01 12:00:00 +07:00
tags: [projects]
description: In this article, I describe the process of creating and deploying a Discord Bot.
---

To stay connected during shelter-in-place in the midst of the COVID-19 pandemic, my club (MDB) turned to Discord as a new platform for voice & social interactions. After hearing about Discord's easy-to-use Developer API, I decided to build a Discord Bot to supplement our conversations & add to the social atmosphere. Below, I describe how I set up and deployed the bot, as well as everything I've trained it to do!

View the GitHub Project [here](http://github.com/mdbdev/MDiscordBot).



## Setting Up a Discord Client

To get started, I followed [this tutorial over at Real Python.](https://realpython.com/how-to-make-a-discord-bot-python/) After initial setup of the Discord server (a.k.a. guild), it's pretty simple to create a bot that can respond to "/" commands sent in any thread. 

The Discord Python library follows the asynchronous style described below.

- To initialize a client, we use `client = discord.Client()`. 
- When a message is sent, the `async def on_message(message)` method is triggered. 
  - To customize a response, we can use `message.author` or `message.content` 
  - We can filter messages by looking for prefixes:  `message.content.startswith('/')`
  - We can respond to messages by sending `await message.channel.send(...)`
-  To run the client (and start listening for messages), we use `client.run(TOKEN)`, where TOKEN is the Discord API Token described in the tutorial above.

I deployed the library to a Heroku dyno by simply linking the GitHub project to a new Heroku Project. 



## MDBot Commands

#### /spoof (name)

Uses a [Markov Chain text generator](https://github.com/jsvine/markovify) trained on Facebook Messenger Group Chats from the current and all previous semesters of the club to generate a fake sentence that often has eerily similar language/voice/tone to the person being spoofed. 

Since I wanted to keep this repository public while keeping the actual content of the messages private, I encrypted the training data with Fernet before uploading it to GitHub for Heroku deployment. The private key is stored as an environment variable.

#### /class (number)

Uses the BerkeleyTime API to look up enrollment data for a particular class. Only works on CS/EECS classes at the moment!

#### /job (company)

We have an internal database of what companies people have worked at (and where our Alumni work as well). This command pulls the names & LinkedIn profiles of people who've worked at a particular company. It's super useful during recruiting season! 

#### /overheard (name)

This one's based on an internal "overheard" repository that we keep. It's essentially filled with a bunch of funny/random/out-of-context quotes by individuals of the club. This command pulls from the Airtable base containing these records and sends a randomly selected quote.

#### /idea

A few years ago, a member of our club wrote a script to generate a bunch of Silicon Valley-esque startup ideas based on fixed templates. Check out the list [here](https://github.com/mdbdev/MDiscordBot/blob/master/scripts/ideas.txt). This command randomly selects an idea and returns it.

#### /habit

Returns a randomly-selected habit from the [7 Habits of Highly Effective People](https://en.wikipedia.org/wiki/The_7_Habits_of_Highly_Effective_People). It's an inside joke :)

#### /joke

Returns a random joke from [this API](https://icanhazdadjoke.com/slack).

#### /quote

Returns a random quote from [this API](http://api.quotable.io/random).

#### /sliver

Scrapes & returns the current day's menu from [Sliver](https://www.sliverpizzeria.com).



## The Actual Bot

![image-20200715121458342](/Users/shomil/Documents/GitHub/Website/personal-website/_posts/projects/discord-bot/image-20200715121458342.png)