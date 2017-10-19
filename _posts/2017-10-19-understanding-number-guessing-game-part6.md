---
layout: post
title: Understanding Number Guessing Game part 6 (Finishing the game)
categories: [Javascript]
---
Let's add that setGameOver() function to the bottom of our code and then walk through it. Add this now, below the rest of your JavaScript:
	 
	1  function setGameOver() {
	2   guessField.disabled = true;
	3   guessSubmit.disabled = true;
	4  resetButton = document.createElement('button');
	5   resetButton.textContent = 'Start new game';
	6   document.body.appendChild(resetButton);
	7   resetButton.addEventListener('click', resetGame);
	8 }
	
The first two lines disable the form text input and button by setting their disabled properties to true. This is necessary, because if we didn't, the user could submit more guesses after the game is over, which would mess things up.

The next three lines generate a new <button> element, set its text label to "Start new game", and add it to the bottom of our existing HTML.
	
The final line sets an event listener on our new button so that when it is clicked, a function called resetGame() is run.
Now we need to define this function too! Add the following code, again to the bottom of your JavaScript:

	1   function resetGame() {
	2    guessCount = 1;
	3
	4   var resetParas = document.querySelectorAll('.resultParas p');
	5   for (var i = 0 ; i < resetParas.length ; i++) {
	6     resetParas[i].textContent = '';
	7   }
	8
	9   resetButton.parentNode.removeChild(resetButton);
	10
	11   guessField.disabled = false;
	12   guessSubmit.disabled = false;
	13   guessField.value = '';
	14   guessField.focus();
	15
	16   lastResult.style.backgroundColor = 'white';
	17
	18   randomNumber = Math.floor(Math.random() * 100) + 1;
	19  }
	
This rather long block of code completely resets everything to how it was at the start of the game, so the player can have another go. It:

- Puts the guessCount back down to 1.
- Clears all the information paragraphs.
- Removes the reset button from our code.
- Enables the form elements, and empties and focuses the text field, ready for a new guess to be entered.
- Removes the background color from the lastResult paragraph.
- Generates a new random number so that you are not just guessing the same number again!
- At this point you should have a fully working (simple) game — congratulations!

All we have left to do now in this article is talk about a few other important code features that you've already seen, although you may have not realised this. So let's continue to the last part - [part 7](https://reizariva-hale.github.io/understanding-number-guessing-game-part7/) where we also talk about Loops.
