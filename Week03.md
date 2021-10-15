# Week 3

### Tracing Practice
Assume all libraries are included
1.
```c++
int x = -1;
int y = 2;

x = y;
y = x * x;

std::cout << x << " " << y << std::endl;
```
<details>
    <summary>Answer
    </summary>

`2 4`
</details>

2.
```c++
int x; std::cin >> x;

if (x % 2 == 0) {
    x = 1;
}
else {
    x = -1;
}

std::cout << x << std::endl;
```
<details>
    <summary>Answer
    </summary>

Even: `1`  
Odd: `-1`
</details>

3.
```c++
int x = 3;
double y = 2;
unsigned z;

z = x;
std::cin >> z;  // input is 10
z *= x;

x = z / y;
y = z / x;

std::cout << x << y << z << std::endl;
```
<details>
    <summary>Answer
    </summary>

`15230`
</details>

4.
```c++
// test with -1, 16, and 20
int input = 0; std::cin >> input;
int x = input * 3;
double result = 0.0;

if (x <= 0) {
    result = 0.0;
}
else if (x < 50) {
    result = static_cast<double>(input) / 5;
}
else {
    result = input / 10;
}

std::cout << result << std::endl;
```
<details>
    <summary>Answer
    </summary>

Input: `-1`, Output: `0`  
Input: `16`, Output: `3.2`  
Input: `20`, Output: `2`  
</details>

5.
```c++
int x = 3;
int y = 10;
int z = 0;

z = y / x;
if (z % 2 == 0) {
    z = y * x;
}
else {
    z *= y;
}

int a;
if (z > 20 && z < 60) {
    a = --z;
}
else {
    a = -z;
}

std::cout << a << std::endl;
```
<details>
    <summary>Answer
    </summary>

`29`
</details>

6. **CHALLENGE**
```c++
int x = 3;
int y = 10;
int z = -2;

if (z < y) 
    x = y;
else 
    z = y;

int a = (x + y + z) / 3;
int b;
if (a > 8)
    b = static_cast<int>(((static_cast<double>(a) + (x * y)) - 10) / 3) % 7;
else if (a < 3) 
    b = static_cast<double>((a-- + sqrt(x))) / 2;

std::cout << b << std::endl;
```
<details>
    <summary>Answer
    </summary>

`4196144`
</details>

### Trace N' Code
<b>Instructions</b>  
This activity consists of Part A and Part B.
* Part A: Trace the code as demonstrated last session
    * Provide the **output**
    * List **all** errors and bugs that you think may be encountered (There may also be none)
      * Include the fixes and the expected output
      * **NOTE: DO NOT CHANGE THE OVERALL ATTEMPTED RESULTS**
* Part B: Write code according to the prompt
    * Trace through your code with the given inputs and outputs

#### Part A
1)
```c++
const int x = 3;
int y = 0;
y = x * x;
x = 10;

std::cout << x * y << std::endl;
```

2)
```c++
double x = 9;
int y = 3;

y = x % y;
if (x == 0) {
    y = x * 100
}
else if (x == 1) {
    y = x * 10;
}

std::cout << y << std::endl;
```

3)
```c++
int a = 30;
int r = 10;
const double pi = -3.14;

int A_circ = (r * r) * pi;
if (A_circ < a) std::cout << a << std::endl;
else std::cout << A_circ << std::endl;

if (A_circ != pi) A_circ = pi;
else if (A_circ < pi) A_circ = pi * 3;

std::cout << A_circ << std::endl;
```

4)
```c++
int x = 4;
int y = 2;

y *= x;
double a = pow(y, x);
int b = static_cast<int> (a);

while (b > 0) {
    b /= 2;
    std::cout << b << std::endl;
}
```

<details>
    <summary>Answers</summary>

1) compile error: const changing, either remove const or remove `x=10` and do `x * 10`  
   output if correct: `90`

2) compile errors: double can't modulo, missing semicolon. change double to int, add semicolon after `y = x * 100`  
   output if correct: `0`

3) bugs: negative pi, results stored in int. Change sign of pi, change int to double  
   output if correct:
   ```c++
   314 
   3.14
   ```

4) no bugs or error  
    ```c++
    2048
    1024
    512
    256
    128
    64
    32
    16
    8
    4
    2
    1
    0
    ```
</details>

#### Part B

1) Write code following prompt:  
   A student wishes to use a program that can compare the density between a **sphere** and a **cube**.
   Write a program that will ask the student to input the *mass* and *dimensions* (radius/sides) of the shape.
   Output the densities of both objects and of which one has the larger density.  
   If the two objects have the same exact density, output that they are equal.
   Then determine which object has a larger density compared to water.
   * Important Info:
      * You do **NOT** need to convert units, assume it's the correct units
      * density = mass / volume
      * density of water = 997
      * Volume of cube: s^3
      * Volume of sphere: 4/3 * pi * r^3
2) Write code for the following prompt:  
   Ask the user for their full name.
   If the first letters of their first and last name is not capitalized, capitalize it.
   If any other names are uppercase, change them to lower case.
   If there are any symbols other than a hyphen (-) or numbers, remove them from the name.
   Output the person's full name. If the person's last name is more than 7 characters, print out the abbreviation.
   On the next line, output the total letters in the name.  
   
   If the name *Kris Miller* is entered, output "Hello Professor Kris Miller!"  
  Example Output (Jason jalepeno):  
  Jason J.  
  Number of letters: 13   