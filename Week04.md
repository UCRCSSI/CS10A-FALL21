# Week 4

Today you'll be exploring how `rand()` and `%` can be utilized together to obtain a desired result.
For each question, discuss with your group and come to an agreed consensus before continuing.

To start off, take a look at this code:
```c++
int n = 12591253;

std::cout << n % 5 << std::endl;
```
* What is the output of this code?

Now, let's modify the code to look like this:
```c++
int n = 0;
std::cin >> n;

std::cout << n % 5 << std::endl;
```
* What are the possible outputs of this code? (Plug in different values into the cin)
* What is the largest output from this code?
* What is the smallest output from this code?

Let's take a look at `rand()`. Trace through this code (use your own custom & appropriate values):
```c++
int n = rand();

std::cout << n << std::endl;
```
* What does rand() give us each time we run it? **(generally, not a numerical value)**

Let's now look at what happens if we add this line of code at the end:
```c++
int n = rand();

std::cout << n << std::endl;
std::cout << n % 10 << std::endl;
```
* What is the a possible output from this code? **(use your own custom & appropriate values)**
* For the second output, what is the largest number that can be printed?
* For the second output, what is the smallest number that can be printed?
* What does doing `rand() % x`, where `x` is some integer, actually do?

<br>
</br>

You should have realized that `%` imposes some effect on the passed in value on the left hand side.
If we combine that with `rand()` we can generate a "random" number of a certain range.  
Using this knowledge, write your own code for the following prompts:
1. Create a program that will generate a number from **0 - 20**
2. Create a program that will generate a number from **0 - 20 inclusive**
3. Create a program that will generate a number from **-30 - 20 inclusive**

*Hint: Given the divisor (right hand side of %), what is the lowest value? What is the highest value? How can you shift ranges up or down?*

**Before continuing, ask the SIL to come to the room and share the code from the above prompts. Use the "Ask for Help" button.**

For the next bit, we're going to dive into a little about certain inputs and when to use them.  
First, take a look at this code:
```c++
int n = 0;
while (n < 4) {
    std::cout << n++ << std::endl;
}
```
* What is the output of this code?

That was a nice review of incremental while loops. Now, let's look at this while loop:
```c++
int n = 0;

while (n == 4) {
    std::cout << "IN" << std::endl;
}
```
* How many times does the loop run for?
* What is the bug in the above code?

Now, let's modify/fix the above code to look like this:
```c++
int n = 0;

std::cin >> n;
while (n != 4) {
    if (n < 4)
        std::cout << "Less" << std::endl;
    else 
        std::cout << "More" << std::endl;
}
```
* What is the output if `3` is inputted? What about `6`? `4`?
* How many times does this while loop loop for?

Notice that we are stuck in the loop. We need to update the `n` somehow.  
Take the above code and add a **single** line of code that could allow us to escape the loop.  

Finally, let's look at string input. Your briefly covered strings in lecture and in chapter 1/2.
Take a look at this code:
```c++
std::cout << "Hello" << std::endl;
```
* What type of string is being outputted here? (Hint: *String L...*.)

Now look at this code:
```c++
std::string n = "";
std::cin >> n;
std::cout << n << std::endl;
```
* If we input `Hello there`, what would be the output?
* Why is the output like this? (it's okay if you don't know)

What if we changed it to look like this:
```c++
std::string n = "";
std::getline(std::cin, n);
std::cout << n << std::endl;
```
* Now, if we input `Hello there`, what would be the output?
* What is the output like this? (look at what changed, and see what the new code says)

<br>
</br>

Nice! You now have a general understanding of loops and `rand()` and string inputs.  
Now to put it all together, you will now write a program that combines all of this.

For this coding practice, you will be writing a random password 2FA locker.
* Generate a random number between 0 and 400 inclusive.
* Give the user 3 tries to guess the number.
* If the user is unable to guess the number in 3 tries output the number and output your own "wrong" message and generate a new random number that is between 0 and 300 inclusive.
* Give the user 3 tries to guess the new number.
* If the user is still unable to guess the number output the number and output your own "wrong" message and generate another new random number between 0 and 200 inclusive.

Notice the pattern, as we give them a new number to guess, the range decreases. Keep asking the user to guess the number until they fail the 4th attempt (0 - 100 inclusive).

If the user guesses correctly, exit loop, and output `Hooray!`, otherwise output your own "failed" message.

Think: How can be use loops to simplify the code? How can we use decremental operators to do this?