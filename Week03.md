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
    <summary>
    </summary>
</details>