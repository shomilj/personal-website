---
title: Bend the Curve - a Robinhood-Esque COVID-19 Statistics App
date: 2020-03-23 00:00:00 +00:00
modified: 2020-03-23 00:00:00 +00:00
tags: [projects]
description: An app to track worldwide and local cases of COVID-19. All data from JHU.

---

This project is an iOS App inspired by the Robinhood UI/UX to effectively track COVID-19 cases across the world. All data is sourced from the [JHU CSSE Dataset of Novel Coronavirus Cases](https://github.com/CSSEGISandData/COVID-19).

The app runs on a Firebase Backend, with Firebase Cloud Functions connected to a Google Cloud Scheduler job performing the daily update of the dataset. News articles are sourced from [NewsAPI.org](https://newsapi.org/).

Unfortunately, Apple is rejecting COVID-19 apps from the App Store unless they're published by an authorized source. Please shoot me an email if you'd like an invite code to download this app via TestFlight!

View the [iOS App](https://github.com/shomilj/Bend-the-Curve-iOS) and [Backend](https://github.com/shomilj/Bend-the-Curve-Backend) on GitHub.

![image-20200619145455323](image-20200619145455323.png)

