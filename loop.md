

---

## 1. Ternary Operator (`?:`)

### Theory
The **ternary operator** is a shorthand way of writing an `if-else` statement in one line.  
It is called "ternary" because it takes **three operands**:

```c
condition ? value_if_true : value_if_false;
```

- **If** the condition is true → it returns `value_if_true`
- **If** the condition is false → it returns `value_if_false`

**Real-world example:**  
Imagine you are deciding whether to take an umbrella:
- If it is raining → take the umbrella.
- If not → leave it at home.

**Syntax:**
```c
result = (condition) ? expression1 : expression2;
```

### Examples with Detailed Explanation

1. **Basic number check**
```c
int num = 5;
printf("%s", (num > 0) ? "Positive" : "Negative");
```
- Checks if `num` is greater than 0.  
- If yes → prints `"Positive"`.  
- Else → prints `"Negative"`.  
- Output: **Positive**.

2. **Even or odd**
```c
int num = 4;
printf("%s", (num % 2 == 0) ? "Even" : "Odd");
```
- `%` gives remainder.  
- If remainder is 0 → even. Else → odd.  
- Output: **Even**.

3. **Maximum of two numbers**
```c
int a = 10, b = 20;
int max = (a > b) ? a : b;
printf("Max = %d", max);
```
- If `a` is greater → max = a, else max = b.  
- Output: **Max = 20**.

4. **Pass or fail**
```c
int marks = 45;
printf("%s", (marks >= 40) ? "Pass" : "Fail");
```
- Checks if marks ≥ 40.  
- Output: **Pass**.

5. **Discount eligibility**
```c
int amount = 500;
printf("%s", (amount > 300) ? "Discount Applied" : "No Discount");
```
- Checks if purchase amount is more than 300.  
- Output: **Discount Applied**.

6. **Temperature check**
```c
int temp = 30;
printf("%s", (temp > 25) ? "Hot" : "Cool");
```
- Above 25 → hot, else cool.  
- Output: **Hot**.

7. **Voting eligibility**
```c
int age = 17;
printf("%s", (age >= 18) ? "Can Vote" : "Cannot Vote");
```
- Checks if age is at least 18.  
- Output: **Cannot Vote**.

8. **Smallest of two numbers**
```c
int a = 3, b = 5;
int min = (a < b) ? a : b;
printf("Min = %d", min);
```
- Chooses smaller number.  
- Output: **Min = 3**.

---

## 2. For Loop

### Theory
A **for loop** is used when we know in advance how many times a block of code will run.

**Syntax:**
```c
for(initialization; condition; update) {
    // code
}
```

**Real-world example:** Counting up to a fixed number.

### Examples with Detailed Explanation

1. **Print 1 to 5**
```c
for(int i = 1; i <= 5; i++) {
    printf("%d ", i);
}
```
- Starts with `i = 1`.  
- Prints i until i > 5.  
- i increases by 1 each time.  
- Output: `1 2 3 4 5`.

2. **Sum of first 10 numbers**
```c
int sum = 0;
for(int i = 1; i <= 10; i++) {
    sum += i;
}
printf("Sum = %d", sum);
```
- Adds numbers 1 to 10.  
- Final sum = **55**.

3. **Print even numbers from 2 to 10**
```c
for(int i = 2; i <= 10; i += 2) {
    printf("%d ", i);
}
```
- Starts at 2, jumps by 2.  
- Output: `2 4 6 8 10`.

4. **Reverse counting**
```c
for(int i = 5; i >= 1; i--) {
    printf("%d ", i);
}
```
- Counts backward.  
- Output: `5 4 3 2 1`.

5. **Multiplication table of 5**
```c
for(int i = 1; i <= 10; i++) {
    printf("5 x %d = %d
", i, 5*i);
}
```
- Multiplies 5 by i.  
- Prints table of 5.

6. **Print ASCII values**
```c
for(char ch = 'A'; ch <= 'Z'; ch++) {
    printf("%c = %d
", ch, ch);
}
```
- Prints characters and their ASCII code.

7. **Factorial of a number**
```c
int n = 5, fact = 1;
for(int i = 1; i <= n; i++) {
    fact *= i;
}
printf("Factorial = %d", fact);
```
- Multiplies numbers 1 to n.  
- Output for 5 = **120**.

8. **Sum of even numbers**
```c
int sum = 0;
for(int i = 2; i <= 20; i += 2) {
    sum += i;
}
printf("Sum = %d", sum);
```
- Adds even numbers from 2 to 20.  
- Output = **110**.

---

## 3. While Loop

### Theory
The **while loop** runs a block of code as long as the condition is true.

**Syntax:**
```c
while(condition) {
    // code
}
```

**Real-world example:** Fill a bucket until it overflows.

### Examples with Detailed Explanation

1. **Print 1 to 5**
```c
int i = 1;
while(i <= 5) {
    printf("%d ", i);
    i++;
}
```
- Starts with i = 1.  
- Prints and increments until i > 5.  
- Output: `1 2 3 4 5`.

2. **Sum until user enters 0**
```c
int num, sum = 0;
while(1) {
    scanf("%d", &num);
    if(num == 0) break;
    sum += num;
}
printf("Sum = %d", sum);
```
- Loops infinitely until user enters 0.  
- Adds each number to sum.  
- Stops when num = 0.

3. **Reverse counting**
```c
int i = 5;
while(i >= 1) {
    printf("%d ", i);
    i--;
}
```
- Starts at 5, decreases until 1.  
- Output: `5 4 3 2 1`.

4. **Table of 3**
```c
int i = 1;
while(i <= 10) {
    printf("3 x %d = %d
", i, 3*i);
    i++;
}
```
- Multiplies 3 by i from 1 to 10.

5. **Count digits of a number**
```c
int num = 1234, count = 0;
while(num != 0) {
    num /= 10;
    count++;
}
printf("Digits = %d", count);
```
- Divides number by 10 until it becomes 0.  
- Counts number of digits.

6. **Sum of digits**
```c
int num = 123, sum = 0;
while(num != 0) {
    sum += num % 10;
    num /= 10;
}
printf("Sum of digits = %d", sum);
```
- Adds each last digit to sum.  
- Output: **6**.

7. **Check palindrome number**
```c
int num = 121, rev = 0, temp = num;
while(temp != 0) {
    rev = rev * 10 + temp % 10;
    temp /= 10;
}
printf("%s", (rev == num) ? "Palindrome" : "Not Palindrome");
```
- Reverses number.  
- Compares with original.

8. **Print alphabets**
```c
char ch = 'A';
while(ch <= 'Z') {
    printf("%c ", ch);
    ch++;
}
```
- Prints uppercase A-Z.

---

## 4. Do-While Loop

### Theory
Runs at least once, then checks condition.

**Syntax:**
```c
do {
    // code
} while(condition);
```

**Real-world example:** You eat at least one bite before deciding to continue.

### Examples with Detailed Explanation

1. **Print 1 to 5**
```c
int i = 1;
do {
    printf("%d ", i);
    i++;
} while(i <= 5);
```
- Prints first, then checks.

2. **User input until 0**
```c
int num;
do {
    scanf("%d", &num);
} while(num != 0);
```
- Always takes at least one input.

3. **Reverse counting**
```c
int i = 5;
do {
    printf("%d ", i);
    i--;
} while(i >= 1);
```
- Prints numbers 5 to 1.

4. **Table of 7**
```c
int i = 1;
do {
    printf("7 x %d = %d
", i, 7*i);
    i++;
} while(i <= 10);
```
- Prints multiplication table.

5. **Sum until negative**
```c
int num, sum = 0;
do {
    scanf("%d", &num);
    if(num > 0) sum += num;
} while(num > 0);
printf("Sum = %d", sum);
```
- Stops when negative entered.

6. **Password check**
```c
int pass;
do {
    printf("Enter password: ");
    scanf("%d", &pass);
} while(pass != 1234);
printf("Access Granted!");
```
- Loops until correct password.

7. **Factorial of 5**
```c
int i = 1, fact = 1;
do {
    fact *= i;
    i++;
} while(i <= 5);
printf("Factorial = %d", fact);
```
- Calculates factorial.

8. **Print alphabets**
```c
char ch = 'A';
do {
    printf("%c ", ch);
    ch++;
} while(ch <= 'Z');
```
- Prints A-Z.

---

## 5. Break and Continue

### Break
Stops loop immediately.

### Continue
Skips current iteration.

### Break Examples

1. **Exit loop when i = 5**
```c
for(int i = 1; i <= 10; i++) {
    if(i == 5) break;
    printf("%d ", i);
}
```
- Stops at 4.

2. **Stop on input 0**
```c
int num;
while(1) {
    scanf("%d", &num);
    if(num == 0) break;
}
```
- Infinite loop until 0.

3. **Stop when negative found**
```c
int arr[] = {1, 2, 3, -1, 4};
for(int i = 0; i < 5; i++) {
    if(arr[i] < 0) break;
    printf("%d ", arr[i]);
}
```
- Stops before -1.

### Continue Examples

1. **Skip i = 5**
```c
for(int i = 1; i <= 10; i++) {
    if(i == 5) continue;
    printf("%d ", i);
}
```
- Prints all except 5.

2. **Skip even numbers**
```c
for(int i = 1; i <= 10; i++) {
    if(i % 2 == 0) continue;
    printf("%d ", i);
}
```
- Prints odd numbers.

3. **Skip negatives in array**
```c
int arr[] = {1, -2, 3, -4, 5};
for(int i = 0; i < 5; i++) {
    if(arr[i] < 0) continue;
    printf("%d ", arr[i]);
}
```
- Prints positives only.

---

## 6. Switch Case

### Theory
Checks multiple cases for a single value.

**Syntax:**
```c
switch(expression) {
    case value1: // code
        break;
    ...
    default: // code
}
```

### Examples with Detailed Explanation

1. **Day of week**
```c
int day = 3;
switch(day) {
    case 1: printf("Monday"); break;
    case 2: printf("Tuesday"); break;
    case 3: printf("Wednesday"); break;
    default: printf("Invalid day");
}
```
- Prints Wednesday.

2. **Calculator**
```c
int a = 5, b = 3;
char op = '+';
switch(op) {
    case '+': printf("%d", a+b); break;
    case '-': printf("%d", a-b); break;
    default: printf("Invalid");
}
```
- Adds because op = '+'.

3. **Grade system**
```c
char grade = 'B';
switch(grade) {
    case 'A': printf("Excellent"); break;
    case 'B': printf("Good"); break;
    default: printf("Try Harder");
}
```
- Prints Good.

4. **Menu choice**
```c
int choice = 2;
switch(choice) {
    case 1: printf("Pizza"); break;
    case 2: printf("Burger"); break;
    default: printf("Invalid");
}
```
- Prints Burger.

5. **Traffic light**
```c
char light = 'R';
switch(light) {
    case 'R': printf("Stop"); break;
    case 'G': printf("Go"); break;
    case 'Y': printf("Wait"); break;
    default: printf("Invalid");
}
```
- Prints Stop.

6. **Season name**
```c
int month = 7;
switch(month) {
    case 12: case 1: case 2: printf("Winter"); break;
    case 3: case 4: case 5: printf("Spring"); break;
    default: printf("Other Season");
}
```
- Prints Other Season.

7. **Number in words**
```c
int num = 2;
switch(num) {
    case 1: printf("One"); break;
    case 2: printf("Two"); break;
    default: printf("Other");
}
```
- Prints Two.

---

