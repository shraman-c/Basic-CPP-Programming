# Basic C++ Programing

## Assignment 1

### 1.	Write a C Program to Check weather a no. is Positive, negative or zero.

**Source Code:**
```c
#include <stdio.h>

int main() {
    int num;
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    if (num > 0) {
        printf("%d is Positive\n", num);
    } else if (num < 0) {
        printf("%d is Negative\n", num);
    } else {
        printf("The number is Zero\n");
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 15
15 is Positive

Enter a number: -8
-8 is Negative

Enter a number: 0
The number is Zero
```

---

### 2. Write a C program to find the even numbers between 1-50

**Source Code:**
```c
#include <stdio.h>

int main() {
    printf("Even numbers between 1 and 50:\n");
    
    for (int i = 1; i <= 50; i++) {
        if (i % 2 == 0) {
            printf("%d ", i);
        }
    }
    printf("\n");
    
    return 0;
}
```

**Output:**
```
Even numbers between 1 and 50:
2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50
```

---

### 3. Write in C to find the Armstrong number.

**Source Code:**
```c
#include <stdio.h>
#include <math.h>

int main() {
    int num, originalNum, remainder, result = 0, n = 0;
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    originalNum = num;
    
    // Count number of digits
    while (originalNum != 0) {
        originalNum /= 10;
        n++;
    }
    
    originalNum = num;
    
    // Calculate sum of nth power of digits
    while (originalNum != 0) {
        remainder = originalNum % 10;
        result += pow(remainder, n);
        originalNum /= 10;
    }
    
    if (result == num) {
        printf("%d is an Armstrong number\n", num);
    } else {
        printf("%d is not an Armstrong number\n", num);
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 153
153 is an Armstrong number

Enter a number: 370
370 is an Armstrong number

Enter a number: 123
123 is not an Armstrong number
```

---

### 4. Write in C to find the Factorial using functions

**Source Code:**
```c
#include <stdio.h>

int factorial(int n) {
    if (n == 0 || n == 1) {
        return 1;
    }
    return n * factorial(n - 1);
}

int main() {
    int num;
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    if (num < 0) {
        printf("Factorial is not defined for negative numbers\n");
    } else {
        printf("Factorial of %d = %d\n", num, factorial(num));
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 5
Factorial of 5 = 120

Enter a number: 7
Factorial of 7 = 5040
```

---

## Assignment 2

### 1. Write in C to find the Armstrong number using function.

**Source Code:**
```c
#include <stdio.h>
#include <math.h>

int isArmstrong(int num) {
    int originalNum = num, remainder, result = 0, n = 0;
    
    // Count digits
    while (originalNum != 0) {
        originalNum /= 10;
        n++;
    }
    
    originalNum = num;
    
    // Calculate sum
    while (originalNum != 0) {
        remainder = originalNum % 10;
        result += pow(remainder, n);
        originalNum /= 10;
    }
    
    return (result == num);
}

int main() {
    int num;
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    if (isArmstrong(num)) {
        printf("%d is an Armstrong number\n", num);
    } else {
        printf("%d is not an Armstrong number\n", num);
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 1634
1634 is an Armstrong number
```

---

### 2. Write a C program to find odd or even using function.

**Source Code:**
```c
#include <stdio.h>

void checkOddEven(int num) {
    if (num % 2 == 0) {
        printf("%d is Even\n", num);
    } else {
        printf("%d is Odd\n", num);
    }
}

int main() {
    int num;
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    checkOddEven(num);
    
    return 0;
}
```

**Output:**
```
Enter a number: 24
24 is Even

Enter a number: 17
17 is Odd
```

---

### 3. Write in C to design a calculator using switch case

**Source Code:**
```c
#include <stdio.h>

int main() {
    char operator;
    double num1, num2, result;
    
    printf("Enter an operator (+, -, *, /): ");
    scanf(" %c", &operator);
    
    printf("Enter two numbers: ");
    scanf("%lf %lf", &num1, &num2);
    
    switch (operator) {
        case '+':
            result = num1 + num2;
            printf("%.2lf + %.2lf = %.2lf\n", num1, num2, result);
            break;
        case '-':
            result = num1 - num2;
            printf("%.2lf - %.2lf = %.2lf\n", num1, num2, result);
            break;
        case '*':
            result = num1 * num2;
            printf("%.2lf * %.2lf = %.2lf\n", num1, num2, result);
            break;
        case '/':
            if (num2 != 0) {
                result = num1 / num2;
                printf("%.2lf / %.2lf = %.2lf\n", num1, num2, result);
            } else {
                printf("Error! Division by zero\n");
            }
            break;
        default:
            printf("Invalid operator\n");
    }
    
    return 0;
}
```

**Output:**
```
Enter an operator (+, -, *, /): *
Enter two numbers: 12 5
12.00 * 5.00 = 60.00
```

---

### 4. Write in C to check weather a character is Vowel or not.

**Source Code:**
```c
#include <stdio.h>

int main() {
    char ch;
    
    printf("Enter a character: ");
    scanf(" %c", &ch);
    
    if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
        ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') {
        printf("%c is a Vowel\n", ch);
    } else {
        printf("%c is not a Vowel\n", ch);
    }
    
    return 0;
}
```

**Output:**
```
Enter a character: e
e is a Vowel

Enter a character: k
k is not a Vowel
```

---

### 5. Write a C program to print from 1 – 10 in a Specific pattern.

**Source Code:**
```c
#include <stdio.h>

int main() {
    int i, j;
    
    printf("Pattern:\n");
    for (i = 1; i <= 10; i++) {
        for (j = 1; j <= i; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }
    
    return 0;
}
```

**Output:**
```
Pattern:
1 
1 2 
1 2 3 
1 2 3 4 
1 2 3 4 5 
1 2 3 4 5 6 
1 2 3 4 5 6 7 
1 2 3 4 5 6 7 8 
1 2 3 4 5 6 7 8 9 
1 2 3 4 5 6 7 8 9 10
```

---

## Assignment 3

### 1.  Write a C program using Structure to show the average marks of a student.
**Source Code:**
```c
#include <stdio.h>

struct Student {
    char name[50];
    int rollNo;
    float marks[5];
    float average;
};

int main() {
    struct Student s;
    float sum = 0;
    
    printf("Enter student name: ");
    scanf("%s", s.name);
    
    printf("Enter roll number: ");
    scanf("%d", &s.rollNo);
    
    printf("Enter marks of 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &s.marks[i]);
        sum += s.marks[i];
    }
    
    s.average = sum / 5;
    
    printf("\n--- Student Details ---\n");
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.rollNo);
    printf("Average Marks: %.2f\n", s.average);
    
    return 0;
}
```

**Output:**
```
Enter student name: John
Enter roll number: 101
Enter marks of 5 subjects:
Subject 1: 85
Subject 2: 90
Subject 3: 78
Subject 4: 88
Subject 5: 92

--- Student Details ---
Name: John
Roll Number: 101
Average Marks: 86.60
```

---

### 2. Write a C program to calculate the sum and product of 2 complex numbers using Struct.

**Source Code:**
```c
#include <stdio.h>

struct Complex {
    float real;
    float imag;
};

struct Complex addComplex(struct Complex c1, struct Complex c2) {
    struct Complex result;
    result.real = c1.real + c2.real;
    result.imag = c1.imag + c2.imag;
    return result;
}

struct Complex multiplyComplex(struct Complex c1, struct Complex c2) {
    struct Complex result;
    result.real = (c1.real * c2.real) - (c1.imag * c2.imag);
    result.imag = (c1.real * c2.imag) + (c1.imag * c2.real);
    return result;
}

int main() {
    struct Complex c1, c2, sum, product;
    
    printf("Enter first complex number (real and imaginary): ");
    scanf("%f %f", &c1.real, &c1.imag);
    
    printf("Enter second complex number (real and imaginary): ");
    scanf("%f %f", &c2.real, &c2.imag);
    
    sum = addComplex(c1, c2);
    product = multiplyComplex(c1, c2);
    
    printf("\nFirst Complex Number: %.2f + %.2fi\n", c1.real, c1.imag);
    printf("Second Complex Number: %.2f + %.2fi\n", c2.real, c2.imag);
    printf("Sum: %.2f + %.2fi\n", sum.real, sum.imag);
    printf("Product: %.2f + %.2fi\n", product.real, product.imag);
    
    return 0;
}
```

**Output:**
```
Enter first complex number (real and imaginary): 3 4
Enter second complex number (real and imaginary): 2 5

First Complex Number: 3.00 + 4.00i
Second Complex Number: 2.00 + 5.00i
Sum: 5.00 + 9.00i
Product: -14.00 + 23.00i
```

---

## Assignment 4

### 1. Write in C++ to add 2 numbers 

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2, sum;
    
    cout << "Enter first number: ";
    cin >> num1;
    
    cout << "Enter second number: ";
    cin >> num2;
    
    sum = num1 + num2;
    
    cout << "Sum = " << sum << endl;
    
    return 0;
}
```

**Output:**
```
Enter first number: 15
Enter second number: 25
Sum = 40
```

---

### 2. Write in C++ to Check if a number is odd or even.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    
    cout << "Enter a number: ";
    cin >> num;
    
    if (num % 2 == 0) {
        cout << num << " is Even" << endl;
    } else {
        cout << num << " is Odd" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 17
17 is Odd
```

---

### 3. Write in C++ to swap 2 numbers

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, temp;
    
    cout << "Enter first number: ";
    cin >> a;
    
    cout << "Enter second number: ";
    cin >> b;
    
    cout << "\nBefore swapping: a = " << a << ", b = " << b << endl;
    
    temp = a;
    a = b;
    b = temp;
    
    cout << "After swapping: a = " << a << ", b = " << b << endl;
    
    return 0;
}
```

**Output:**
```
Enter first number: 10
Enter second number: 20

Before swapping: a = 10, b = 20
After swapping: a = 20, b = 10
```

---

### 4. Write in C++ to Find the largest number among 3 numbers.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2, num3;
    
    cout << "Enter three numbers: ";
    cin >> num1 >> num2 >> num3;
    
    if (num1 >= num2 && num1 >= num3) {
        cout << "Largest number is: " << num1 << endl;
    } else if (num2 >= num1 && num2 >= num3) {
        cout << "Largest number is: " << num2 << endl;
    } else {
        cout << "Largest number is: " << num3 << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter three numbers: 45 78 32
Largest number is: 78
```

---

### 5. Write in C++ to find the absolute difference between n & 51. If n is greater than 51, return triple the difference.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, diff;
    
    cout << "Enter a number: ";
    cin >> n;
    
    if (n > 51) {
        diff = 3 * (n - 51);
    } else {
        diff = 51 - n;
    }
    
    cout << "Result: " << diff << endl;
    
    return 0;
}
```

**Output:**
```
Enter a number: 60
Result: 27

Enter a number: 40
Result: 11
```

---

### 6. Write in C++ to check if 2 given integers, and return true if one of them is 30 or if their sum is 30

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2;
    
    cout << "Enter two integers: ";
    cin >> num1 >> num2;
    
    if (num1 == 30 || num2 == 30 || (num1 + num2) == 30) {
        cout << "true" << endl;
    } else {
        cout << "false" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter two integers: 30 5
true

Enter two integers: 15 15
true

Enter two integers: 10 12
false
```

---

### 7. Write in C++ to check if a 2 given non negative integers to have the same last digit.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2;
    
    cout << "Enter two non-negative integers: ";
    cin >> num1 >> num2;
    
    if (num1 % 10 == num2 % 10) {
        cout << "Both numbers have the same last digit" << endl;
    } else {
        cout << "Numbers do not have the same last digit" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter two non-negative integers: 123 43
Both numbers have the same last digit

Enter two non-negative integers: 25 36
Numbers do not have the same last digit
```

---

### 8. Write in C++ to check if it is possible to add 2 integers to get the third from three given integers.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, c;
    
    cout << "Enter three integers: ";
    cin >> a >> b >> c;
    
    if ((a + b == c) || (a + c == b) || (b + c == a)) {
        cout << "true - Two integers can add to get the third" << endl;
    } else {
        cout << "false - No two integers can add to get the third" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter three integers: 5 10 15
true - Two integers can add to get the third

Enter three integers: 3 7 12
false - No two integers can add to get the third
```

---

## Assignment 5

### 1. Write in C++ to find the first 10 natural numbers.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "First 10 natural numbers:" << endl;
    
    for (int i = 1; i <= 10; i++) {
        cout << i << " ";
    }
    cout << endl;
    
    return 0;
}
```

**Output:**
```
First 10 natural numbers:
1 2 3 4 5 6 7 8 9 10
```

---

### 2. Write in C++ to find the sum of the first 10 natural numbers.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int sum = 0;
    
    for (int i = 1; i <= 10; i++) {
        sum += i;
    }
    
    cout << "Sum of first 10 natural numbers = " << sum << endl;
    
    return 0;
}
```

**Output:**
```
Sum of first 10 natural numbers = 55
```

---

### 3. Write in C++ to find the factorial of a number.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    long long factorial = 1;
    
    cout << "Enter a number: ";
    cin >> num;
    
    if (num < 0) {
        cout << "Factorial is not defined for negative numbers" << endl;
    } else {
        for (int i = 1; i <= num; i++) {
            factorial *= i;
        }
        cout << "Factorial of " << num << " = " << factorial << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 6
Factorial of 6 = 720
```

---

### 4. Write in C++ to find the sum of digits of a number.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num, sum = 0, digit;
    
    cout << "Enter a number: ";
    cin >> num;
    
    int temp = num;
    
    while (temp > 0) {
        digit = temp % 10;
        sum += digit;
        temp /= 10;
    }
    
    cout << "Sum of digits of " << num << " = " << sum << endl;
    
    return 0;
}
```

**Output:**
```
Enter a number: 1234
Sum of digits of 1234 = 10
```

---

### 5. Write in C++ to find whether a number is prime or not.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    bool isPrime = true;
    
    cout << "Enter a number: ";
    cin >> num;
    
    if (num <= 1) {
        isPrime = false;
    } else {
        for (int i = 2; i * i <= num; i++) {
            if (num % i == 0) {
                isPrime = false;
                break;
            }
        }
    }
    
    if (isPrime) {
        cout << num << " is a Prime number" << endl;
    } else {
        cout << num << " is not a Prime number" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 29
29 is a Prime number

Enter a number: 15
15 is not a Prime number
```

---

### 6. Write in C++ to find whether a number is perfect or not.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num, sum = 0;
    
    cout << "Enter a number: ";
    cin >> num;
    
    for (int i = 1; i < num; i++) {
        if (num % i == 0) {
            sum += i;
        }
    }
    
    if (sum == num && num > 0) {
        cout << num << " is a Perfect number" << endl;
    } else {
        cout << num << " is not a Perfect number" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 28
28 is a Perfect number

Enter a number: 12
12 is not a Perfect number
```

---

### 7. Write in C++ to find perfect numbers in a range.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

bool isPerfect(int num) {
    int sum = 0;
    for (int i = 1; i < num; i++) {
        if (num % i == 0) {
            sum += i;
        }
    }
    return (sum == num && num > 0);
}

int main() {
    int start, end;
    
    cout << "Enter range (start and end): ";
    cin >> start >> end;
    
    cout << "Perfect numbers between " << start << " and " << end << ":" << endl;
    
    bool found = false;
    for (int i = start; i <= end; i++) {
        if (isPerfect(i)) {
            cout << i << " ";
            found = true;
        }
    }
    
    if (!found) {
        cout << "No perfect numbers found in this range";
    }
    cout << endl;
    
    return 0;
}
```

**Output:**
```
Enter range (start and end): 1 500
Perfect numbers between 1 and 500:
6 28 496
```

---

### 8. Write in C++ to check if a number is a Strong number.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    int fact = 1;
    for (int i = 1; i <= n; i++) {
        fact *= i;
    }
    return fact;
}

int main() {
    int num, sum = 0;
    
    cout << "Enter a number: ";
    cin >> num;
    
    int temp = num;
    
    while (temp > 0) {
        int digit = temp % 10;
        sum += factorial(digit);
        temp /= 10;
    }
    
    if (sum == num) {
        cout << num << " is a Strong number" << endl;
    } else {
        cout << num << " is not a Strong number" << endl;
    }
    
    return 0;
}
```

**Output:**
```
Enter a number: 145
145 is a Strong number

Enter a number: 123
123 is not a Strong number
```

---

## Assignment 6

### 1. Create a class “Book” and calculate the Volume of a Book using member variables and functions.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Book {
private:
    float length, width, height;
    
public:
    void setDimensions(float l, float w, float h) {
        length = l;
        width = w;
        height = h;
    }
    
    float calculateVolume() {
        return length * width * height;
    }
    
    void displayVolume() {
        cout << "Volume of the book = " << calculateVolume() << " cubic units" << endl;
    }
};

int main() {
    Book b;
    float l, w, h;
    
    cout << "Enter length, width, and height of the book: ";
    cin >> l >> w >> h;
    
    b.setDimensions(l, w, h);
    b.displayVolume();
    
    return 0;
}
```

**Output:**
```
Enter length, width, and height of the book: 10 5 2
Volume of the book = 100 cubic units
```

---

### 2. Create a class “Car” and accept the details of a car for its id and price. Display the details of 2 such car objects.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Car {
private:
    int id;
    float price;
    
public:
    void setDetails(int i, float p) {
        id = i;
        price = p;
    }
    
    void displayDetails() {
        cout << "Car ID: " << id << endl;
        cout << "Car Price: $" << price << endl;
        cout << "------------------------" << endl;
    }
};

int main() {
    Car car1, car2;
    int id;
    float price;
    
    cout << "Enter details for Car 1:" << endl;
    cout << "ID: ";
    cin >> id;
    cout << "Price: ";
    cin >> price;
    car1.setDetails(id, price);
    
    cout << "\nEnter details for Car 2:" << endl;
    cout << "ID: ";
    cin >> id;
    cout << "Price: ";
    cin >> price;
    car2.setDetails(id, price);
    
    cout << "\n--- Car Details ---" << endl;
    car1.displayDetails();
    car2.displayDetails();
    
    return 0;
}
```

**Output:**
```
Enter details for Car 1:
ID: 101
Price: 25000

Enter details for Car 2:
ID: 102
Price: 30000

--- Car Details ---
Car ID: 101
Car Price: $25000
------------------------
Car ID: 102
Car Price: $30000
------------------------
```

---

### 3. Create a class “Employee”. Take user input for salary and allowance of 3 employees and display these using array of objects.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    float salary;
    float allowance;
    
public:
    void setDetails(float s, float a) {
        salary = s;
        allowance = a;
    }
    
    void displayDetails(int empNum) {
        cout << "Employee " << empNum << ":" << endl;
        cout << "Salary:" << salary << endl;
        cout << "Allowance:" << allowance << endl;
        cout << "Total:" << (salary + allowance) << endl;
        cout << "------------------------" << endl;
    }
};

int main() {
    Employee emp[3];
    float salary, allowance;
    
    for (int i = 0; i < 3; i++) {
        cout << "Enter details for Employee " << (i + 1) << ":" << endl;
        cout << "Salary: ";
        cin >> salary;
        cout << "Allowance: ";
        cin >> allowance;
        emp[i].setDetails(salary, allowance);
        cout << endl;
    }
    
    cout << "--- Employee Details ---" << endl;
    for (int i = 0; i < 3; i++) {
        emp[i].displayDetails(i + 1);
    }
    
    return 0;
}
```

**Output:**
```
Enter details for Employee 1:
Salary: 50000
Allowance: 5000

Enter details for Employee 2:
Salary: 60000
Allowance: 6000

Enter details for Employee 3:
Salary: 55000
Allowance: 5500

--- Employee Details ---
Employee 1:
Salary: 50000
Allowance: 5000
Total: 55000
------------------------
Employee 2:
Salary: 60000
Allowance: 6000
Total: 66000
------------------------
Employee 3:
Salary: 55000
Allowance: 5500
Total: 60500
------------------------
```

---

### 4. Create a class “Student”. Take user input for roll number and marks of 5 subjects of a student. Display the total marks of the student using member functions.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Student {
private:
    int rollNo;
    float marks[5];
    
public:
    void setDetails() {
        cout << "Enter roll number: ";
        cin >> rollNo;
        
        cout << "Enter marks of 5 subjects:" << endl;
        for (int i = 0; i < 5; i++) {
            cout << "Subject " << (i + 1) << ": ";
            cin >> marks[i];
        }
    }
    
    float calculateTotal() {
        float total = 0;
        for (int i = 0; i < 5; i++) {
            total += marks[i];
        }
        return total;
    }
    
    void displayDetails() {
        cout << "\n--- Student Details ---" << endl;
        cout << "Roll Number: " << rollNo << endl;
        cout << "Total Marks: " << calculateTotal() << endl;
    }
};

int main() {
    Student s;
    
    s.setDetails();
    s.displayDetails();
    
    return 0;
}
```

**Output:**
```
Enter roll number: 205
Enter marks of 5 subjects:
Subject 1: 85
Subject 2: 90
Subject 3: 78
Subject 4: 88
Subject 5: 92

--- Student Details ---
Roll Number: 205
Total Marks: 433
```

---

### 5. Swap 2 numbers using call by reference, using class and object concepts.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Swap {
public:
    void swapNumbers(int &a, int &b) {
        int temp = a;
        a = b;
        b = temp;
    }
};

int main() {
    Swap s;
    int num1, num2;
    
    cout << "Enter first number: ";
    cin >> num1;
    
    cout << "Enter second number: ";
    cin >> num2;
    
    cout << "\nBefore swapping: num1 = " << num1 << ", num2 = " << num2 << endl;
    
    s.swapNumbers(num1, num2);
    
    cout << "After swapping: num1 = " << num1 << ", num2 = " << num2 << endl;
    
    return 0;
}
```

**Output:**
```
Enter first number: 10
Enter second number: 20

Before swapping: num1 = 10, num2 = 20
After swapping: num1 = 20, num2 = 10
```

---

## Assignment 7

### 1. Write in C++ to show the use of a static variable

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Counter {
public:
    static int count;
    
    Counter() {
        count++;
    }
    
    static void displayCount() {
        cout << "Total objects created: " << count << endl;
    }
};

// Initialize static variable
int Counter::count = 0;

int main() {
    cout << "Creating objects..." << endl;
    
    Counter c1;
    Counter::displayCount();
    
    Counter c2;
    Counter::displayCount();
    
    Counter c3;
    Counter::displayCount();
    
    return 0;
}
```

**Output:**
```
Creating objects...
Total objects created: 1
Total objects created: 2
Total objects created: 3
```

---

### 2. WAP in C++ to show the use of parameterized constructor.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Rectangle {
private:
    float length;
    float width;
    
public:
    // Parameterized constructor
    Rectangle(float l, float w) {
        length = l;
        width = w;
        cout << "Rectangle created with length " << length 
             << " and width " << width << endl;
    }
    
    float calculateArea() {
        return length * width;
    }
    
    void displayArea() {
        cout << "Area of rectangle = " << calculateArea() << " square units" << endl;
    }
};

int main() {
    float l, w;
    
    cout << "Enter length and width: ";
    cin >> l >> w;
    
    Rectangle rect(l, w);
    rect.displayArea();
    
    return 0;
}
```

**Output:**
```
Enter length and width: 12 8
Rectangle created with length 12 and width 8
Area of rectangle = 96 square units
```

---

## Assignment 8

### 1. WAP in C++ to calculate the value of 2 book objects using parameterized constructor

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Book {
private:
    string title;
    float price;
    int pages;
    
public:
    // Parameterized constructor
    Book(string t, float p, int pg) {
        title = t;
        price = p;
        pages = pg;
    }
    
    float calculateValue() {
        // Value = price * (pages/100)
        return price * (pages / 100.0);
    }
    
    void displayDetails() {
        cout << "Title: " << title << endl;
        cout << "Price:" << price << endl;
        cout << "Pages: " << pages << endl;
        cout << "Calculated Value:" << calculateValue() << endl;
        cout << "------------------------" << endl;
    }
};

int main() {
    Book book1("C++ Programming", 450, 600);
    Book book2("Data Structures", 550, 800);
    
    cout << "--- Book Details ---" << endl;
    book1.displayDetails();
    book2.displayDetails();
    
    return 0;
}
```

**Output:**
```
--- Book Details ---
Title: C++ Programming
Price: 450
Pages: 600
Calculated Value: 2700
------------------------
Title: Data Structures
Price: 550
Pages: 800
Calculated Value: 4400
------------------------
```
---
### 2. WAP in C++ to create multiple Book Objects and display the number of objects created using a static member.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Book {
private:
    string title;
    float price;
    static int objectCount;
    
public:
    // Parameterized constructor
    Book(string t, float p) {
        title = t;
        price = p;
        objectCount++;
    }
    
    void displayDetails() {
        cout << "Title: " << title << endl;
        cout << "Price: $" << price << endl;
        cout << "------------------------" << endl;
    }
    
    static void displayObjectCount() {
        cout << "Total Book objects created: " << objectCount << endl;
    }
};

int Book::objectCount = 0;

int main() {
    cout << "Creating Book objects..." << endl << endl;
    
    Book b1("Harry Potter", 299);
    Book::displayObjectCount();
    
    Book b2("Lord of the Rings", 399);
    Book::displayObjectCount();
    
    Book b3("The Hobbit", 250);
    Book::displayObjectCount();
    
    cout << "\n--- Book Details ---" << endl;
    b1.displayDetails();
    b2.displayDetails();
    b3.displayDetails();
    
    cout << "\nFinal Count:" << endl;
    Book::displayObjectCount();
    
    return 0;
}
```

**Output:**
```
Creating Book objects...

Total Book objects created: 1
Total Book objects created: 2
Total Book objects created: 3

--- Book Details ---
Title: Harry Potter
Price: $299
------------------------
Title: Lord of the Rings
Price: $399
------------------------
Title: The Hobbit
Price: $250
------------------------

Final Count:
Total Book objects created: 3
```

---

### 3. WAP in C++ to demonstrate inline function.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    // Inline function to add two numbers
    inline int add(int a, int b) {
        return a + b;
    }
    
    // Inline function to multiply two numbers
    inline int multiply(int a, int b) {
        return a * b;
    }
    
    // Inline function to find square
    inline int square(int n) {
        return n * n;
    }
};

int main() {
    Calculator calc;
    int num1, num2;
    
    cout << "Enter two numbers: ";
    cin >> num1 >> num2;
    
    cout << "\n--- Results ---" << endl;
    cout << "Addition: " << calc.add(num1, num2) << endl;
    cout << "Multiplication: " << calc.multiply(num1, num2) << endl;
    cout << "Square of " << num1 << ": " << calc.square(num1) << endl;
    cout << "Square of " << num2 << ": " << calc.square(num2) << endl;
    
    return 0;
}
```

**Output:**
```
Enter two numbers: 5 8

--- Results ---
Addition: 13
Multiplication: 40
Square of 5: 25
Square of 8: 64
```

---

### 4.WAP in C++ to add 2 integers and 2 floats using function overloading.

**Source Code:**
```cpp
#include <iostream>
using namespace std;

class Adder {
public:
    // Function to add two integers
    int add(int a, int b) {
        cout << "Adding two integers..." << endl;
        return a + b;
    }
    
    // Overloaded function to add two floats
    float add(float a, float b) {
        cout << "Adding two floats..." << endl;
        return a + b;
    }
};

int main() {
    Adder adder;
    int int1, int2;
    float float1, float2;
    
    cout << "Enter two integers: ";
    cin >> int1 >> int2;
    
    cout << "Enter two floats: ";
    cin >> float1 >> float2;
    
    cout << "\n--- Results ---" << endl;
    int intSum = adder.add(int1, int2);
    cout << "Sum of integers: " << intSum << endl << endl;
    
    float floatSum = adder.add(float1, float2);
    cout << "Sum of floats: " << floatSum << endl;
    
    return 0;
}
```

**Output:**
```
Enter two integers: 10 20
Enter two floats: 5.5 3.2

--- Results ---
Adding two integers...
Sum of integers: 30

Adding two floats...
Sum of floats: 8.7
```

---

## Assignment 9

### 1. A company wants to maintain employee details using an object-oriented approach. Each employee has a name, ID, and basic salary. 
### Managers are a special type of employee who also receive an additional allowance. 
### Write a C++ program using **single inheritance** where the base class Employee stores general employee details, and the derived class Manager adds manager-specific data. The program should calculate and display the total salary of a manager.

**Source Code:**
```cpp
#include <iostream>
#include <string>
using namespace std;

// Base class
class Employee {
protected:
    string name;
    int id;
    float basicSalary;
    
public:
    void setEmployeeDetails() {
        cout << "Enter employee name: ";
        cin.ignore();
        getline(cin, name);
        
        cout << "Enter employee ID: ";
        cin >> id;
        
        cout << "Enter basic salary: ";
        cin >> basicSalary;
    }
    
    void displayEmployeeDetails() {
        cout << "\n--- Employee Details ---" << endl;
        cout << "Name: " << name << endl;
        cout << "ID: " << id << endl;
        cout << "Basic Salary: $" << basicSalary << endl;
    }
};

// Derived class
class Manager : public Employee {
private:
    float allowance;
    
public:
    void setManagerDetails() {
        setEmployeeDetails();
        cout << "Enter allowance: ";
        cin >> allowance;
    }
    
    float calculateTotalSalary() {
        return basicSalary + allowance;
    }
    
    void displayManagerDetails() {
        displayEmployeeDetails();
        cout << "Allowance: $" << allowance << endl;
        cout << "Total Salary: $" << calculateTotalSalary() << endl;
    }
};

int main() {
    Manager mgr;
    
    cout << "=== Manager Information System ===" << endl;
    mgr.setManagerDetails();
    mgr.displayManagerDetails();
    
    return 0;
}
```

**Output:**
```
=== Manager Information System ===
Enter employee name: John Smith
Enter employee ID: 1001
Enter basic salary: 50000
Enter allowance: 15000

--- Employee Details ---
Name: John Smith
ID: 1001
Basic Salary: $50000
Allowance: $15000
Total Salary: $65000
```

---

### 2. A transport company rents different types of vehicles. 
### The system needs to calculate the total rent for a customer based on vehicle type and number of days rented. 

### Design a **multilevel inheritance** program: 

### - The base class Vehicle holds general details (vehicle number and type). 
### - The derived class Car adds car-specific details like brand and daily rent rate. 
### - The next derived class Customer stores customer details and calculates total rent.

**Source Code:**
```cpp
#include <iostream>
#include <string>
using namespace std;

class Vehicle {
protected:
    string vehicleNumber;
    string vehicleType;
    
public:
    void setVehicleDetails() {
        cout << "Enter vehicle number: ";
        cin >> vehicleNumber;
        
        cout << "Enter vehicle type: ";
        cin >> vehicleType;
    }
    
    void displayVehicleDetails() {
        cout << "\n--- Rental Details ---" << endl;
        cout << "Vehicle Number: " << vehicleNumber << endl;
        cout << "Vehicle Type: " << vehicleType << endl;
    }
};

class Car : public Vehicle {
protected:
    string brand;
    float dailyRentRate;
    
public:
    void setCarDetails() {
        setVehicleDetails();
        
        cout << "Enter car brand: ";
        cin >> brand;
        
        cout << "Enter daily rent rate: $";
        cin >> dailyRentRate;
    }
    
    void displayCarDetails() {
        displayVehicleDetails();
        cout << "Brand: " << brand << endl;
        cout << "Daily Rent Rate: $" << dailyRentRate << endl;
    }
    
    float getDailyRate() {
        return dailyRentRate;
    }
};


class Customer : public Car {
private:
    string customerName;
    int daysRented;
    
public:
    void setCustomerDetails() {
        setCarDetails();
        
        cout << "Enter customer name: ";
        cin.ignore();
        getline(cin, customerName);
        
        cout << "Enter number of days rented: ";
        cin >> daysRented;
    }
    
    float calculateTotalRent() {
        return getDailyRate() * daysRented;
    }
    
    void displayRentalSummary() {
        displayCarDetails();
        cout << "Customer Name: " << customerName << endl;
        cout << "Days Rented: " << daysRented << endl;
        cout << "Total Rent: $" << calculateTotalRent() << endl;
    }
};

int main() {
    Customer c;
    
    cout << "=== Vehicle Rental System ===" << endl;
    c.setCustomerDetails();
    c.displayRentalSummary();
    
    return 0;
}
```

**Output:**
```
=== Vehicle Rental System ===
Enter vehicle number: MH12AB1234
Enter vehicle type: SUV
Enter car brand: Toyota
Enter daily rent rate: $80
Enter customer name: Alice Johnson
Enter number of days rented: 5

--- Rental Details ---
Vehicle Number: MH12AB1234
Vehicle Type: SUV
Brand: Toyota
Daily Rent Rate: $80
Customer Name: Alice Johnson
Days Rented: 5
Total Rent: $400
```

---

## Assignment 10

### 1. An e-commerce company accepts multiple payment methods such as **Credit Card** and **PayPal**. 
### Each payment method processes the transaction differently.
### You need to design a system that uses **runtime polymorphism** (virtual functions) to process payments dynamically depending on the payment type selected.


**Source Code:**
```cpp
#include <iostream>
#include <string>
using namespace std;

// Base class
class Payment {
protected:
    float amount;
    
public:
    Payment(float amt) {
        amount = amt;
    }
    
    // Virtual function for runtime polymorphism
    virtual void processPayment() {
        cout << "Processing payment of $" << amount << endl;
    }
    
    virtual void displayDetails() {
        cout << "Payment Amount: $" << amount << endl;
    }
    
    virtual ~Payment() {}
};

// Derived class for Credit Card
class CreditCard : public Payment {
private:
    string cardNumber;
    string cardHolder;
    
public:
    CreditCard(float amt, string cardNum, string holder) : Payment(amt) {
        cardNumber = cardNum;
        cardHolder = holder;
    }
    
    void processPayment() override {
        cout << "\n=== Credit Card Payment ===" << endl;
        cout << "Processing credit card payment..." << endl;
        cout << "Verifying card details..." << endl;
        cout << "Payment of " << amount << " successful!" << endl;
    }
    
    void displayDetails() override {
        cout << "Card Holder: " << cardHolder << endl;
        cout << "Card Number: ****" << cardNumber.substr(cardNumber.length() - 4) << endl;
        cout << "Amount: " << amount << endl;
    }
};

// Derived class for PayPal
class PayPal : public Payment {
private:
    string email;
    
public:
    PayPal(float amt, string mail) : Payment(amt) {
        email = mail;
    }
    
    void processPayment() override {
        cout << "\n=== PayPal Payment ===" << endl;
        cout << "Processing PayPal payment..." << endl;
        cout << "Connecting to PayPal account..." << endl;
        cout << "Payment of " << amount << " successful!" << endl;
    }
    
    void displayDetails() override {
        cout << "PayPal Email: " << email << endl;
        cout << "Amount: " << amount << endl;
    }
};

int main() {
    Payment *payment;
    int choice;
    float amount;
    
    cout << "=== E-Commerce Payment System ===" << endl;
    cout << "Enter payment amount: $";
    cin >> amount;
    
    cout << "\nSelect Payment Method:" << endl;
    cout << "1. Credit Card" << endl;
    cout << "2. PayPal" << endl;
    cout << "Enter choice: ";
    cin >> choice;
    
    if (choice == 1) {
        string cardNum, holder;
        cout << "Enter card number: ";
        cin >> cardNum;
        cout << "Enter card holder name: ";
        cin.ignore();
        getline(cin, holder);
        
        payment = new CreditCard(amount, cardNum, holder);
    } else if (choice == 2) {
        string email;
        cout << "Enter PayPal email: ";
        cin >> email;
        
        payment = new PayPal(amount, email);
    } else {
        cout << "Invalid choice!" << endl;
        return 1;
    }
    
    payment->displayDetails();
    payment->processPayment();
    
    delete payment;
    
    return 0;
}
```

**Output:**
```
=== E-Commerce Payment System ===
Enter payment amount: 150

Select Payment Method:
1. Credit Card
2. PayPal
Enter choice: 1
Enter card number: 1234567812345678
Enter card holder name: John Doe
Card Holder: John Doe
Card Number: ****5678
Amount: 150

=== Credit Card Payment ===
Processing credit card payment...
Verifying card details...
Payment of 150 successful!
```

---

### 2. A company evaluates its employees based on their job type:
### • Developer → evaluated on number of projects completed.
### • Manager → evaluated on number of teams handled.
### The company wants a flexible evaluation system using virtual functions, allowing different evaluation criteria for each employee type.

**Source Code:**
```cpp
#include <iostream>
#include <string>
using namespace std;

// Base class
class Employee {
protected:
    string name;
    int id;
    
public:
    Employee(string n, int empId) {
        name = n;
        id = empId;
    }
    
    // Virtual function for evaluation
    virtual void evaluate() {
        cout << "Evaluating employee..." << endl;
    }
    
    virtual void displayDetails() {
        cout << "Employee Name: " << name << endl;
        cout << "Employee ID: " << id << endl;
    }
    
    virtual ~Employee() {}
};

// Derived class for Developer
class Developer : public Employee {
private:
    int projectsCompleted;
    
public:
    Developer(string n, int empId, int projects) : Employee(n, empId) {
        projectsCompleted = projects;
    }
    
    void evaluate() override {
        cout << "\n=== Developer Evaluation ===" << endl;
        displayDetails();
        cout << "Projects Completed: " << projectsCompleted << endl;
        
        if (projectsCompleted >= 10) {
            cout << "Performance: Excellent" << endl;
            cout << "Rating: 5/5" << endl;
        } else if (projectsCompleted >= 7) {
            cout << "Performance: Very Good" << endl;
            cout << "Rating: 4/5" << endl;
        } else if (projectsCompleted >= 5) {
            cout << "Performance: Good" << endl;
            cout << "Rating: 3/5" << endl;
        } else {
            cout << "Performance: Needs Improvement" << endl;
            cout << "Rating: 2/5" << endl;
        }
    }
};

// Derived class for Manager
class Manager : public Employee {
private:
    int teamsHandled;
    
public:
    Manager(string n, int empId, int teams) : Employee(n, empId) {
        teamsHandled = teams;
    }
    
    void evaluate() override {
        cout << "\n=== Manager Evaluation ===" << endl;
        displayDetails();
        cout << "Teams Handled: " << teamsHandled << endl;
        
        if (teamsHandled >= 5) {
            cout << "Performance: Excellent" << endl;
            cout << "Rating: 5/5" << endl;
            cout << "Leadership: Outstanding" << endl;
        } else if (teamsHandled >= 3) {
            cout << "Performance: Very Good" << endl;
            cout << "Rating: 4/5" << endl;
            cout << "Leadership: Strong" << endl;
        } else if (teamsHandled >= 2) {
            cout << "Performance: Good" << endl;
            cout << "Rating: 3/5" << endl;
            cout << "Leadership: Satisfactory" << endl;
        } else {
            cout << "Performance: Needs Improvement" << endl;
            cout << "Rating: 2/5" << endl;
            cout << "Leadership: Developing" << endl;
        }
    }
};

int main() {
    Employee *emp;
    int choice;
    string name;
    int id;
    
    cout << "=== Employee Evaluation System ===" << endl;
    cout << "Select Employee Type:" << endl;
    cout << "1. Developer" << endl;
    cout << "2. Manager" << endl;
    cout << "Enter choice: ";
    cin >> choice;
    
    cout << "Enter employee name: ";
    cin.ignore();
    getline(cin, name);
    
    cout << "Enter employee ID: ";
    cin >> id;
    
    if (choice == 1) {
        int projects;
        cout << "Enter number of projects completed: ";
        cin >> projects;
        
        emp = new Developer(name, id, projects);
    } else if (choice == 2) {
        int teams;
        cout << "Enter number of teams handled: ";
        cin >> teams;
        
        emp = new Manager(name, id, teams);
    } else {
        cout << "Invalid choice!" << endl;
        return 1;
    }
    
    // Runtime polymorphism in action
    emp->evaluate();
    
    delete emp;
    
    return 0;
}
```

**Output (Developer):**
```
=== Employee Evaluation System ===
Select Employee Type:
1. Developer
2. Manager
Enter choice: 1
Enter employee name: Sarah Williams
Enter employee ID: 2501
Enter number of projects completed: 12

=== Developer Evaluation ===
Employee Name: Sarah Williams
Employee ID: 2501
Projects Completed: 12
Performance: Excellent
Rating: 5/5
```

**Output (Manager):**
```
=== Employee Evaluation System ===
Select Employee Type:
1. Developer
2. Manager
Enter choice: 2
Enter employee name: Michael Brown
Enter employee ID: 3102
Enter number of teams handled: 4

=== Manager Evaluation ===
Employee Name: Michael Brown
Employee ID: 3102
Teams Handled: 4
Performance: Very Good
Rating: 4/5
Leadership: Strong
```
