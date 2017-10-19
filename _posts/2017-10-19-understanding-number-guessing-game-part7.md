

#### Loops
One part of the above code that we need to take a more detailed look at is the for loop. Loops are a very important concept in programming, which allow you to keep running a piece of code over and over again, until a certain condition is met.

To start with, go to your browser developer tools JavaScript console again, and enter the following:

  for (var i = 1 ; i < 21 ; i++) { console.log(i) }

What happened? The numbers 1 to 20 were printed out in your console. This is because of the loop. A for loop takes three input values (arguments):

A starting value: In this case we are starting a count at 1, but this could be any number you like. You can replace i with any name you like too, but i is used as a convention because it's short and easy to remember.
An exit condition: Here we have specified i < 21 — the loop will keep going until i is no longer less than 21. When i reaches 21, the loop will no longer run.
An incrementor: We have specified i++, which means "add 1 to i". The loop will run once for every value of i, until i reaches a value of 21 (as discussed above). In this case, we are simply printing the value of i out to the console on every iteration using console.log().
Now let's look at the loop in our number guessing game — the following can be found inside the resetGame() function:

