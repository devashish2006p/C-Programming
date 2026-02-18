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

## Nested Loop 
A **nested loop** in C means writing one loop inside another loop. It is used when we need to perform **repetitive tasks in multiple dimensions**, like iterating over rows and columns. The outer loop controls the number of overall iterations, while the inner loop runs completely for each iteration of the outer loop. This is especially useful in working with arrays, matrices, and pattern printing.

### Mechanism 
1. The outer loop starts and checks its condition.

2. For each iteration of the outer loop, the inner loop runs fully.

3. Once the inner loop finishes, control goes back to the outer loop for the next iteration.

4. This continues until the outer loop condition becomes false.

5. Total iterations = (outer loop count × inner loop count).

