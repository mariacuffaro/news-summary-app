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
```
NewsItem is a single news item - it has a title and a url

Headlines gets the json returned from the Guardian api and creates an array of NewsItems.

HeadlinesView is instantiated with a Headlines object and extracts each NewsItem (title and url) and wraps it in html so that they appear as a list on the screen.

NewsItemSummary is instantiated with a news item and uses an api call (Aylien) to get the summary text for the news NewsItem

SummaryView is instatiated with a NewsItemSummary and wraps the text in html to display on the page

*** Controllers ***

headline-controller creates an instance of the Headlines object and then a HeadlinesView object and displays title and url for each of the headines on the screen.

summary-controller is called by the headline-controller if a url is clicked on the main page.  It creates a NewsItemSummary and SummaryView for the NewsItem that has been selected and renders them to the pages.

item-controller is called by the headline or summary controller if the 'full article' link is selected.  It makes an api call to retrieve the entire article???

```

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
