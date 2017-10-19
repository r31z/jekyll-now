---
layout: post
title: Understanding Number Guessing Game part 5 (Events)
categories: [Javascript]
---
#### Events
At this point we have a nicely implemented checkGuess() function, but it won't do anything because we haven't called it yet. Ideally we want to call it when the "Submit guess" button is pressed, and to do this we need to use an event. Events are actions that happen in the browser, like a button being clicked, or a page loading, or a video playing, in response to which we can run blocks of code. The constructs that listen out for the event happening are called event listeners, and the blocks of code run in response to the event firing are called event handlers.

Add the following line below the closing curly brace of your checkGuess() function:
  
