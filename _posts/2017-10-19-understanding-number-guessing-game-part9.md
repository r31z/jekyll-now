---
layout: post
title: Understanding Number Guessing Game part 6 (Events)
categories: [Javascript]
---
#### Events
At this point we have a nicely implemented checkGuess() function, but it won't do anything because we haven't called it yet. Ideally we want to call it when the "Submit guess" button is pressed, and to do this we need to use an event. Events are actions that happen in the browser, like a button being clicked, or a page loading, or a video playing, in response to which we can run blocks of code. The constructs that listen out for the event happening are called event listeners, and the blocks of code run in response to the event firing are called event handlers.

Add the following line below the closing curly brace of your checkGuess() function:
    
    guessSubmit.addEventListener('click', checkGuess);
    
Here we are adding an event listener to the guessSubmit button. This is a method that takes two input values (called arguments) — the type of event we are listening out for (in this case click) as a string, and the code we want to run when the event occurs (in this case the checkGuess() function — note that we don't need to specify the parentheses when writing it inside [addEventListener())](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener).

Try saving and refreshing your code now, and your example should now work, to a point. The only problem now is that if you guess the correct answer or run out of guesses, the game will break because we've not yet defined the setGameOver() function that is supposed to be run once the game is over. Let's add our missing code now and complete the example functionality.

Continue to [part 6](https://reizariva-hale.github.io/understanding-number-guessing-game-part6/) where we also talk about Conditionals.
