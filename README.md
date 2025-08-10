# If, Else-If, and Else in C Language

## Introduction

Decision-making is an essential concept in programming. Just as humans make choices every day based on certain situations, a program also needs to make decisions to perform specific actions.

In C programming, decision-making is done using:

- **`if`** — Runs a block of code only if a given condition is true.
- **`else`** — Runs a block of code if the `if` condition is false.
- **`else-if`** — Checks another condition if the previous `if` (or `else-if`) condition is false.

### Why It’s Important
Without decision-making statements, a program would simply execute instructions sequentially without adapting to different scenarios. Using **if**, **else-if**, and **else** allows programs to react differently depending on input or system states.

**Real-life parallel:**  
Imagine a traffic light:
- **If** it’s green → You drive.
- **Else if** it’s yellow → You slow down.
- **Else** (must be red) → You stop.

This guide contains runnable C examples, with **detailed explanations** (what it does, step-by-step logic, execution trace, sample I/O, edge cases, suggested improvements, complexity, ASCII flowchart, and a short real-world analogy) for each program.

---

## Syntax & Real-world Analogy (Quick Reference)

### `if`
```c
if (condition) {
    // executed if condition is true (non-zero)
}
```c
Analogy: If it is raining, take an umbrella.

### `if ... else`
```c
if (condition) {
    // if true
} else {
    // if false
}
```c
Analogy: If you pass the exam → Celebrate. Else → Study harder.

### `if ... else-if ... else`
```c
if (condition1) {
    // cond1 true
} else if (condition2) {
    // cond2 true
} else {
    // none true
}
```c
Analogy: If sunny → park; else if cloudy → café; else → stay home.

Important: checks run top-to-bottom; first true branch executes and the rest are skipped.

---

# Examples


## Example 1 — Check if a Number is Positive (single `if`)

```c
#include <stdio.h>

int main() {
    int num;
    printf("Enter a number: ");
    if (scanf("%d", &num) != 1) {
        printf("Invalid input. Please enter an integer.\n");
        return 1;
    }

    if (num > 0) {
        printf("The number is positive.\n");
    }

    return 0;
}
```c

**What it does:** Prints a message only if the input number is greater than 0.

**Step-by-step:**
1. Prompt the user and read an integer into `num`.
2. Evaluate `num > 0`.
3. If true, run the `printf` inside the `if` block.
4. Otherwise skip the `if` block and exit.

**Execution trace (input = 5):**
- `scanf` reads 5 → `num = 5`.
- `if (5 > 0)` is true → prints `"The number is positive."`.

**Sample I/O:**
- Input: `5` → Output: `The number is positive.`
- Input: `0` → Output: *(no output from the program)*
- Input: `-2` → Output: *(no output)*


**Flowchart:**
```c
Start
  |
[Input num]
  |
(num > 0?) -Yes-> Print "Positive" -> End
           -No-> End
```c

---

## Example 2 — Positive or Negative (`if ... else`)

```c
#include <stdio.h>

int main() {
    int num;
    printf("Enter a number: ");
    if (scanf("%d", &num) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (num >= 0) {
        printf("The number is positive.\n");
    } else {
        printf("The number is negative.\n");
    }

    return 0;
}
```c

**What it does:** Classifies the number as "positive" if `num >= 0`; otherwise "negative". Note: this treats `0` as positive.

**Step-by-step:**
1. Read `num`.
2. Check `num >= 0`.
3. If true, print positive; else print negative.

**Execution trace (input = -3):**
- `scanf` reads -3 → `num = -3`.
- `-3 >= 0` false → prints `"The number is negative."`.

**Sample I/O:**
- Input `10` → `The number is positive.`
- Input `0` → `The number is positive.`
- Input `-1` → `The number is negative.`


**Flowchart:**
```c
Start -> Input num
  |
(num >= 0?) Yes -> Print "Positive"
             No  -> Print "Negative"
```c

---

## Example 3 — Positive / Negative / Zero (`if` → `else if` → `else`)

```c
#include <stdio.h>

int main() {
    int num;
    printf("Enter a number: ");
    if (scanf("%d", &num) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (num > 0) {
        printf("Positive number.\n");
    } else if (num < 0) {
        printf("Negative number.\n");
    } else {
        printf("Zero.\n");
    }
    return 0;
}
```c

**What it does:** Distinguishes all three mutually exclusive cases: positive, negative, or zero.

**Step-by-step:**
1. Read `num`.
2. Check `num > 0`; if true, print "Positive" and skip other checks.
3. Else, check `num < 0`; if true, print "Negative".
4. Else, print "Zero" (this covers `num == 0`).

**Execution trace (input = 0):**
- `scanf` reads 0 -> `num = 0`.
- `num > 0` false -> `num < 0` false -> `else` prints `"Zero."`.

**Sample I/O:**
- `25` → `Positive number.`
- `-9` → `Negative number.`
- `0` → `Zero.`


**Flowchart:**
```c
Start -> Input num
  |
(num > 0?) Y -> Positive -> End
       N -> (num < 0?) Y -> Negative -> End
                   N -> Zero -> End
```c

---

## Example 4 — Even or Odd (modulo `%`)

```c
#include <stdio.h>

int main() {
    int num;
    printf("Enter an integer: ");
    if (scanf("%d", &num) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (num % 2 == 0) {
        printf("%d is Even.\n", num);
    } else {
        printf("%d is Odd.\n", num);
    }
    return 0;
}
```c

**What it does:** Uses `num % 2 == 0` to detect even numbers; else odd.

**Step-by-step:**
1. Read `num`.
2. Compute `num % 2` (remainder of division by 2).
3. If remainder is 0, it's even; otherwise odd.

**Execution trace (input = -4):**
- `-4 % 2` is `0` in C -> prints `-4 is Even.`

**Sample I/O:**
- `4` → `4 is Even.`
- `7` → `7 is Odd.`
- `0` → `0 is Even.`

**Flowchart:**
```c
Start -> Input num
  |
(num % 2 == 0?) Y -> Print "Even"
                N -> Print "Odd"
```c

---

## Example 5 — Student Grade Calculator (multi `else if` ladder)

```c
#include <stdio.h>

int main() {
    int marks;
    printf("Enter marks (0-100): ");
    if (scanf("%d", &marks) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (marks < 0 || marks > 100) {
        printf("Invalid marks. Enter 0-100.\n");
    } else if (marks >= 90) {
        printf("Grade: A+\n");
    } else if (marks >= 75) {
        printf("Grade: A\n");
    } else if (marks >= 60) {
        printf("Grade: B\n");
    } else if (marks >= 40) {
        printf("Grade: C\n");
    } else {
        printf("Fail\n");
    }

    return 0;
}
```c

**What it does:** Assigns grades based on descending thresholds; higher grades checked first so they match correctly.

**Step-by-step:**
1. Read `marks` and validate range.
2. If invalid range -> print error.
3. Else check `marks >= 90` -> A+.
4. Else check `marks >= 75` -> A.
5. Else check `marks >= 60` -> B.
6. Else check `marks >= 40` -> C.
7. Else -> Fail.

**Execution trace (marks = 78):**
- `78 >= 90` false -> `78 >= 75` true -> prints `Grade: A` and exits ladder.

**Sample I/O:**
- `92` → `Grade: A+`
- `30` → `Fail`
- `150` → `Invalid marks.`

**Flowchart (compact):**
```c
Start -> Input marks
  |-> invalid? -> print invalid
  |-> marks>=90? -> A+
  |-> marks>=75? -> A
  |-> marks>=60? -> B
  |-> marks>=40? -> C
  |-> else -> Fail
```c

---

## Example 6 — Leap Year Checker (compound boolean logic)

```c
#include <stdio.h>

int main() {
    int year;
    printf("Enter a year: ");
    if (scanf("%d", &year) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0)) {
        printf("%d is a Leap Year.\n", year);
    } else {
        printf("%d is not a Leap Year.\n", year);
    }

    return 0;
}
```c

**What it does:** Implements the Gregorian leap year rule:
- Year divisible by 400 → leap.
- Else if divisible by 4 and not by 100 → leap.
- Else → not leap.

**Step-by-step:**
1. Read `year`.
2. Check `year % 400 == 0`; if true, leap.
3. Else check `year % 4 == 0 && year % 100 != 0`; if true, leap.
4. Else not leap.

**Execution trace (year = 1900):**
- `1900 % 400` != 0 -> false.
- `1900 % 4 == 0` true but `1900 % 100 != 0` false -> combined false.
- Prints `1900 is not a Leap Year.`

**Sample I/O:**
- `2000` → `Leap Year.`
- `1900` → `Not a Leap Year.`
- `2012` → `Leap Year.`


**Flowchart:**
```c
Start -> Input year
  -> year%400==0? -> Leap
  -> year%4==0? -> year%100!=0? -> Leap : Not Leap
```c

---

## Example 7 — Age Group Classification

```c
#include <stdio.h>

int main() {
    int age;
    printf("Enter age: ");
    if (scanf("%d", &age) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (age < 0) {
        printf("Invalid age.\n");
    } else if (age < 13) {
        printf("Child\n");
    } else if (age < 20) {
        printf("Teenager\n");
    } else if (age < 60) {
        printf("Adult\n");
    } else {
        printf("Senior Citizen\n");
    }

    return 0;
}
```c

**What it does:** Classifies age into buckets using `<` checks that avoid overlap.

**Step-by-step:**
1. Read `age` and validate non-negativity.
2. If `age < 13` -> Child.
3. Else if `age < 20` -> Teenager.
4. Else if `age < 60` -> Adult.
5. Else -> Senior Citizen.

**Execution trace (age = 13):**
- `age < 13` false -> `age < 20` true -> prints `Teenager`.

**Sample I/O:**
- `10` → `Child`
- `16` → `Teenager`
- `35` → `Adult`
- `70` → `Senior Citizen`

**Flowchart:** simple ladder similar to earlier examples.

---

## Example 8 — Simple ATM Withdrawal

```c
#include <stdio.h>

int main() {
    int balance = 5000;
    int withdraw;
    printf("Enter amount to withdraw: ");
    if (scanf("%d", &withdraw) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (withdraw <= 0) {
        printf("Enter a positive amount.\n");
    } else if (withdraw <= balance) {
        balance -= withdraw;
        printf("Withdrawal successful. Remaining balance: %d\n", balance);
    } else {
        printf("Insufficient balance.\n");
    }

    return 0;
}
```c

**What it does:** Checks validity and sufficiency of withdrawal, updates balance if allowed.

**Step-by-step:**
1. Initialize `balance` to 5000.
2. Read `withdraw` amount.
3. If `withdraw <= 0` -> invalid amount.
4. Else if `withdraw <= balance` -> subtract and print remaining balance.
5. Else -> print insufficient funds.

**Execution trace (withdraw = 1000):**
- `1000 <= 0` false -> `1000 <= 5000` true -> `balance = 4000` -> print success.

**Sample I/O:**
- `1000` → `Withdrawal successful. Remaining balance: 4000`
- `6000` → `Insufficient balance.`

**Edge cases & notes:**
- Negative withdrawals rejected.
- Consider ATM cash increment constraints (e.g., multiples of 100) in enhancements.
- For real banking use decimal-based types (cents) and persistent storage.

---

## Example 9 — Traffic Signal Simulation (string compare)

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char signal[16];
    printf("Enter signal color (red/yellow/green): ");
    if (scanf("%15s", signal) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    // convert to lowercase for case-insensitive match
    for (int i = 0; signal[i]; ++i) signal[i] = tolower((unsigned char)signal[i]);

    if (strcmp(signal, "red") == 0) {
        printf("Stop!\n");
    } else if (strcmp(signal, "yellow") == 0) {
        printf("Get Ready!\n");
    } else if (strcmp(signal, "green") == 0) {
        printf("Go!\n");
    } else {
        printf("Invalid signal color.\n");
    }

    return 0;
}
```c

**What it does:** Compares the (lowercased) input string to expected colors and prints the correct action.

**Step-by-step:**
1. Read a word into `signal` (up to 15 chars).
2. Convert to lowercase for case-insensitive matching.
3. Compare with `"red"`, `"yellow"`, `"green"` sequentially using `strcmp`.
4. Print corresponding message or invalid notice.

**Execution trace (input = "Green")**
- `signal` becomes `"Green"`, then lowercased to `"green"`.
- `strcmp(signal,"red") != 0`, `strcmp(...,"yellow") != 0`, `strcmp(...,"green") == 0` -> print `"Go!"`.

**Sample I/O:**
- `red` → `Stop!`
- `YELLOW` → `Get Ready!`
- `blue` → `Invalid signal color.`

**Flowchart:** classic multi-branch matching.

---

## Example 10 — Largest of Three Numbers

```c
#include <stdio.h>

int main() {
    int a, b, c;
    printf("Enter three numbers: ");
    if (scanf("%d %d %d", &a, &b, &c) != 3) {
        printf("Invalid input.\n");
        return 1;
    }

    if (a >= b && a >= c) {
        printf("%d is the largest.\n", a);
    } else if (b >= a && b >= c) {
        printf("%d is the largest.\n", b);
    } else {
        printf("%d is the largest.\n", c);
    }
    return 0;
}
```c

**What it does:** Compares pairs to determine the greatest. Using `>=` ensures correct behavior when numbers are equal (ties are resolved by reporting the first variable that satisfies the condition).

**Step-by-step:**
1. Read three integers `a`, `b`, `c` (validate input count).
2. Check `a >= b && a >= c`. If true → `a` is largest (or tied for largest).
3. Else check `b >= a && b >= c`. If true → `b` is largest.
4. Else → `c` is largest.

**Execution trace (input: 3 9 5):**
- `a=3, b=9, c=5`.
- `a >= b && a >= c` → false.
- `b >= a && b >= c` → true → prints `9 is the largest.`

**Execution trace (input: 7 7 2):**
- `a=7, b=7, c=2`.
- `a >= b && a >= c` → `(7 >= 7 && 7 >= 2)` → true → prints `7 is the largest.` (reports `a` for the tie).

**Sample I/O:**
- `3 9 5` → `9 is the largest.`
- `7 7 2` → `7 is the largest.`
- `5 7 7` → `7 is the largest.` (prints `b` because `a>=b` false, then `b>=a && b>=c` true)

**Flowchart:**
```c
Start -> Input a,b,c
  -> (a >= b && a >= c?) Yes -> Print a -> End
  -> (b >= a && b >= c?) Yes -> Print b -> End
  -> Else -> Print c -> End
```c

---

## Example 11 — Login System (simple credentials check)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char username[32], password[32];
    printf("Enter username: ");
    if (scanf("%31s", username) != 1) return 1;
    printf("Enter password: ");
    if (scanf("%31s", password) != 1) return 1;

    if (strcmp(username, "admin") == 0 && strcmp(password, "1234") == 0) {
        printf("Login Successful!\n");
    } else {
        printf("Invalid Credentials.\n");
    }
    return 0;
}
```c

**What it does:** Verifies both username and password match expected strings; prints success only if both match.

**Step-by-step:**
1. Read `username` and `password` (bounded).
2. `strcmp` returns 0 when strings equal.
3. Use logical `&&` to require both matches.

**Sample I/O:**
- `admin` + `1234` → `Login Successful!`
- any other combination → `Invalid Credentials.`

**Flowchart:** straightforward AND-check.

---

## Example 12 — Electricity Bill Calculator (tiered rates)

```c
#include <stdio.h>

int main() {
    int units;
    double bill;
    printf("Enter electricity units: ");
    if (scanf("%d", &units) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (units < 0) {
        printf("Invalid units.\n");
        return 1;
    }

    if (units <= 100) {
        bill = units * 1.5;
    } else if (units <= 200) {
        bill = 100 * 1.5 + (units - 100) * 2.5;
    } else {
        bill = 100 * 1.5 + 100 * 2.5 + (units - 200) * 3.5;
    }

    printf("Total Bill: ₹%.2f\n", bill);
    return 0;
}
```c

**What it does:** Applies tiered pricing for electricity units:
- First 100 units at ₹1.5/unit.
- Next 100 units (101–200) at ₹2.5/unit.
- Remaining units above 200 at ₹3.5/unit.

**Step-by-step (units = 250):**
1. `units <= 100?` No.
2. `units <= 200?` No.
3. Else: `bill = 100*1.5 + 100*2.5 + (250-200)*3.5` → `150 + 250 + 175 = 575.00`.

**Sample I/O:**
- `80` → `Total Bill: ₹120.00`
- `150` → `Total Bill: ₹275.00`
- `250` → `Total Bill: ₹575.00`

**Flowchart:** tiered checks and arithmetic calculation.

---
