

#### Loops
One part of the above code that we need to take a more detailed look at is the for loop. Loops are a very important concept in programming, which allow you to keep running a piece of code over and over again, until a certain condition is met.

To start with, go to your browser developer tools JavaScript console again, and enter the following:

  	for (var i = 1 ; i < 21 ; i++) { console.log(i) }

What happened? The numbers 1 to 20 were printed out in your console. This is because of the loop. A for loop takes three input values (arguments):

A starting value: In this case we are starting a count at 1, but this could be any number you like. You can replace i with any name you like too, but i is used as a convention because it's short and easy to remember.

An exit condition: Here we have specified i < 21 — the loop will keep going until i is no longer less than 21. When i reaches 21, the loop will no longer run.

An incrementor: We have specified i++, which means "add 1 to i". The loop will run once for every value of i, until i reaches a value of 21 (as discussed above). In this case, we are simply printing the value of i out to the console on every iteration using console.log().
Now let's look at the loop in our number guessing game — the following can be found inside the resetGame() function:

	var resetParas = document.querySelectorAll('.resultParas p');
	for (var i = 0 ; i < resetParas.length ; i++) {
	  resetParas[i].textContent = '';
	}
This code creates a variable containing a list of all the paragraphs inside <div class="resultParas"> using the querySelectorAll() method, then it loops through each one, removing the text content of each.
	
####A small discussion on objects
Let's add one more final improvement before we get to this discussion. Add the following line just below the var resetButton; line near the top of your JavaScript, then save your file:
	
	guessField.focus();
	
This line uses the focus() method to automatically put the text cursor into the <input> text field as soon as the page loads, meaning that the user can start typing their first guess right away, and doesn't have to click the form field first. It's only a small addition, but it improves usability — giving the user a good visual clue as to what they've got to do to play the game.

Let's analyze what's going on here in a bit more detail. In JavaScript, everything is an object. An object is a collection of related functionality stored in a single grouping. You can create your own objects, but that is quite advanced and we won't be covering it until much later in the course. For now, we'll just briefly discuss the built-in objects that your browser contains, which allow you to do lots of useful things.

In this particular case, we first created a guessField variable that stores a reference to the text input form field in our HTML — the following line can be found amongst our variable declarations near the top:

	var guessField = document.querySelector('.guessField');
	
To get this reference, we used the querySelector() method of the document object. querySelector() takes one piece of information — a CSS selector that selects the element you want a reference to.

Because guessField now contains a reference to an <input> element, it will now have access to a number of properties (basically variables stored inside objects, some of which can't have their values changed) and methods (basically functions stored inside objects). One method available to input elements is focus(), so we can now use this line to focus the text input:

	guessField.focus();

Variables that don't contain references to form elements won't have focus() available to them. For example, the guesses variable contains a reference to a <p> element, and guessCount contains a number.
