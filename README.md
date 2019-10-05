Notes App Challenge
===================

Features:
-------
```
As a busy politician
I can see all of today's headlines in one place
So I know what the big stories of the day are

As a busy politician
I can click a link to see the original news article
So that I can get an in depth understanding of a very important story

As a busy politician
I can see a summary of a news article
So I can get a few more details about an important story

As a busy politician
I can see a picture to illustrate each news article when I browse headlines
So that I have something nice to look at

As a busy politician
I can read the site comfortably on my phone
Just in case my laptop breaks

As a busy politician
I can see whizzy animations in the app
To make my news reading more fun
```




Technical Approach:
-----



Notes on functionality (once all user stories are implemented):
------

## Domain model


**Access Page and show Notes**
```sequence {theme="hand"}
politician->browser: open app
browser->localhost(server): url route ('./')
localhost(server)->browser: index.html
browser->browser: rendered index.html
politician->browser: selects news item
browser->browser: renders summary
```

## Terminal instructions for downloading and running the app

* git clone git@github.com:mariacuffaro/news-summary-app.git
* npm install
* node node_modules/http-server/bin/http-server
