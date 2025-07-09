# 📚 Progress Log

This file documents the chronological progress of my learning in ML-integrated generative design for energy-efficient buildings. Organized by learning phase and UK date format.

---

## 🧱 Phase 1 – Foundations: Python, Data Handling, and Energy Simulation

---

### 📆 26/06/2025 | 🔧 GitHub Structure

**What I did**:
* Created initial file and folder structure for the learning roadmap project on GitHub.
* Established a `docs/` directory for this progress log and a `src/` directory for code examples related to each learning phase.

**Reflections**:
* This initial setup is crucial for maintaining an organized and scalable project. It provides a clear framework for tracking progress and segregating different types of content (documentation vs. code).
* **Implication for Project**: A well-organized repository will facilitate easier collaboration (if applicable later) and maintainability as the project on ML-integrated generative design grows in complexity. It also allows for clearer version control of learning materials and code.

**Next steps**:
* Populate the `src/` directory with basic Python scripts as I progress through foundational learning.
* Regularly commit changes to ensure version control and maintain a detailed history of learning activities.

---

### 📆 30/06/2025 | 📘 Chapter 1 - Python Basics

**What I did**:
* Completed Chapter 1 of *"Automate the Boring Stuff with Python"* by Al Sweigart, focusing on Python fundamentals.
* Practiced distinguishing and manipulating core data types (`int`, `float`, `str`, `bool`) through interactive REPL sessions and small test scripts.
* Explored basic arithmetic and string operations, understanding type compatibility and conversion.

**Reflections & Insights**:
* Gained clarity on the importance of **data types** in Python; operations differ significantly between numeric and string types. This foundational understanding is critical for accurate data handling in energy simulation, where numerical precision and unit consistency are paramount.
* The interactive REPL was highly effective for immediate feedback and solidifying syntax, reinforcing the iterative nature of programming.
* **Connection to Project**: A strong grasp of basic data types is fundamental for representing and processing building parameters (e.g., temperature as `float`, material properties as `str`, occupancy status as `bool`) within an energy simulation or ML model.

**Challenges**:
* Initially confused by implicit type conversion in certain contexts; needed to explicitly practice `int()`, `float()`, `str()` conversions.

**How I Addressed It**:
* Focused on writing small "type-check" scripts to predict and verify output types, reinforcing explicit conversion practices.

**Next steps**:
* Proceed to Chapter 2 ("Flow Control") to understand conditional logic and looping structures, which are essential for creating dynamic energy simulation scenarios.
* Develop a series of mini-exercises that directly apply data types to conceptual energy scenarios (e.g., representing solar gain or heat loss values).

---

### 📆 01/07/2025 | 🔁 Chapter 2 – Flow Control

**What I did**:
* Completed Chapter 2 exercises on `if`, `elif`, `else` statements and logical operators (`and`, `or`, `not`).
* Practiced `while` and `for` loops, including range-based iteration and nested loops, by working through provided examples.
* Began applying these concepts to mock energy simulation examples, such as creating logic to trigger heating or cooling systems based on simulated indoor temperature thresholds.

**Reflections & Insights**:
* **Conditional logic** is undeniably crucial for creating rule-based design behaviors, especially for defining climate adaptation thresholds or operational schedules in energy simulations. For example, understanding how to model a thermostat's behavior or a shading device's deployment.
* Mastering `while` loops highlighted the importance of clear loop termination conditions to prevent infinite loops, a common debugging challenge.
* **Connection to Project**: Flow control will be indispensable for defining complex building system interactions, occupant behavior models, and iterative optimization processes within generative design algorithms.

**Challenges**:
* Ensuring correct nesting and indentation for complex `if-elif-else` structures.
* Identifying appropriate loop conditions to avoid off-by-one errors or infinite loops.

**How I Addressed It**:
* Used an IDE with automatic indentation (VS Code) to visually verify code structure.
* Drew out flowcharts for more complex conditional paths before coding to map out logic.
* Used `print()` statements within loops to track variable values and iteration counts during initial testing.

**Next steps**:
* Advance to Chapters 3 & 4, focusing on functions and lists, which will allow for modularizing code and handling collections of data relevant to energy performance.
* Design a slightly more complex energy-related exercise combining current skills, e.g., simulating daily temperature fluctuations and triggering HVAC actions throughout a 24-hour cycle.

---

### 📆 03/07/2025 | 📘 Chapters 3 & 4 – Functions, Lists, and Loops

**What I did**:
* Learned to define and utilize **functions** to encapsulate reusable logic, including passing arguments and returning values.
* Practiced understanding **variable scope** (local vs. global) and its implications within and outside functions.
* Explored Python **lists**, including indexing, slicing, appending, and other list operations.
* Used `for` and `while` loops to effectively iterate over lists, including nested lists, to process datasets.
* Applied functions and loops together to simulate basic HVAC control logic over daily temperature data, where a function might represent an HVAC unit and a list holds temperature readings.

**Reflections & Insights**:
* **Functions**: Significantly improve code modularity, readability, and reusability. This will be paramount for managing the complexity of different building system models (e.g., separate functions for natural ventilation, lighting control, envelope performance) within a larger simulation framework.
* **Lists**: Are clearly essential for storing time-series energy data (e.g., hourly energy consumption, sensor readings), building component properties, or simulation outputs. Their flexibility makes them ideal for dynamic data handling.
* **Looping with Data Structures**: The combination of loops and lists enables scalable processing of large datasets, which is critical for energy modeling and machine learning applications that often involve extensive input or output data.
* **Variable Scope**: Understanding local vs. global scope is critical for preventing unintended side effects and ensuring data integrity across different parts of a program.

**Challenges**:
* Initially struggled with the nuances of local vs. global variable scope, leading to unexpected behavior in early function calls.
* Avoiding common logical errors like off-by-one errors when slicing or iterating through lists.
* Maintaining clean and readable code, especially when nesting loops and managing complex list manipulations.

**How I Addressed It**:
* Created specific small functions to test variable scope in isolation, observing how changes inside a function affect variables outside.
* Used `len()` and explicit range iteration to confirm loop boundaries and prevent off-by-one errors.
* Focused on breaking down complex problems into smaller, manageable functions to improve readability and reduce nesting depth. Employed meaningful variable names.

**Next steps**:
* Move to Chapter 5 ("Debugging") to formalize debugging techniques. This will be crucial for efficiently identifying and resolving issues in more complex scripts that will combine functions, lists, and flow control for energy simulations.
* Practice designing simple functions that take lists of "building parameters" and return "energy performance metrics," applying concepts learned so far.

---

### 📆 04/07/2025 | 📘 Chapter 5 – Debugging with VS Code

**What I did**:
* Thoroughly read Chapter 5 on **debugging techniques** for Python programs, focusing on **Visual Studio Code's integrated debugging features**.
* Learned a structured debugging approach: identifying the bug, isolating the problematic code section, diagnosing the root cause, and implementing a fix.
* Practiced setting **breakpoints** in VS Code by clicking the left gutter, and stepping through code using controls like `Step Over` (F10), `Step Into` (F11), and `Step Out` (Shift+F11).
* Experimented with inspecting variables in the **Variables pane** and evaluating expressions directly in the **Debug Console** within VS Code.
* Explored the utility of `print()` statements for quick checks and tracing, understanding how they appear in the VS Code Terminal or Debug Console.
* Practiced using `assert` statements to enforce assumptions about program state and input data, observing how `AssertionError` is raised and how VS Code highlights the point of failure.

**Reflections & Insights**:
* A systematic approach to debugging (identify, isolate, diagnose, fix) is far more efficient than trial-and-error, especially as code complexity grows. This will save significant time in developing and refining energy models.
* VS Code's integrated debugger offers a powerful and intuitive way to understand program execution. **Stepping through code, inspecting variables in real-time, and using the Debug Console** provides much deeper insight than `print()` statements alone, especially for complex logical flows or functions with many variables. This is a critical skill for developing robust simulation and ML code.
* The concept of using `assert` statements throughout code is a powerful proactive measure. It forces developers to explicitly state assumptions about data shapes, types, and model behavior, which can catch errors much earlier in the development cycle, preventing silent failures.
* **Connection to Project**: Debugging skills are indispensable for developing reliable ML models and energy simulation tools. Issues can arise from incorrect data inputs, flawed algorithms, or unexpected interactions between different code modules. Proficiency here will directly impact the accuracy and trustworthiness of my generative design outcomes.

**Challenges**:
* Initially getting comfortable with the various debugging controls (step over, step into, continue) in VS Code and understanding when to use each.
* Diagnosing silent failures (where a program runs but produces incorrect output without throwing an error) remains challenging; this is where `assert` statements and thorough unit testing become critical.

**How I Addressed It**:
* Worked through VS Code's official Python debugging tutorials to familiarize myself with the interface and features.
* Intentionally introduced bugs into small scripts and used the VS Code debugger to pinpoint and resolve them.
* Began incorporating `assert` statements into simple functions to validate input types and expected outputs, aiming to make hidden assumptions explicit and leverage VS Code's error highlighting.

**Next steps**:
* Read Chapter 6 ("Lists") to deepen my understanding of list structures and advanced operations, including list comprehensions, which are highly efficient for data transformations.
* Begin planning how to apply debugging strategies to more complex scenarios, potentially involving external libraries or data files, in preparation for actual energy simulation tasks.
* Consider exploring unit testing frameworks (e.g., `unittest`, `pytest`) once I have a more solid grasp of Python fundamentals, as they offer a more automated and robust way to catch errors.

### 📆 07/07/2025 - 09/07/25| 📘 Chapter 6 – Manipulating Lists

**What I did**:
* Learned how to use list methods like `append()`, `insert()`, `remove()`, `sort()`, and `reverse()`
* Practiced list slicing, indexing, and copying techniques (`list[:]`, `copy.copy()`, `copy.deepcopy()`)
* Explored how lists store references to objects rather than actual values
* Experimented with mutability and how changes to one list can affect others if not copied properly.
* Practiced using `in`, `not in`, and `for` loops to search and iterate through lists

**Reflections**:
* Lists are incredibly versatile, but small mistakes (e.g. off-by-one indexing or reference errors) can break logic
* It’s easy to underestimate the complexity of even basic programs when they combine slicing, loops, and conditionals
* Sorting and filtering lists will be useful for processing and analyzing building performance datasets
* The ability to dynamically update lists should be important for generative workflows and iterative design testing

**Challenges**:
* Remembering the difference when a list operation mutates the list in-place vs returning a new one
* Needed to revisit earlier parts of the chapter to understand why certain list manipulations didn’t behave as expected
* Avoiding accidental reference sharing when copying complex list structures
* Handling mixed-type lists and preserving data consistency.
* Struggled for an hour with the 'Coin Flip Streak' problem because of an `or` operator precedence bug, due to 'short-circuiting, always 100% or 0%.
 
**Next Step**
* **Strategic Adjustment**: I've realized that my understanding from this chapter wasn't solidifying as quickly as I'd like, primarily because I wasn't getting enough hands-on, problem-solving coding practice. To address this and increase my practical coding fluency, I will now begin '100 Days of Code: The Complete Python Pro Bootcamp' (Angela Yu, Udemy). This will provide the intensive, project-based coding experience I need.
* While working on the bootcam, I will also:
  * Break larger problems into smaller parts and write helper functions where possible
  * Re-attempt challenging list-based exercises to reinforce understanding (Struggled for an hour with the 'Coin Flip Streak' problem because of an `or` operator precedence bug, due to 'short-circuiting, always 100% or 0%.)
  * Read Chapter 7 on Dictionaries to understand how key-value data structures can be combined with lists
  * Create a small mini-project that uses both lists and loops, such as managing sensor data or simulation results over time.
