# Introduction to C Decision Making 
Decision making in C programming refers to the ability of a program to **choose different paths of execution** based on certain conditions. It allows developers to control the flow of the program logically, making it more dynamic and intelligent.

# Importance of Decision Making in Programming

Decision making is one of the most fundamental aspects of programming. It allows a program to **respond intelligently to different situations** instead of executing instructions in a fixed, linear order.

- **Dynamic Behavior**  
  Programs can adapt their execution flow depending on user input, system state, or external conditions.

- **Problem Solving**  
  Enables logical branching for tasks like validation, error handling, and conditional execution.

- **Efficiency**  
  Saves resources by skipping unnecessary computations or avoiding irrelevant code paths.

- **User Interaction**  
  Provides personalized responses and interactive experiences based on user choices.

- **Algorithm Foundation**  
  Essential for implementing loops, recursion, and complex decision-based algorithms.

---
# Conditional Statements 
## if statement 

The **if statement** in C is the simplest form of decision-making. It allows the program to **execute a block of code only when a given condition is true**. If the condition evaluates to false, the block is skipped and program control moves forward. This makes the program dynamic and responsive to different inputs.
### Syntax 
```
if (condition){
 // statements to execute if condition is true
}
```
### Mechanism
1. The condition inside parentheses is evaluated.

2. If the condition is true (non-zero) → the statements inside the block are executed.

3. If the condition is false (zero) → the block is skipped, and control moves to the next statement after the if.

4. No action is taken if the condition fails, unless combined with else.

## if - else statement 

The **if-else statement** in C is used when a program needs to choose between **two alternative paths**. If the condition is true, one block of code executes; if false, another block executes. This ensures that the program always performs one of the two possible actions. It is the most common form of decision-making in programming.

### Syntax 
```
if (condition){
// statements executed if condition is true
}else{
// statements executed if condition is true
}
```
### Mechanism 
1. The condition inside parentheses is evaluated.
2. If the condition is true -> the *if* block executes.
3. If the condition is false -> the *else* block executes.
4. Exactly one of the two blocks will run, ensuring a binary choice.
   
## else - if ladder statement 

The **else-if ladder** in C is used when we need to check **multiple conditions sequentially**. It allows the program to test one condition after another, executing the block of the first true condition. If none of the conditions are true, the `else` block (if present) executes. This structure is helpful when there are more than two possible outcomes.
### Syntax 
```
if (condition1){
  //Statements if conditiona1 is true
}
else if(condition2){
  // statements if condition 2 is ture
}
else if (condition3){
  // statements if condition 3 is true
} else {
  // statements if none of the conditions are ture
}
```
### Mechanism 
1. The program evaluates condition1. If true -> executes its block and skips the rest.
2. If false -> moves to condition2. If true -> executes its block and skips the rest.
3. This continues until a condition is true.
4. If none of the conditions are true, the else block executes.

## nested if statement 

The **nested if statement** in C means placing one `if` statement inside another. It is used when a program needs to check **multiple conditions in a hierarchical manner**. This allows more complex decision-making where one condition depends on another. It is especially useful when decisions are structured step by step.

### Syntax
```
if (condition1){
  if(condition2){
    //statements executed if both condition1 and condition2 are ture
  }
}
```
### Mechanism 
1. The outer if condition is evaluated first.

2. If the outer condition is true, then the inner if condition is checked.

3. If the inner condition is also true, its block executes.

4. If either condition is false, the corresponding block is skipped.

5. This structure allows layered decision-making.
   
## switch 
The **switch statement** in C is a multi-way branch statement. It allows a variable or expression to be tested against multiple possible values, and executes the block corresponding to the matching case. This is useful when there are many possible outcomes based on a single variable. It makes code cleaner and more readable compared to multiple `else-if` conditions.

### Syntax
```
switch (expression){
  case value1:
      // statements for value1
      break;
  case value2:
      // statements for value2
      break;
  default:
      // statements if no case matches
}
```
### Mechanism 
1. The expression inside switch is evaluated.

2. Control jumps to the case that matches the value of the expression.

3. The statements under that case execute until a break is encountered.

4. If no case matches, the default block executes (optional).

5. Without break, execution continues into the next case (known as fall-through).

---

# Loops 
Looping means repeating a task again and again as long as a condition is true, that is, keep repeating until the task is completed.

## While loop
The **while loop** in C is an **entry-controlled loop**. It repeatedly executes a block of code **as long as the given condition is true**. If the condition is false at the beginning, the loop body is skipped entirely. This makes it useful when the number of iterations is not fixed and depends on a condition.
### Syntax
```
while(condition){
  //statements to execute repeatedly
}
```
### Mechanism 
1. The condition inside parentheses is evaluated before each iteration.

2. If the condition is true (non-zero) → the loop body executes.

3. After executing the body, control goes back to re-check the condition.

4. If the condition becomes false (zero) → the loop terminates, and control moves to the next statement after the loop.

### Common Usages of While Loop

1. **Input Validation**  
   Keep asking the user for input until they provide valid data.  
   Example: Keep prompting until a positive number is entered.

2. **Menu-driven Programs**  
   Continuously display options until the user chooses to exit.  
   Example: ATM or shopping cart systems.

3. **Reading Data Until Condition**  
   Process items until a stopping condition is met.  
   Example: Reading lines from a file until end-of-file (EOF).

### Potential Pitfalls: Infinite Loops and How to Avoid Them

#### What is an Infinite Loop?
An infinite loop occurs when the condition of a `while` loop never turns false.  
As a result, the program runs indefinitely, which can cause:
- Memory overflow
- Application crashes
- System slowdown

---

#### Common Causes of Infinite Loops
1. **Condition never changes**  
   - The loop variable or state is not updated inside the loop.  
   - Example: `while(x < 5)` but `x` never increments.

2. **Logical errors in condition**  
   - Mistakes in the condition make it always evaluate to `true`.  
   - Example: `while(x != 5)` when `x` is stuck at a value other than 5.

---

## How to Avoid Infinite Loops
- **Update loop variables inside the loop**  
  Ensure the condition can eventually change.

- **Verify the condition will be met**  
  Double‑check that the loop will eventually evaluate to `false`.

- **Use debugging and testing**  
  Catch potential infinite loops early during development.

---


## do-while loop 
The **do-while loop** in C is an **exit-controlled loop**. It executes the loop body **at least once**, and then continues repeating as long as the condition is true. Unlike the `while` loop, the condition is checked **after** executing the body. This guarantees one execution even if the condition is false initially.

### Syntax
```
do{
  // statements to execute repeatedly
} while (condition); 
```

### Mechanism
1. The loop body executes first, without checking the condition.

2. After execution, the condition is evaluated.

3. If the condition is true (non-zero) → the loop repeats.

4. If the condition is false (zero) → the loop terminates.

5. This ensures the loop runs at least once regardless of the condition.

### Scenarios for Using do-while Loop

The `do-while` loop is useful when you want the loop to execute **at least once**, regardless of the initial condition.  

1. **User Prompt**  
   - Ensures the user is asked for input at least once.  
   - Example: Prompting for a password or username.

2. **Menu-Driven Programs**  
   - Displays a menu repeatedly until the user chooses to exit.  
   - Example: ATM systems or console-based applications.

3. **Retry Logic**  
   - Runs code first, then checks if retry is needed.  
   - Example: Retrying an operation or validating input format.
  
### Comparison: while vs do-while Loop

| Feature                | while Loop                                   | do-while Loop                                |
|-------------------------|----------------------------------------------|----------------------------------------------|
| **Condition Check**     | Condition is checked **before** the loop runs | Condition is checked **after** the loop runs |
| **Minimum Executions**  | May execute **zero times** if condition is false initially | Executes **at least once**, even if condition is false |
| **Use Case**            | When you are unsure if the loop should run at all | When the loop must run at least once (e.g., user prompts

---


## for loop 
The **for loop** in C is an **entry-controlled loop** used when the number of iterations is known in advance. It provides a compact way to initialize, check condition, and update a variable in a single line. This makes it the most commonly used loop for repetitive tasks with fixed counts. It is especially useful for arrays, counters, and structured iterations.

### Syntax 
```
for (initialization; condition; update){
  // statements to execute repeatedly
}
```
### Mechanism
1. Initialization → sets the starting value of the loop variable.

2. Condition → checked before each iteration; if true, the loop body executes.

3. Body Execution → statements inside the loop run.

4. Update → modifies the loop variable (e.g., increment/decrement).

5. Steps 2–4 repeat until the condition becomes false, then control exits the loop.

### Implementing Iterations with a for Loop

The `for` loop is ideal for implementing **fixed iterations**.  
Here are some typical ways to use it:

1. Simple Counting
for (int i = 1; i <= 10; i++) {
    printf("%d ", i); // Prints numbers from 1 to 10
}
2. Array Traversal
c
int arr[] = {10, 20, 30, 40, 50};
int size = sizeof(arr) / sizeof(arr[0]);

for (int i = 0; i < size; i++) {
    printf("%d ", arr[i]); // Prints elements of the array
}
3. Reverse Counting
c
for (int i = 10; i > 0; i--) {
    printf("%d ", i); // Prints numbers from 10 to 1
}

### When to Use a for Loop over Other Loops

The `for` loop is preferred in situations where:

- **Fixed Iteration Count**  
  When the number of iterations is known before entering the loop.

- **Counters and Sequential Progression**  
  Ideal for incrementing or decrementing a counter by a fixed amount each time.

- **Array and Collection Traversal**  
  Commonly used for accessing elements in arrays or data collections where index tracking is required.

---


## Nested Loop 
A **nested loop** in C means writing one loop inside another loop. It is used when we need to perform **repetitive tasks in multiple dimensions**, like iterating over rows and columns. The outer loop controls the number of overall iterations, while the inner loop runs completely for each iteration of the outer loop. This is especially useful in working with arrays, matrices, and pattern printing.

### Mechanism 
1. The outer loop starts and checks its condition.

2. For each iteration of the outer loop, the inner loop runs fully.

3. Once the inner loop finishes, control goes back to the outer loop for the next iteration.

4. This continues until the outer loop condition becomes false.

5. Total iterations = (outer loop count × inner loop count).

# Control Flow Statements in C

Control flow statements allow you to manage the execution path of your program. Here is a breakdown of the most common jump statements used in C programming.

---

## 1. Break Statement
The **break statement** is a loop control statement used to terminate a loop or a `switch` statement immediately.
* **Instant Termination:** Even if the loop condition is still `true`, `break` forces the program to exit the loop.
* **In short:** As soon as `break` is encountered, the loop ends without waiting for the condition to finish.

## 2. Continue Statement
The **continue statement** skips the current iteration and jumps directly to the next iteration of the loop.
* **Skip & Jump:** It stops the execution of the code for the current round and moves straight to the next "round."
* **In short:** "Leave the current work and move to the next cycle immediately."

## 3. Return Statement
In C, the **return statement** is used to exit a function immediately and optionally send a value back to the caller.
* **Exit Point:** Once `return` is executed, the function stops, and control returns to where the function was called.
* **Value Return:** It can return data types like `int`, `float`, `char`, etc., or nothing (`void`).

## 4. Goto Statement
The **goto statement** is a jump statement that moves the program flow directly to a specified label.
* **Forceful Redirect:** It is used to forcefully send the program to a different part of the code without needing a loop or a specific condition.
* **Usage:** It requires a "label" to identify the destination.

### Syntax of `goto`:
```c
goto label_name;

// ... some code that will be skipped ...

label_name: 
    // This is where the program will continue execution
