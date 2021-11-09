# Week 7

### Practice Tracing
What is the output for each of these blocks of code?  
1.
```c++
int Sum(int a, int b) {
    return a + b;
}

int main() {
    cout << Sum(10, 15) << endl;
}
```

2.
```c++
bool IsPositive(int a) {
    bool isPos = 0;
    if (a >= 0) {
        isPos = 1;
    }

    return isPos;
}

int main() {
    int x = 15;
    cout << x << " is ";
    if (IsPositive(x)) {
        cout << "positive" << endl;
    }
    else {
        cout << "negative" << endl;
    }
}
```

3.
```c++
bool PrintString(string str) {
    cout << str << endl;
    return 1;
}

int main() {
    if (PrintString("Good Morning!")) {
        cout << "Print Successful" << endl;
    }
    else {
        cout << "Print Unsuccessful" << endl;
    }
}
```

4.
```c++
double GetSide(int side) {
    double sideVal = 0.0;

    if (side == 0) {    // assume input is 5
        cout << "Enter width: ";
        cin >> sideVal;
    }
    else if (side == 1) {   // assume input is 10
        cout << "Enter length: ";
        cin >> sideVal;
    }
    else if (side == 2) {   // assume input is 3
        cout << "Enter height: ";
        cin >> sideVal;
    }
    else {
        sideVal = 0.0;
    }

    return sideVal;
}

double CubeVol(double w, double l, double h) {
    return w * l * h;
}

int main() {
    cout << CubeVol(GetSide(0),
                    GetSide(1),
                    GetSide(2)) 
        << endl;
}
```

5.
```c++
void Print(string str) {
    cout << str << endl;
}
void Print(int n) {
    cout << n << endl;
}
void Print(char c) {
    cout << c << endl;
}
void PrintAll(string str, int n, char c) {
    Print(str);
    Print(n);
    Print(c);
}

int main() {
    string s = "Functions are interesting!";
    int x = 155;
    char c = 97;
    Print(x);
    Print(c);
    Print(s);
    PrintAll(s, x, c);
}
```

### Explore This!
Now that you've done the above 5 tracing problems, did you notice anything special about some of them?
Specifically, is there anything interesting about code (4) and code (5)?

Well, there is in fact something interesting about them! Can you identify them?

If you're having trouble understanding, that's okay. Here it is:
* (4) has us use functions as arguments. More specifically, we're using the return value of those functions as arguments for another function.
* (5) has us use different functions, yet those functions are all similarly named.
    * This is known as **function overloading**. You're essentially overloading that function number name to perform multiple tasks
    * Compiler decides which function to use based on your arguments.
    * **BE CAREFUL!** If **BOTH** the *parameters* and *function name* are the same, this is actually re-defining, which will give you an error

Remember the function `getline`?  
This function utilizes the idea of function overloading. It looks like this:  

```c++
// delim is the char you will want to stop reading at
istream& getline (istream& is, string& str, char delim);    
istream& getline (istream& is, string& str);
```
**YOU DON'T NEED TO KNOW WHAT ANY OF THE DATA TYPES ARE**  

There are two functions, but defined differently so that if you were to have one extra argument, it will use one function over the other (similarly vice versa)

`getline` can also be implemented like this with a single function rather than two overloaded ones:
```c++
istream& getline (istream& is, string& str, char delim = '\n'); 
```
The last parameter is known as an **optional parameter**. Essentially, it:
1. Checks if there's an argument for this parameter
2. If there *is* an argument, assign the argument to `delim`
3. If there *isn't* an argument, assign `delim` with the pre-designated value `\n` (endline).

It's optional because if there isn't an argument, there'll be another value ready for it already.

### Coding Practice
1. **Who's the bigger area now?**

    Create a program that will ask the user for two diameters. Using functions, the program will calculate the surface area of two spheres using each of the diameters.
The program will then output both solutions using a `print()` function. Additionally, the program will determine which sphere has a larger surface area (using a function).
   
2. **Powering Up**

    Create a program that will take in a **double** and an **integer**. The program will then calculate **double** to the power of **integer**.
Use a function for this program.
   
3. **esreveR**

    Create a program that will utilize a function that will **reverse** an inputted string (i.e car becomes rac).
Make sure to ask the user for an input.  
    Hint: How do you swap letters?