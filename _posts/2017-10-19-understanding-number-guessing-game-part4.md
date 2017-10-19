---
layout: post
title: Understanding Number Guessing Game part 4 (Conditionals)
categories: [Javascript]
---

#### Conditionals
Returning to our checkGuess() function, I think it's safe to say that we don't want it to just spit out a placeholder message. We want it to check whether a player's guess is correct or not, and respond appropriately.

At this point, replace your current checkGuess() function with this version instead:

	1	function checkGuess() {
	2	  var userGuess = Number(guessField.value);
	3	  if (guessCount === 1) {
	4	    guesses.textContent = 'Previous guesses: ';
	5	  }
	6	  guesses.textContent += userGuess + ' ';
	7
	8	  if (userGuess === randomNumber) {
	9	    lastResult.textContent = 'Congratulations! You got it right!';
	10	    lastResult.style.backgroundColor = 'green';
	11	    lowOrHi.textContent = '';
	12	    setGameOver();
	13	  } else if (guessCount === 10) {
	14	    lastResult.textContent = '!!!GAME OVER!!!';
	15	    setGameOver();
	16	  } else {
	17	    lastResult.textContent = 'Wrong!';
	18	    lastResult.style.backgroundColor = 'red';
	19	    if(userGuess < randomNumber) {
	20	      lowOrHi.textContent = 'Last guess was too low!';
	21	    } else if(userGuess > randomNumber) {
	22	      lowOrHi.textContent = 'Last guess was too high!';
	23	    }
	24	  }
	25
	26	  guessCount++;
	27	  guessField.value = '';
	28	  guessField.focus();
	29	}
This is a lot of code — phew! 
So...
The first line (line 2 above) declares a variable called userGuess and sets its value to the current value entered inside the text field. We also run this value through the built-in Number() method, just to make sure the value is definitely a number.

Next, we encounter our first conditional code block (lines 3–5 above). A conditional code block allows you to run code selectively, depending on whether a certain condition is true or not. It looks a bit like a function, but it isn't. The simplest form of conditional block starts with the keyword if, then some parentheses, then some curly braces. Inside the parentheses we include a test. If the test returns true, we run the code inside the curly braces. If not, we don't, and move on to the next bit of code. In this case the test is testing whether the guessCount variable is equal to 1 (i.e. whether this is the player's first go or not):
	
	guessCount === 1
If it is, we make the guesses paragraph's text content equal to "Previous guesses: ". If not, we don't.

Line 6 appends the current userGuess value onto the end of the guesses paragraph, plus a blank space so there will be a space between each guess shown.
The next block (lines 8–24 above) does a few checks:
	1. The first if(){ } checks whether the user's guess is equal to the randomNumber set at the top of our JavaScript. If it is, the player has guessed correctly and the game is won, so we show the player a congratulations message with a nice green color, clear the contents of the Low/High guess information box, and run a function called setGameOver(), which we'll discuss later.
	2. Now we've chained another test onto the end of the last one using an else if(){ } structure. This one checks whether this turn is the user's last turn. If it is, the program does the same thing as in the previous block, except with a game over message instead of a congratulations message.
	3. The final block chained onto the end of this code (the else { }) contains code that is only run if neither of the other two tests returns true (i.e. the player didn't guess right, but they have more guesses left). In this case we tell them they are wrong, then we perform another conditional test to check whether the guess was higher or lower than the answer, displaying a further message as appropriate to tell them higher or lower.

The last three lines in the function (line 26–28 above) get us ready for the next guess to be submitted. We add 1 to the guessCount variable so the player uses up their turn (++ is an incrementation operation — increment by 1), and empty the value out of the form text field and focus it again, ready for the next guess to be entered.

Continue to [part 5](https://reizariva-hale.github.io/understanding-number-guessing-game-part4/) where we also talk about Events.
