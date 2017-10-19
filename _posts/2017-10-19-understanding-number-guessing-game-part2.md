#### Adding variables to store our data
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
	
