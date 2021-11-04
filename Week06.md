# Week 7

This will be another explorative session. This time, you will be looking ahead at Chapter 7: Functions.  

To start off, do these functions look familiar?
```c++
pow(x, y);
at(i);
toupper('');
...
```

There are many more functions of which you have already used.  
**Go ahead and list 3 other functions that you have used so far with your group**  

Take a look at this algorithm:
```c++
int sol = 1;
for (size_t i = 0; i < y; i++) {
    if (i == 0) {
        sol = x;
    }
    else {
        sol *= x;
    }
}
```
* What does this algorithm do?
* If `x` was 2 and `y` was 5, what would `sol` be?

Now take a look at this code:
```c++
int x = 2;
int y = 3;
int sol = 1;
for (size_t i = 0; i < y; i++) {
    if (i == 0) {
        sol = x;
    }
    else {
        sol *= x;
    }
}
x = 231;
y = 2;
sol = 1;
for (size_t i = 0; i < y; i++) {
    if (i == 0) {
        sol = x;
    }
    else {
        sol *= x;
    }
}
x = 5;
y = 12;
sol = 1;
for (size_t i = 0; i < y; i++) {
    if (i == 0) {
        sol = x;
    }
    else {
        sol *= x;
    }
}
```
* Do you like how this looks?
* How many loops do we have to manually code or copy and paste?

Oh boy, how it would be nice if we had a way to make the code shorter somehow :think:

Take a look at this:
```c++
int foo(int x);
```
* What is this?
* What does it do?

The code above is new. It's a part of chapter 7: Functions. What does it do? Take a look at this code:
```c++
int foo(int x, int y) {
    int sol = 1;
    for (size_t i = 0; i < y; i++) {
        if (i == 0) {
            sol = x;
        }
        else {
            sol *= x;
        }
    }
    
    return sol;
}

int main() {
    foo(2, 3);
    foo(231, 2);
    foo(5, 12);
}
```
* Does this code look familiar to something you've seen before? Perhaps *recently*
* What is happening here?

This code does the exact same thing as what you saw earlier. But it's sooo much shorter :D.  
* Now, go ahead and format a list of benefits that functions can give us **(there should be 3)**

<hr>
</hr>

Take a look at the  code again, but specifically the function:
```c++
int foo(int x, int y) {
    int sol = 1;
    for (size_t i = 0; i < y; i++) {
        if (i == 0) {
            sol = x;
        }
        else {
            sol *= x;
        }
    }
    
    return sol;
}
```
**For each of these, discuss with your group members**
* What is this function doing?
* Looking at `int foo(int x, int y)`, what does the first `int` do?
    * What about the second `int x`? the third `int y`?
    * What exactly is `foo`?

Now looking at the inside of the function, you should notice a few things.
* First, notice the `x` and `y` being used. Where are they coming from?
* What is `return sol` doing?

**The SIL will ask you questions regarding the above information here**

Nice! Look at these two functions:
```c++
bool foo(int x) {
    bool ret = 0;
    if (x > 0) {
        ret = 1;
    }
    
    return ret;
}
bool bar(int x) {
    if (x > 0) {
        return true;
    }
    
    return false;
}
```
Notice the format of the two functions above. 
Comparing the two and the earlier power function (the one above this code block), answer these questions:
* What is the general format for a function (identify the different parts)
    * What should be the first line (before the `{`) consist of?
    * What goes inside the `()`?
    * What "always" goes at the end of the function before `}`?

Now, look at the top block of code with the `bool`s. There are two functions here, what's the difference?

You should notice that there's a big difference between these two.  
The difference is the length of the functions.  
In fact, that's all there is! The functions are the same; however, they utilize two different methods.
The first utilizes a `bool` variable within the function and returns that.
The second simply returns the **constant `true` or `false`**.
**However, for now, always write your code like the top bool function.**
The second function, especially since you're only starting to learn, is likely to lead to bugs.

Finally, look at this function:
```c++
void foo(string str) {
    cout << str << endl;
//    return;
}
```
* What does this function do?
* Note that the `return` is commented out. This function doesn't need it, why?
* Answer the two questions above, what does `void` do?

Final note: Although void functions don't technically need a return, you can still put one.
