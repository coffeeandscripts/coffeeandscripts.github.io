---
layout: post
title:  "My Custom Start Page"
date:   2018-04-17
excerpt: "Breaking down everything to the basics."
image: "/images/posts/170418/startpage.gif"
---

A start page is simple. It's the first thing you see when you open your browser, and the first thing when you open a new tab. For me, it must be simple, easy to use, aesthetic and informative. This isn't easy to achieve.

There are a few start pages out there already. The most popular is the Chrome extension called Momentum. Here is what they promote.

> New Tab page that gives you a moment of calm and inspires you to be more productive. Get inspired with a daily photo and quote, set a daily focus, and track your to-dos. Eliminate distractions and beat procrastination with a reminder of your focus for the day on every new tab. Join over 3 million users and get inspired to create the life you want to live.

I don't want any of that crap. Motivation for me is work. I achieve goals through progress and control. I thus need a start page that achieves this.

My first step was to break everything down to basic tenants of life which I had once seen in an ancient lifestyle magazine:

### Work
THe idea of working is critical to my lifestyle. I have so much going on simultaneously that I need to find ways to organise myself. This includes calendars, emails, work related tools like Jira and Slack, among other things.

### Play
Amongst the work, it is imperative that you find time to play. This involves things that don't promote or support your work, but rather give you relaxation. For me in real life, this is my music and writing (as well as this blog). If you don't find time for this, you'll go mad.

### Sleep
I would be the first to admit that I don't get enough of this, but it is essential. For this category, I wanted to add the more boring but essential stuff in my life, such as various news websites and banking links. I hate getting involved with them, but they are a necessary evil to become a more well-rounded person.

## Creation
I had a basic idea of what I wanted. Simplicity was key, and it was apparent that I wanted to see my background as much as possible as well. I have that habit with my computer desktops as well (not so much my read desk on which I work).

Typically I like to structure my static websites with the js and css files separated, but since this was a tiny job, I decided against that extra work. Saved me 4 seconds. Wasted it writing that last sentence. I needed a CSS file and JS file accompanying an index.html. This is all easy to do. I'm not a big fan of using media tags in CSS, so I decided to use view height and width to do most of my work. This allows for font sizes and margins to be adjusted dynamically. Below is an example of how I did that:

```
#wrapper {
    width: 100vw;
    height: 100vh;
    overflow: none;
}
#content {
    width: 100%;
    height: 100%;
    background-color: white;
    background-image: url("background.jpg");
    background-repeat: no-repeat;
    background-size: cover;
}
...
.tabContent li {
    font-size: 1.4vw;
    list-style-type: none;
    margin: 0;
    padding: 0;
    padding-top: 5px;
    padding-bottom: 5px;
    margin-bottom: 0;
    margin-left: 0;
    padding-left: 1.4vw;
    transition: background-color 0.5s;
} 
```

Note here how the font-size and padding-left adjust based on the size of the wrapper's width.

Furthermore, much to the chagrin of my superiors while at work, I like to keep everything local, including images and fonts. So I got my (former) terminal font and added the ttf to the root directory. Importing it is a breeze and you can extend this function to include bold fonts as well.

```
@font-face {
    font-family: "Gohu";
    src: url("gohufont-11.ttf");
}
body {
    font-family: "Gohu";
    margin: 0px;
}
```

Having done the main layout, and most of the CSS, the last main job was the javascript. Now jquery is a godsend here, even if everyone riles on about it. Simple jobs it works well for. Anything too intense I will shit the bed. Now my approach to adding the time was very elementary school. Pretty sure there are some 4 year olds who can implement this better than I can. But please enjoy the bin fire that I created below:

```
var showTime = function() {
    setInterval(function() {
        var months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
        var days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
        var d = new Date();
        var day = d.getDate();
        if (day == 1) {
            day = day + "st";
        } else if (day == 2) {
            day = day + "nd";
        } else if (day == 3) {
            day = day + "rd";
        } else {
            day = day + "th";
        }
        var date = days[d.getDay()] + ", " + day + " of " + months[d.getMonth()] + " " + d.getFullYear();
        var seconds = d.getSeconds();
        if (seconds < 10) {
            seconds = "0" + seconds;
        }
        var minutes = d.getMinutes();
        if (minutes < 10) {
            minutes = "0" + minutes;
        }
        var hours = d.getHours();
        if (hours < 10) {
            hours = "0" + hours;
        }
        var time = hours + ":" + minutes + ":" + seconds;
        $('#mainTitleContentDate').html(date);
        $('#mainTitleContentTime').html(time);
    }, 500);
}
$(document).ready(showTime);
```

**It works so shut up.**

One thing to note is that with javascript functions, I prefer to create the function and call it when document is ready in a separate area. This allows for a more modular approach to functions where I can integrate them when necessary.

The last point was to deploy. The way I did this for chrome initially was to add an extension called New Tab Redirect, which worked great, albeit just a tad slow. When I moved to Safari, I could throw this away and it felt great. Just setting one variable was enough for Safari. Unfortunately in my Linux setup, I use Chromium and had to install the extension again. I haven't done anything for qutebrowser since this start page defeats the purpose of a mouseless browser anyway.

If you also want to work with this start page, you can clone or fork it at my Github right [here](https://github.com/coffeeandscripts/startPage).

*Remember to follow me on social media:<br/>
[**Twitter:** coffeenscripts](https://twitter.com/coffeenscripts)<br/>
[**Youtube:** coffeeandscripts](https://www.youtube.com/channel/UCdM4qTlyqK74fjghIc-Syew)<br/>
[**Steam:** coffeeandscripts](https://steamcommunity.com/id/coffeeandscripts/)<br/>
[**Github:** coffeeandscripts](https://github.com/coffeeandscripts)*