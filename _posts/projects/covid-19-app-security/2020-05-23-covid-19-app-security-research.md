---
title: A brief security analysis of COVID-19 informational & contact tracing apps
date: 2020-05-23 00:00:00 +00:00
modified: 2020-05-23 00:00:00 +00:00
tags: [projects]
description: See title.

---

> Note: this article may contain vulnerabilities that have been patched since the time the article was written.

Over the past few weeks, a handful of companies, states, and counties have released COVID-19 informational or contact-tracing apps. These apps aren't built on the official Contact Tracing API specification published by Apple and Google – that functionality hasn't officially been rolled out by those two companies yet. Rather, these apps either provide some alternative approach to contact tracing – or simply provide information regarding the virus.

In this article, I highlight a handful of privacy and/or security-related flaws I discovered while conducting research on the apps that I could find on the iOS App Store related to COVID-19.   

---

# Application #1: HEALTHYNKED COVID-19 Tracker

**Developer & Ratings**: This app was developed by HealthLynked Corp. It has 35,000 ratings, with an average rating of 4.6 stars. Download on the [iOS App Store](https://apps.apple.com/us/app/healthlynked-covid-19-tracker/id1500575377).

**App Summary:** This app provides the ability for users to self-report symptoms of COVID-19 - data which is then shown to users in an aggregated map-like format.

### Vulnerability: Unauthenticated Writes to Database

Upon inspection of the API call that enables this functionality, it appears that commenting out the session cookies results from the API call results in a successful database write, with a status code 200 and success message. 

![img](https://lh3.googleusercontent.com/KTb8mAH9tdFNYudRe07QvlawnL4rVvVS__ieLuxjBGR1QZ3d-t4B4jKcKOOKAUn1TMlp71WOrepYSDe1D8RIOiiNh2mc0YBuUpxCqKyWCR-ep1t1bVe-p0P_iEPJgze4Gl1RJ8Qg)

A hacker could exploit this feature by randomly generating reports associated with particular areas, which would then allow massive misinformation campaigns surrounding false positives in particular zip codes. These results would propagate directly to the map view shown to users.

### Vulnerability: HTTP Plaintext Authentication

Upon logging in, the user’s entered email and password combination are sent over an unencrypted HTTP POST request to /api/sessions/login in plaintext. Note the unchecked TLS column visible in BurpSuite. 

![img](https://lh4.googleusercontent.com/8SMfK23YrO5Wym_BzTVaRJIWzTTU4YDWSxF46oDh48VzCT-Chyu5JrQyGcscVZ-BYMLNwxcO1sEE3JL_cE_AdJRjG7uuN4O_4LlJR42OWN-3dQW7ZoYMZfmPW9V0sHY6FILyTry8)

An on-path attacker could observe and capture the email and password sent across the unencrypted channel. 

# Application #2: Care19 (North Dakota)

**Developer & Ratings**: This app was developed by the State of North Dakota. It has 256 ratings, with an average rating of 3.0 stars. This is a review of app version 3.1. Download on the [iOS App Store.](https://apps.apple.com/us/app/care19/id1506077328)

**App Summary:** This is the official contact tracing app of North Dakota. This app recently came under fire for sharing location data - latitude and longitude coordinates - with [third party FourSquare](https://www.mediapost.com/publications/article/351775/north-dakota-contact-tracing-app-found-to-share-lo.html) without user consent, which was a direct violation of its Privacy Policy. 

### Vulnerability: Sharing Information with Third Party

In version 3.1, the developers claim to have “increase[d] user privacy by removing a set of support diagnostics.” However, the application appears to still be sharing identifiable analytics information with FourSquare, including arbitrary values like phone battery strength, without user consent.

![img](https://lh4.googleusercontent.com/vTBm5lEthQFOz5RpUtW-c2kN6BF58UsUXi1cUcme4Df2UER7o1y7DfKg5YxV8AH6lXzzUoCmgeF9VPGZf8zHgMyCrFqjJ4-81YnxVi433lSm7w51KQsKQCe7UXu9KOgNwwGnTXZ5)

# Application #3: SoCo COVID-19 Check (Sonoma County)

**Developer & Ratings**: This app was developed by Sonoma County in a partnership with IBM. It has 4 ratings, with an average rating of 3.5 stars. Download on the [iOS App Store.](https://apps.apple.com/us/app/soco-covid-19-check/id1511037042)

**App Description:** This application contains a survey created by IBM and the Sonoma County Health Department to collect crowdsourced self-reporting information from users. 

### Vulnerability: Spoofed Survey Responses => Falsifying Data

This application allows self-reporting of user information via a survey. The survey responses are pushed to a server database via a POST request. The request includes a user field, which contains a UUID referring to the particular user. This UUID remains constant throughout subsequent survey responses sent from the same device.

![img](https://lh3.googleusercontent.com/mAW7wXS4gjgDuxj803M2_wIziCdyn8MBsNOM_AKxGfZmAn_Uzt_lJibjR5ZPunDlpmQcmSlvLE1ejoPjyMW3BfCw7MqCwP6oavKkBy8CbQM9WuZav1mtl1Tio4ywXbRjY2FziBag)

With no user validation (see the “user” key-value pair in the data payload replaced with an arbitrary “SOME_USER_HERE” value), an attacker could arbitrarily generate user ID’s – perhaps ID’s matching the syntax of the client – and flood the database with fake survey results. The app would likely be unable to differentiate between legitimate survey results and spoofed ones, as the application appears to generate the user ID randomly on the client on first launch.

# Application #4: Healthy Together - COVID-19 (Utah)

**Developer & Ratings**: This app was developed by Twenty Holdings, Inc in a partnership with the State of Utah. It has 3.1K ratings, with an average rating of 4.7 stars.  Download on the [iOS App Store](https://apps.apple.com/us/app/healthy-together-covid-19/id1507570835).

**App Description:** Utah’s official contact-tracing application.

### Vulnerability: Spoofed Location Responses => Falsifying Data

This application has an opt-in location tracking feature, which allows users to share their location with researchers and public health authorities for data analysis purposes. In an effort to make this as private and anonymous as possible, the app doesn’t tie locations to user survey responses (note the POST request below: it has no identifying information in the header/data excluding the location points themselves). 

![img](https://lh4.googleusercontent.com/n0hKylnI9oK0UAsrdXzSKKfO7VrN-3a-8wDRcl-GjKwkKTayX8jX6SbjwrBXRH8dTLV5dbap5L9V1vxhNxdkkLRkA4v-7SMw5HaZ1emdg0X8R78tgp1y_M4aoC6EfHohGizmv036)

This opens this app up to a particular vulnerability; hackers could potentially reproduce this POST request and send millions of fake user locations to the server, which would then deem any research or data collection purposes futile.

# Application #5: COVID-19 (Vietnam)

**Developer & Ratings**: This app was developed by Electronic Health Administration, Ministry of Health, Vietnam. It has 34 ratings, with an average rating of 3.4 stars.  Download on the [iOS App Store](https://apps.apple.com/us/app/covid-19/id1501810040).

**App Description:** this is an informational app created by the Government of Vietnam.

### Vulnerability: Facebook Backend => User Identification

This app is using Facebook as a backend and Google Analytics as well. The Facebook backend draws immediate concern; users who are using the Facebook mobile application may be traceable via a device fingerprint.

### Vulnerability: Hard-Coded Authentication

This isn’t immediately a security violation, but this app appears to be using some form of authentication with a hard-coded client-side email and password (I didn’t enter these myself; the app automatically sent them along). As hard-coded authentication keys, there's a small chance that these could be used to unlock aspects of the database that shouldn't be accessible to users of the app. 

![img](https://lh5.googleusercontent.com/POhCHaa6O99nOhPTH84i9xspK9MC6vhJ72zHPu34miFXL06HB7NKlRr3ir_IltNcW4v3nhOxF_7tkKi0hz0vzZ7k7GoLllyupCnQ0s71zoOG0LfLAlKRbbJ3Ph46VdGE3pNGD2bA)

# Application #6: Coronavírus - SUS

**Developer & Ratings**: This app was developed by the Government of Brazil. It has 99 ratings, with an average rating of 3.6 stars.  This is a review of version 2.0.8. Download on the [iOS App Store](https://apps.apple.com/us/app/coronav%C3%ADrus-sus/id1408008382).

**App Description:** This is the official COVID-19 informational app for the country of Brazil.

### Vulnerability: Sending Location Data over Insecure HTTP Channel

 This application is using a weak HTTP connection instead of an encrypted HTTPS connection to send private information via POST requests, like latitude and longitude coordinates tied to particular user ID’s. Note the unchecked TLS column in BurpSuite.

![img](https://lh5.googleusercontent.com/fJ1CyKgI43BNzpUo6e0AwxOTa9htFS2zyh14T-yXV7bAj7yneW1v0G9XeIEY-TD33HW1Fcez3eDY6zFaFSCnGVhVbrhzoGeyvOLQiUaRkeu8f0Hx4AmxHOPHaIm-b1IDzjE1T4gx)

Due to the lack of encryption, on-path attacker could observe and silently collect precise user locations of millions of users. 

# Application #7: CONTACT Tracing (Daly City)

**Developer & Ratings**: This app was developed by the Piusworks LLC for Daly City. It has 17 ratings, with an average rating of 3.8 stars.  This is a review of version 1.4.0. Download on the [iOS App Store](https://apps.apple.com/us/app/contact-tracing/id1504531104).

**App Description:** The official contact-tracing app of Daly City, CA built on a custom framework.

### Vulnerability: Significant Breach of User Privacy in Logging Framework

This application has a significant breach of user privacy in its logging framework. It appears that when the app encounters an error during the login process, it sends a POST request to endpoint /app/api_email.php with the username and MD5 hashed (but not salted) password in the payload. It appears to be sending an email accessible by the support team and/or developers containing an unsalted hash of the user-entered password, which could be identified via a brute-force dictionary attack.

![img](https://lh4.googleusercontent.com/eIxAgTlnvxdl5cLtmy2rBEuoi13qBUcQPWzJx55bTIO2lwVykwogubEk1AefLoBavDbIr3vcsX7h58AK1VeRjApaABF-9LqIxGlaWW27l_wAzbLWgWe0RyjQaau2yLmFX7zX24Ur)

> This article may be updated periodically as new COVID-19 apps are released on the iOS App Store.