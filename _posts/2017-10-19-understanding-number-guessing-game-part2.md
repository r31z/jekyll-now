---
layout: post
title: Understanding Number Guessing Game part 2 (Variables)
categories: [Javascript game]
---
#### Adding variables to store our data - Understanding Number Guessing Game
Let's get started. First of all, add the following lines inside the <script> element:
		
	var randomNumber = Math.floor(Math.random() * 100) + 1;

	var guesses = document.querySelector('.guesses');
	var lastResult = document.querySelector('.lastResult');
	var lowOrHi = document.querySelector('.lowOrHi');

	var guessSubmit = document.querySelector('.guessSubmit');
	var guessField = document.querySelector('.guessField');

	var guessCount = 1;
	var resetButton;
	
This section of the code sets up the variables we need to store the data our program will use. Variables are basically containers for values (such as numbers, or strings of text). You create a variable with the keyword var followed by a name for your variable. You can then assign a value to your variable with an equals sign (=) followed by the value you want to give it.

In our example:

The first variable — randomNumber — is assigned a random number between 1 and 100, calculated using a mathematical algorithm.
The next three variables are each made to store a reference to the results paragraphs in our HTML, and are used to insert values into the paragraphs later on in the code:
	
	<p class="guesses"></p>
	<p class="lastResult"></p>
	<p class="lowOrHi"></p>
	
The next two variables store references to the form text input and submit button and are used to control submitting the guess later on.
	
	<label for="guessField">Enter a guess: </label>
	<input type="text" id="guessField" class="guessField">
 	<input type="submit" value="Submit guess" class="guessSubmit">
	
Our final two variables store a guess count of 1 (used to keep track of how many guesses the player has had), and a reference to a reset button that doesn't exist yet (but will later).

Continue to Understanding Number Guessing Game [part 3](https://reizariva-hale.github.io/understanding-number-guessing-game-part3/) where we talk about Functions.
