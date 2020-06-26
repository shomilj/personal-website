---
title: A sentiment-based political debate scoreboard
date: 2019-06-27 00:00:00 +00:00
modified: 2019-06-27 00:00:00 +00:00
tags: [projects]
description: See title.  
---

The Democratic Party presidential debates just kicked off. With so many candidates (enough for two nights of back-to-back debates), I wanted to build something to gauge widespread political perception in realtime. To do this, I decided applied VADER Sentiment Analysis to a live feed of tweets from the Twitter API. The results were fascinating.

I fed an average of the VADER compound polarity scores of all tweets associated with solely one candidate directly into the scoreboard. The compound score outputs a continuous value ranging from +1 (most positive) to -1 (most negative).

Check out this segment where Kamala Harris attacks Joe Biden on race and segregation. Note how Kamala's score climbs significantly, and Joe's score drops.

<video muted controls width="40%" style="display:block; margin:0 auto; border-style: dotted; border-width: 1px; border-color: #ebeff0">
    <source src="khjb.mov" type="video/mp4">
</video>

Or this segment, where Pete Buttigieg's score rise as he talks about racial profiling and police brutality.

<video muted controls width="40%" style="display:block; margin:0 auto; border-style: dotted; border-width: 1px; border-color: #ebeff0">
    <source src="pb.mov" type="video/mp4">
</video>

It's important to note that other factors could be at play here – in particular, bots that may be included in the data feed. Moreover, this doesn't take into account retweets and likes due to the real-time nature of the feed – a future version of this scoreboard would likely incorporate those as well.

Regardless, it's interesting to see how public perception changes in realtime on such a large scale!

Check out the code to this project [here](https://github.com/shomilj/live-twitter-sentiment-dashboard). To actually run the scoreboard, you'll have to apply for a [Twitter API Key](https://developer.twitter.com/en/docs).