---
layout: post
title:  "Safari vs Chrome: Why I stay native"
date:   2018-04-14
excerpt: "Safari feels like home, Chrome is a noisy guest."
image: "/images/posts/140418/splash1.png"
---

## I Choose Safari

I am a Mac user and live quite intensely in the Apple ecosystem. I know in some parts of the open source community this is akin to a shooting offence. As someone why uses an Apple Watch (mainly for exercise and calls/text), as well as an iPhone with ludicrous amounts of music on it, being able to manage everything seamlessly through the Mac ecosystem is quite beneficial. In the same manner, I like things to be seamless. That's exactly how I've set up my main Linux system as well.

With the Mac, Safari ships natively. As a native product, it does fit completely seamlessly into the entire experience. All of the GUI elements look normal and work well, which is one of the key tenants of all Apple software. Even when developing for iOS, one of our goals was to make the app seem to fit into the iOS ecosystem and make it look like a native app. This increases trust in the product by the user, raising engagement and returns. We did the same for the Android version of the app. While this was extra work, it certainly paid off.

<span class="image right"><img src="{{ "/images/140418/urukhai.jpg" | absolute_url }}" alt="" /></span> 

Now back to the lecture at hand (quoting Snoop Dogg). Google are a monolithic enterprise, with their tendrils reaching into every pocket of the software world. Chrome is one of their babies, trained purely to raid and burn all RAM that stands in their way. A bit like Uruk-hai in Lord of the Rings. That would make my RAM clones of Boromir. But they are yet to betray me to date.

The reason for this RAM hungry design I believe is the approach to development. The age old idea of pure and utter efficiency is thrown out of the window, replaced with the idea of doing as much behind the scenes as possible. When I open Chrome, I often have a feeling that so much is going on under the hood, that it struggles to even load my start page. The time taken to load my custom made start page in Chrome against Safari is nearly twice as long, and involving quite a bit of screen tearing as it loads the image. There is no problem with Safari which loads it all instantaneously, even after the cache has been cleared.

Now I can start opening new tabs. In Chrome this is when my fan goes into absolute overdrive (I use a 2013 Mac Air). I check my activity monitor, and here we have many instances of Google Chrome Helper. I wondered for a long time what this demon was, only to learn that it is basically just another instance of Google Chrome loaded into RAM (nearly 300MB sometimes). Open scores of tabs, as some of my friends do, against my suggestions, and you'll start getting Chrome and other programs be pushed into swap memory. This is where all good things (efficiency) goes to die. Safari doesn't do this, loading a large amount of data in one fell swoop, and then opening up smalling instances of itself with each tab. The benefit to what Chrome does is that in the event of a crash, the process of the tab can be stopped separately, without any damage to the other tabs. This is a very Unix-like approach to development which I highly respect, but the burden and load that Chrome takes on the system is too much to warrant this. It's as if Google assumes everyone is running the latest Macbook Pro with everything decked out. Some of us run ThinkPads from 1999.

Chrome does have a very big step up over Safari however, specifically involving web development. The web inspector and console are just superior to Safari, as well as network management. This is mainly why Chrome isn't uninstalled from my computer. However it lacks strength in CORS related areas, where extensions are needed to make it work. Safari Technology Preview ships naturally with this (it may also be in the latest Safari but I haven't had an work with CORS recently).

On my Linux build, I use Chromium, which is the open source alternative to Chrome, mainly for quick single tab work like Youtube, or if I am developing. Since I like to keep everything on the keyboard and quite streamlined, I don't use it for larger tasks such as reading news while getting through the Arch wiki because I've obviously broken something. I use qutebrowser for that, particularly because it holds my favourite vim keybindings for most efficient movement through everything. But this is a completely different lecture.

All up, I love Safari on my Mac. It's lightweight and fits into the ecosystem flawlessly. It has added privacy compared to Chrome, which is just eating away at your system in the background. However Chrome has an important place for me when it comes to web development, and so will continue to have my love.