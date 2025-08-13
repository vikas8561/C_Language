

---


Definition of Loop in Programming (C Language Context)
A loop is a control structure in programming that allows a block of code to be executed repeatedly as long as a certain condition is true.
It helps in avoiding repetitive code and makes programs shorter, cleaner, and easier to maintain.

In C language, common types of loops are:

for loop – Used when the number of repetitions is known.

while loop – Used when repetitions depend on a condition.

do-while loop – Similar to while, but executes at least once before checking the condition.

Key Points:
Condition-controlled → Repeats until the condition becomes false.

Entry-controlled → Condition checked before execution (for, while).

Exit-controlled → Condition checked after execution (do-while).

Real-World Example
Imagine you have to serve tea to 50 guests at a wedding.
You wouldn’t say:

"Boil water, add tea leaves, pour into a cup" … and then write those steps 50 times.

Instead, you’d think:

Start with guest 1

Serve tea

Move to next guest

Repeat until all guests have tea

That’s a loop in real life — repeat the same task until a condition is met (guest_number <= 50).



Definition of for Loop
The for loop in C is an entry-controlled loop — this means the condition is checked before each iteration, and the loop executes only if the condition is true.
It is generally used when the number of repetitions (iterations) is known in advance.

Syntax
c
Copy
Edit
for (initialization; condition; update) {
    // Code to be repeated
}
Parts of a for Loop
Initialization

Runs only once at the start of the loop.

Usually sets a counter variable.

Example: int i = 1;

Condition

Checked before every iteration.

If it’s true → Loop runs.

If it’s false → Loop stops.

Example: i <= 10

Update (Increment/Decrement)

Runs after each iteration.

Changes the counter variable so the loop eventually stops.

Example: i++ or i += 2

Flow of Execution
Initialization → set starting value

Check Condition → if false → exit loop

Execute Loop Body → run the statements

Update Counter → increment/decrement value

Repeat from step 2

Example — Printing Numbers 1 to 5
c
Copy
Edit
#include <stdio.h>

int main() {
    int i;
    for (i = 1; i <= 5; i++) {  
        printf("%d
", i);
    }
    return 0;
}
Explanation Step-by-Step:

Initialization: i = 1 (runs once)

Condition: i <= 5 (check each time)

Loop Body: prints i

Update: i++ → increases i by 1

Repeats until i becomes 6 (condition fails)

Real-World Analogy
Imagine you have 10 chairs to arrange in a hall.
You can think like this:

Start from chair #1

Arrange the chair

Move to the next chair

Repeat until chair #10 is arranged

This matches a for loop: start → check → do work → move to next → repeat.

Types of for Loops
Incrementing Loop

c
Copy
Edit
for (int i = 1; i <= 10; i++) { ... }
Decrementing Loop

c
Copy
Edit
for (int i = 10; i >= 1; i--) { ... }
Loop with Step Size

c
Copy
Edit
for (int i = 0; i <= 20; i += 2) { ... }
Infinite Loop

c
Copy
Edit
for (;;) { ... }  // No condition, runs forever until break
Advantages
Compact — all control elements in one line.

Easy to understand for counting and fixed iteration tasks.

Limitations
Not ideal when you don’t know in advance how many times the loop will run (in such cases, while or do-while is better).


Example 1 — Print Numbers 1 to 5
c
Copy
Edit
#include <stdio.h> // Standard input-output header file

int main() {
    int i; // Declare loop counter variable

    // for loop starts
    // Initialization: i = 1 → loop starts from 1
    // Condition: i <= 5 → loop will run as long as i is less than or equal to 5
    // Update: i++ → increment i by 1 after each iteration
    for (i = 1; i <= 5; i++) {
        printf("%d
", i); // Print current value of i
    }

    return 0; // End of program
}
Sample Output:

Copy
Edit
1
2
3
4
5
Example 2 — Print Even Numbers from 2 to 10
c
Copy
Edit
#include <stdio.h>

int main() {
    int i; // Loop counter variable

    // Start at 2, end at 10, step size 2
    for (i = 2; i <= 10; i += 2) {
        printf("%d
", i); // Will print only even numbers
    }

    return 0;
}
Sample Output:

Copy
Edit
2
4
6
8
10
Example 3 — Countdown from 10 to 1
c
Copy
Edit
#include <stdio.h>

int main() {
    int i; // Counter variable

    // Start from 10, run until i >= 1, decrement i each time
    for (i = 10; i >= 1; i--) {
        printf("%d
", i); // Prints countdown
    }

    return 0;
}
Sample Output:

Copy
Edit
10
9
8
7
6
5
4
3
2
1
Example 4 — Sum of First 10 Natural Numbers
c
Copy
Edit
#include <stdio.h>

int main() {
    int i, sum = 0; // sum initialized to 0

    // Loop from 1 to 10
    for (i = 1; i <= 10; i++) {
        sum += i; // Add current number to sum
    }

    printf("Sum = %d
", sum); // Display total sum

    return 0;
}
Sample Output:

ini
Copy
Edit
Sum = 55
Example 5 — Multiplication Table of 5
c
Copy
Edit
#include <stdio.h>

int main() {
    int i; // Counter variable

    // Loop from 1 to 10
    for (i = 1; i <= 10; i++) {
        printf("5 x %d = %d
", i, 5 * i); // Multiplication table
    }

    return 0;
}
Sample Output:

Copy
Edit
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
Example 6 — Calculate Factorial of a Number
c
Copy
Edit
#include <stdio.h>

int main() {
    int n, i;
    long long fact = 1; // factorial can be large, so use long long

    printf("Enter a number: "); // Ask for input
    scanf("%d", &n); // Read number from user

    // Multiply numbers from 1 to n
    for (i = 1; i <= n; i++) {
        fact *= i; // fact = fact * i
    }

    printf("Factorial of %d = %lld
", n, fact); // Display result

    return 0;
}
Sample Output (n = 5):

mathematica
Copy
Edit
Enter a number: 5
Factorial of 5 = 120
Example 7 — Print ASCII Values of A–Z
c
Copy
Edit
#include <stdio.h>

int main() {
    char ch; // Character variable

    // Loop from 'A' to 'Z'
    for (ch = 'A'; ch <= 'Z'; ch++) {
        printf("%c -> %d
", ch, ch); // Print character and ASCII value
    }

    return 0;
}
Sample Output:

rust
Copy
Edit
A -> 65
B -> 66
C -> 67
D -> 68
E -> 69
...
Z -> 90


1. break Statement
Definition
The break statement in C is used to immediately terminate the execution of a loop (for, while, do-while) or a switch statement, regardless of the loop’s condition.
Once break is executed, control is transferred to the first statement after the loop/switch.

Syntax
c
Copy
Edit
break;
Key Points
Works inside loops and switch blocks only.

Immediately exits the nearest enclosing loop or switch.

Commonly used to stop loop execution early when a certain condition is met.

Flow Diagram for break
mathematica
Copy
Edit
Start Loop → Check Condition → Run Statements → If break executed → Exit Loop
Example 1 — Stop Loop when Number is Found
c
Copy
Edit
#include <stdio.h>

int main() {
    int i;
    for (i = 1; i <= 10; i++) {
        if (i == 5) {   // If i equals 5
            break;      // Exit the loop immediately
        }
        printf("%d
", i);
    }
    return 0;
}
Output:

Copy
Edit
1
2
3
4
(Stops at 5 and does not print further numbers.)

Real-Life Analogy for break
Imagine you are searching for your lost pen in drawers:

You start checking drawer 1, then drawer 2, then drawer 3...

Once you find the pen, you stop searching immediately without checking the remaining drawers.
That’s how break works.

2. continue Statement
Definition
The continue statement in C is used to skip the current iteration of a loop and move to the next iteration without executing the remaining statements inside that iteration.

Syntax
c
Copy
Edit
continue;
Key Points
Only works inside loops (for, while, do-while).

Does not exit the loop; it just skips the rest of the code for that iteration.

Useful when you want to ignore specific cases during looping.

Flow Diagram for continue
vbnet
Copy
Edit
Start Loop → Check Condition → Run Statements → If continue executed → Skip remaining code in loop body → Go to next iteration
Example 2 — Skip Number 5
c
Copy
Edit
#include <stdio.h>

int main() {
    int i;
    for (i = 1; i <= 10; i++) {
        if (i == 5) {   // If i is 5
            continue;   // Skip printing 5 and go to next iteration
        }
        printf("%d
", i);
    }
    return 0;
}
Output:

Copy
Edit
1
2
3
4
6
7
8
9
10
(5 is skipped, but the loop continues.)

Real-Life Analogy for continue
Imagine you’re checking exam answer sheets:

If a sheet is blank, you skip it and move to the next sheet.
You don’t stop checking all sheets; you just ignore that one and continue.

Key Differences between break and continue
Feature	break	continue
Purpose	Exits the loop entirely	Skips current iteration and moves to next
Scope	Loops + switch cases	Loops only
Effect on Loop	Stops loop execution	Loop continues until condition fails
Execution after Statement	Goes to first statement after the loop	Goes to loop’s condition/update step



Switch Case in C
Definition
The switch statement in C is a multi-way decision-making control structure that allows a program to execute one block of code out of many possible blocks, based on the value of a single expression (usually a variable).

It is often used as a cleaner and more readable alternative to multiple if-else-if statements when you are comparing the same variable to many constant values.

Syntax
c
Copy
Edit
switch (expression) {
    case constant1:
        // Code block for constant1
        break;

    case constant2:
        // Code block for constant2
        break;

    ...

    default:
        // Code block if no cases match
}
Explanation of Each Part
switch (expression)

The expression is evaluated once.

Its result is compared with each case constant.

Expression must be of type int, char, enum, or short (floating-point values are not allowed).

case constant:

A constant value to compare against the expression.

If the value matches, the statements inside that case execute.

break;

Used to terminate the current case block.

If omitted, the execution will "fall through" to the next case.

default:

Executes if no matching case is found.

It’s optional, but recommended.

Flow of Execution
Evaluate the expression inside switch.

Compare it with each case value in order.

If a match is found → execute statements in that case until a break or end of switch is reached.

If no match → execute the default block (if present).

Example 1 — Basic Switch
c
Copy
Edit
#include <stdio.h>

int main() {
    int day;
    printf("Enter day number (1-3): ");
    scanf("%d", &day);

    switch (day) {
        case 1:
            printf("Monday
");
            break;
        case 2:
            printf("Tuesday
");
            break;
        case 3:
            printf("Wednesday
");
            break;
        default:
            printf("Invalid day
");
    }

    return 0;
}
Sample Output:

mathematica
Copy
Edit
Enter day number (1-3): 2
Tuesday
Real-Life Analogy
Think of a switchboard in a house:

If you flip switch 1, the fan turns on.

If you flip switch 2, the light turns on.

If you flip switch 3, the TV turns on.

If you press a switch that doesn’t exist, nothing happens (default case).

Key Rules for switch
The expression must be an integer type (char, short, int, long).

case values must be constant literals — no variables allowed.

break is important to prevent fall-through.

The default case is optional but good for handling unexpected inputs.

Example 2 — Without Break (Fall-Through Behavior)
c
Copy
Edit
#include <stdio.h>

int main() {
    int number = 2;

    switch (number) {
        case 1:
            printf("One
");
        case 2:
            printf("Two
");
        case 3:
            printf("Three
");
        default:
            printf("Other
");
    }

    return 0;
}
Output:

nginx
Copy
Edit
Two
Three
Other
💡 Reason: No break after case 2, so execution continues to all remaining cases.

Advantages of Switch
Cleaner and easier to read than long if-else-if chains.

Faster for multiple comparisons (compiler optimization possible).

Structured, avoids repeated if conditions.

Limitations
Works only for discrete values, not for ranges (e.g., you can’t check x > 10 directly).

Expression type must be integer-like.

case labels must be constant values (no variables).


Example 1 — Day of the Week
c
Copy
Edit
#include <stdio.h> // Standard Input/Output header

int main() {
    int day; // Variable to store day number
    
    printf("Enter day number (1-7): "); // Ask user for input
    scanf("%d", &day); // Read integer input
    
    // Switch statement to match day number
    switch (day) {
        case 1: // If day == 1
            printf("Monday
"); // Print Monday
            break; // Exit switch after printing
        case 2: // If day == 2
            printf("Tuesday
");
            break;
        case 3:
            printf("Wednesday
");
            break;
        case 4:
            printf("Thursday
");
            break;
        case 5:
            printf("Friday
");
            break;
        case 6:
            printf("Saturday
");
            break;
        case 7:
            printf("Sunday
");
            break;
        default: // If none of the above cases match
            printf("Invalid day number!
");
    }
    
    return 0; // End of program
}
Sample Output:

mathematica
Copy
Edit
Enter day number (1-7): 3
Wednesday
Example 2 — Simple Calculator
c
Copy
Edit
#include <stdio.h>

int main() {
    char op;       // Variable for operator (+, -, *, /)
    double num1, num2; // Variables for operands
    
    printf("Enter an operator (+, -, *, /): "); 
    scanf(" %c", &op); // Read operator (space before %c to ignore newline)
    
    printf("Enter two numbers: ");
    scanf("%lf %lf", &num1, &num2); // Read two floating-point numbers
    
    // Switch on the operator
    switch (op) {
        case '+': // If operator is +
            printf("Result: %.2lf
", num1 + num2);
            break;
        case '-': // If operator is -
            printf("Result: %.2lf
", num1 - num2);
            break;
        case '*': // If operator is *
            printf("Result: %.2lf
", num1 * num2);
            break;
        case '/': // If operator is /
            if (num2 != 0) // Check for divide-by-zero
                printf("Result: %.2lf
", num1 / num2);
            else
                printf("Error: Division by zero!
");
            break;
        default: // If operator doesn't match any case
            printf("Invalid operator!
");
    }
    
    return 0;
}
Sample Output:

vbnet
Copy
Edit
Enter an operator (+, -, *, /): *
Enter two numbers: 5 3
Result: 15.00
Example 3 — Grade Evaluation
c
Copy
Edit
#include <stdio.h>

int main() {
    char grade; // Variable to store grade
    
    printf("Enter your grade (A, B, C, D, F): ");
    scanf(" %c", &grade); // Read grade as character
    
    // Switch to check grade
    switch (grade) {
        case 'A': // If grade is A
            printf("Excellent!
");
            break;
        case 'B':
            printf("Well done!
");
            break;
        case 'C':
            printf("Good work!
");
            break;
        case 'D':
            printf("You passed.
");
            break;
        case 'F':
            printf("Better luck next time.
");
            break;
        default:
            printf("Invalid grade!
");
    }
    
    return 0;
}
Sample Output:

mathematica
Copy
Edit
Enter your grade (A, B, C, D, F): B
Well done!
Example 4 — Fall-Through Behavior (No Breaks)
c
Copy
Edit
#include <stdio.h>

int main() {
    int num = 2; // Set number to 2
    
    // Switch statement without break
    switch (num) {
        case 1:
            printf("One
"); // Will not run because num != 1
        case 2:
            printf("Two
"); // Runs because num == 2
        case 3:
            printf("Three
"); // Runs due to fall-through
        default:
            printf("Other
"); // Runs due to fall-through
    }
    
    return 0;
}
Sample Output:

nginx
Copy
Edit
Two
Three
Other
💡 Explanation:
Since there’s no break, once case 2 matches, all remaining cases execute sequentially.

Example 5 — Menu-Driven Program
c
Copy
Edit
#include <stdio.h>

int main() {
    int choice; // Variable for menu choice
    
    // Display menu
    printf("Menu:
");
    printf("1. Say Hello
");
    printf("2. Display Sum of 2 Numbers
");
    printf("3. Exit
");
    printf("Enter your choice: ");
    scanf("%d", &choice); // Read choice
    
    // Switch to handle menu selection
    switch (choice) {
        case 1:
            printf("Hello! How are you?
");
            break;
        case 2: {
            int a, b;
            printf("Enter two integers: ");
            scanf("%d %d", &a, &b);
            printf("Sum = %d
", a + b);
            break;
        }
        case 3:
            printf("Exiting program...
");
            break;
        default:
            printf("Invalid choice!
");
    }
    
    return 0;
}
Sample Output:

mathematica
Copy
Edit
Menu:
1. Say Hello
2. Display Sum of 2 Numbers
3. Exit
Enter your choice: 2
Enter two integers: 7 5
Sum = 12

---
