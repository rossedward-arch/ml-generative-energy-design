# 📚 Progress Log

This file documents the progress of my learning in ML-integrated generative design for energy-efficient buildings. Organized by learning phase.

---

## 🧱 Phase 1 – Foundations: Python, Data Handling, and Energy Simulation

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
* **Connection to Project**: A strong understanding of basic data types is fundamental for representing and processing building parameters (e.g., temperature as `float`, material properties as `str`, occupancy status as `bool`) within an energy simulation or ML model.

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
* **Functions**: Significantly improve code modularity, readability, and reusability. This will be important for managing the complexity of different building system models (e.g., separate functions for natural ventilation, lighting control, envelope performance) within a larger simulation framework.
* **Lists**: Are essential for storing time-series energy data (e.g., hourly energy consumption, sensor readings), building component properties, or simulation outputs. Their flexibility makes them ideal for dynamic data handling.
* **Looping with Data Structures**: The combination of loops and lists enables scalable processing of large datasets, which is critical for energy modeling and machine learning applications that often involve extensive input or output data.
* **Variable Scope**: Understanding local vs. global scope is critical for preventing unintended side effects and ensuring data integrity across different parts of a program.

**Challenges**:
* Initially struggled with the differences between local vs. global variable scope, leading to unexpected behavior in early function calls.
* Avoiding common logical errors like off-by-one errors when slicing or iterating through lists.
* Maintaining clean and readable code, especially when nesting loops and managing complex list manipulations.

**How I Addressed It**:
* Created specific small functions to test variable scope in isolation, observing how changes inside a function affect variables outside.
* Used `len()` and explicit range iteration to confirm loop boundaries and prevent off-by-one errors.
* Focused on breaking down complex problems into smaller, manageable functions to improve readability and reduce nesting depth. Employed meaningful variable names.

**Next steps**:
* Move to Chapter 5 ("Debugging") to formalize debugging techniques. This will be crucial for identifying and resolving issues in more complex scripts that will combine functions, lists, and flow control for energy simulations.
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
* A systematic approach to debugging (identify, isolate, diagnose, fix) is more efficient than trial-and-error, especially as code complexity grows. This will save time in developing and refining energy models.
* VS Code's integrated debugger offers a powerful and intuitive way to understand program execution. **Stepping through code, inspecting variables in real-time, and using the Debug Console** provides much deeper insight than `print()` statements alone, especially for complex logical flows or functions with many variables. This is a important skill for developing robust simulation and ML code.
* The concept of using `assert` statements throughout code is a powerful proactive measure. It forces developers to explicitly state assumptions about data shapes, types, and model behavior, which can catch errors much earlier in the development cycle, preventing silent failures.
* **Connection to Project**: Debugging skills are valuable for developing reliable ML models and energy simulation tools. Issues can arise from incorrect data inputs, flawed algorithms, or unexpected interactions between different code modules. Proficiency in this will directly impact the accuracy and trustworthiness of my generative design outcomes.

**Challenges**:
* Initially getting comfortable with the various debugging controls (step over, step into, continue) in VS Code and understanding when to use each.
* Diagnosing silent failures (where a program runs but produces incorrect output without throwing an error) remains challenging; this is where `assert` statements and thorough unit testing become important.

**How I Addressed It**:
* Worked through VS Code's official Python debugging tutorials to familiarize myself with the interface and features.
* Intentionally introduced bugs into small scripts and used the VS Code debugger to pinpoint and resolve them.
* Began incorporating `assert` statements into simple functions to validate input types and expected outputs, aiming to make hidden assumptions explicit and leverage VS Code's error highlighting.

**Next steps**:
* Read Chapter 6 ("Lists") to deepen my understanding of list structures and advanced operations, including list comprehensions, which are highly efficient for data transformations.
* Begin planning how to apply debugging strategies to more complex scenarios, potentially involving external libraries or data files, in preparation for actual energy simulation tasks.
* Consider exploring unit testing frameworks (e.g., `unittest`, `pytest`) once I have a more solid grasp of Python fundamentals, as they offer a more automated and robust way to catch errors.

---

### 📆 07/07/2025 - 09/07/25| 📘 Chapter 6 – Manipulating Lists

**What I did**:
* Learned how to use list methods like `append()`, `insert()`, `remove()`, `sort()`, and `reverse()`
* Practiced list slicing, indexing, and copying techniques (`list[:]`, `copy.copy()`, `copy.deepcopy()`)
* Explored how lists store references to objects rather than actual values
* Experimented with mutability and how changes to one list can affect others if not copied properly.
* Practiced using `in`, `not in`, and `for` loops to search and iterate through lists

**Reflections**:
* Lists are versatile, but small mistakes (e.g. off-by-one indexing or reference errors) can break logic
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
  * Break larger problems into smaller parts and write helper functions where possible.
  * Re-attempt challenging list-based exercises to reinforce understanding.
  * Read Chapter 7 on Dictionaries to understand how key-value data structures can be combined with lists.
  * Create a small mini-project that uses both lists and loops, such as managing sensor data or simulation results over time.

---

### 📆 12/07/2025 | 🎯 100 Days of Code – Days 1–5 (Angela Yu, Udemy)

**What I did**
* Startedd the **100 Days of Code: The Complete Python to Pro Bootcamp** to gain structured, project based practice.
* Completed **Days 1-5**, which covered:
    * Day 1: Printing, String manipulation, debugging basics, and `input()` usage
    * Day 2: Variables, data types, and simple mathematical operations
    * Day 3: Control flow with `if`, `else`, `elif`; logical operators; nested conditionals
    * Day 4: Randomization and Python lists
    * Day 5: Python loops (`for`, `while`).

* Built small, projects for each day, including:
   * Band Name Generrator
   * A Tip Calculator
   * A simple Treasure Map Game
   * A Rock, Paper, Scissor game
   * Password Generator (with random character selection and user input for complexity
 
 **Reflections & Insights:**
* The bite sized projects help reinforce understanding of core python syntax and logic building skills in a practical context
* The course was designed easier for repetition and gave a greater sense of progression compared to *Automate the Boring Stuff*
* The practice helped me understand **when to use different list operations, control flow logic, and basic user interaction** — useful for simulation input handling.
* Practicing both input() styles — input() vs input("Question") — highlighted how clarity for the user matters when building tools others might use (e.g. simulation UI prompts).

**Challenges:**
* Found it tricky to design the **password generator logic** — especially determining when to use nested loops and how to shuffle characters for randomness.
* Questioned the best style for user prompts: whether to use input() on its own (*Automate the Boring Stuff*) or input("Enter your password length: ") (*100 Days of Code*) — the latter improves clarity and is better for real-world use, but can clutter code during testing.
* Occasionally got confused about **loop ranges and indexing**, especially when combining multiple lists of characters.

**How I Addressed It:**
* Simplified the password generator to print letters, symbols then numbers in a string. Then went back, changed string it to an empty list and `apended.(random.choice(letter/symbol/number))`. Then `random.shuffle` the list and used the `for` loop to turn the list back into a string.
* Settled on always using input("Prompt") with clear labels as a personal best practice

**Next Stage** 
* Read Chapter 7 Dictionaries and Structuring Data 
* Continue with Days 6–10, which include Python functions and built-in modules — both highly relevant to structuring energy simulation code. (will supplement Chapter 2, 3, 4, 6 & 7 from *Automate the Boring Stuff*)

---

### 📆 13/07/2025 | 🎯 Chapter 7 - Dictionaries & Structuiring Data + 100 Days of Code (Days 6 & 7) 

**What I did**
* Read Chapter 7 of *Automate the Boring Stuff with Python* on **dictionaries andd data structuring**
* Practiced creating, accessing, modifying and iterating through dictionaries using `.keys()`, `.values()`, `.items()`, `get()`.
* The importance of using dictionaries for **storing structured data**, especially when working with named inputs or grouped values (e.g materials, properties or simulation parameters).
* Completed Days 6 & 7 of **Angela Yu's 100 Days of Code (Python Bootcamp):**
    * **Day 6**:  Revisited  defining and calling functions in Python,  applied control flow to solve logic-based puzzles using **Reeborg’s World** (Karel-style visual maze-solving) and Built the **"Escape the Maze"** project using loops, conditionals, and functions.
    * **Day 7**: Practiced **string manipulation, flow control, and logic design** in the building **Hangman** game project, using functions and lists together to manage game state, user guesses, and feedback.

**Reflections & Insights:**
* **Dictionaries** make it easy to store complex, labeled data—especially useful for organizing simulation parameters (e.g. room names and thermal properties).
* Nested dictionaries will be key when modeling hierarchical data structures like multi-zone buildings, or storing time-series results by date and sensor.
* **Function-based thinking** allows to break logic into reusable, modular and testable blocks. Which could be applied to different projects and data sets.
* **The Hangman game (Day 7)** reinforced control flow and state tracking—skills.  These skills help with tasks like iterating through simulation steps or tracking convergence (Convergence Meaning your simulation or model reaches a *stable result* or *target threshold* after a number of iterations...)
* Karel-style maze logic reinforced algorithmic thinking and helped build confidence with nested conditionals and loops.

**Challenges:**
* Initially struggled with deeply nested dictionaries—accessing the correct level required careful use of brackets and key names.
* In Hangman, I had trouble keeping which letters had already been guessed when new guesses were made
* Reeborg’s maze logic required careful debugging such as loop conditions that depended on sensing walls or openings.

**How I Addressed It:**
* Started with smaller dictionary examples and used `print` to view nested structures clearly; this made it easier to debug and understand dictionary depth during simulation logic design.
* I createdd list to store all previously guessed letters in Hangman and added a condition to check if the new guess was already in that list before processing.
* I broke the maze-solving algorithm into smaller conditional blocks (e.g., if `right_is_clear():`, `elif front_is_clear():`) and stepped through the program one decision at a time. I also added temporary `print()` statements to trace the decision path. This made it easier to spot infinite loops and incorrect wall-following logic.

**Next Steps:**
*  **Read Chapter 8 – Strings and Text Editing**
 This chapter will strengthen my ability to work with string data—essential for reading/writing simulation configuration files, interpreting user input, handling filenames, and parsing log outputs.
*  **Continue with 100 Days of Code (Days 8–10):**
 Build up confidence with functions, loops, and logic by completing more hands-on projects. These will also support habits in clean, reusable code design.

---

### 📆 16/07/2025 | 📘 100 Days of Code: Day 8 – Caesar Cipher Project

**What I did**
* Completed Day 8 of Angela Yu's "100 Days of Code" bootcamp, focusing on building the **Caesar Cipher** program.
* Learned about modulo operator (`%`) for wrapping around the alphabet
* Practiced implementing conditional logic (`if/else`) for handling encoding/decoding and non-alphabetic characters.
* Reinforced the use of `input()` for user interaction and `while` loops for program continuation.

**Reflections**
* The Caesar Cipher project provided a good application for several important Python concepts (loops, conditionals, string/list manipulation, indexing).
* The use of the modulo operator (`% 26`) for handling shifts that go beyond the alphabet length was a particularly intresting technique I hadn't came across yet.
* Implementing the `if letter not in alphabet:` check was a good practical example of robust input handling. This check for non-alphabet characters is like how I'll need to clean up messy data in my research. If an energy sensor sends a faulty reading, I can't just process it like a normal number; I need to skip it or handle it separately. This was a simple version of that 'robust input handling' idea.
* This project offered valuable hands-on coding practice, aligning with my goal to improve coding fluency identified in my previous log.

**Challanges**
* Initially ensuring the shift_amount correctly wrapped around the alphabet for both encoding and decoding required careful thought, as well as understanding and application of the modulo operator.
* Managing the program's loop (allowing the user to restart or exit) was straightforward but emphasized the importance of clear logical flow.

**Improvements & Research (Self-Directed):**
* After completing Angela Yu's version, I wasn't fully satisfied with the code structure and identified areas for improvement through independent research.
* **Encapsulated Core Logic:** Refactored the main Caesar cipher logic into a dedicated caesar() function that returns the result, rather than directly printing it. This makes the function more reusable and adheres to the principle of "separation of concerns."
* **Organized Program Flow:** Introduced a main() function to manage the primary program loop and user interactions. This significantly improves code organization and readability.
* **Used if __name__ == "__main__": block:** Added this standard Python idiom to ensure the main() function only runs when the script is executed directly (not when imported as a module). This is a best practice for structuring Python applications.
* **Simplified alphabet:** Changed alphabet from a list to a simple string ('abcdefghijklmnopqrstuvwxyz'), as strings are iterable and allow indexing, making the code slightly more concise.
* **Enhanced Readability:** Added more specific comments to functions and key logic blocks.

**Next Step:**
* Continue with Day 9 and subsequent days of the "100 Days of Code" bootcamp, actively looking for opportunities to refactor and apply best practices beyond the immediate lesson.
* Maintain focus on understanding the underlying logic and problem-solving patterns, not just syntax.
* Enure I am logging ,ore specific bug?soulutions ddetails as they arrise, similar to 'coinflip streak' example

---

### 📆 18/07/2025 | 📘 100 Days of Code: Day 9 – Secret Auction Program

**What I did**
* Completed Day 9 of Angela Yu's "100 Days of Code" bootcamp, focusing on building the Secret Auction Program.
* Implemented core auction logic: collecting bidder names and bids, and identifying the highest bidder.
* Integrated a "screen clear" feature to hide previous bids from subsequent participants, enhancing the "secret" aspect of the auction.
* 
**Reflections**
* The project provided an excellent opportunity to apply and solidify foundational Python concepts in a practical scenario.
* Deepened my understanding of the `return` statement in functions, specifically how it passes multiple values (`like name`, `bid_amount`, and a boolean `are_more_bidders`) back to the main program for further processing.
* Gained crucial clarity on how comparison operators (`==`) directly evaluate to boolean (`True`/`False`) values. This allowed for direct assignment to variables (e.g., `are_more_bidders = (more_bidders_answer == "yes"))`, simplifying conditional logic and program flow control.
* Reinforced the utility of dictionaries for storing key-value pairs (bidder name: bid amount) and iterating through them efficiently to find specific data.

**Challanges**
* Persistent Typo: Initially struggled with a subtle but critical typo (`biding_finished` vs. `bidding_finished`) in the loop control variable. This caused the main bidding loop to run indefinitely, even when "No" was entered, highlighting the absolute importance of consistent variable naming and careful debugging.
* Winner Logic Refinement: Had to refine the logic within the `find_highest_bidder` (later `find_auction_winner`) function to correctly track and update both the `highest_bid_so_far` amount and the `winner_name` simultaneously, ensuring the final result was accurate.

**Improvements & Research (Self-Directed):**
* **Enhanced Readability & Clarity:**
  * Refactored variable and function names to be more descriptive and intuitive (e.g., `get_bidder_info` instead of `bidders_info`, `is_bidding_finished` instead of `biding_finished`, `all_bids` instead of `name_and_bid`, `find_auction_winner` instead of `find_highest_bidder`).
  * Added extensive inline comments and docstrings to explain the purpose and logic of each code block and function, significantly improving code maintainability.
* **Robust Screen Clearing:** Implemented a `dedicated clear_screen()` function and strategically placed calls to it within the bidding loop (after each bid, if more bidders exist) and before the final winner announcement. This effectively obscures previous input for the next user.
* **Program Structure (`if __name__ == "__main__":`):** Incorporated the `if __name__ == "__main__":` block to encapsulate the main program execution logic. This is a standard best practice for Python scripts, making the code more modular and reusable if functions were to be imported elsewhere.
* **Function Argument Passing:** Modified the `find_auction_winner function` to explicitly accept the `all_bids` dictionary as an argument, promoting better function independence and data encapsulation.

Next Step:
* Continue with Day 10 and subsequent days of the "100 Days of Code" bootcamp.
* Actively apply the principles of clear naming, robust logic, and modular design learned today to all new projects.
* Maintain focus on understanding the underlying logic and problem-solving patterns, not just syntax.
* Ensure I am logging more specific bug/solution details as they arise, similar to the "coinflip streak" example.

### 📆 20/07/2025 | 📘 100 Days of Code: Day 10 – Calculator Program & PhD learning Environment Setup

**What I did**
* **Miniconda & Environment Setup**: Successfully initiated Miniconda and verified its installation. Created dedicated Conda environments (`phd_learning_env and phd_research_env`) for my PhD learning work. Installed essential data science and machine learning packages (`numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`, `jupyterlab`) into `phd_learning_env`.
* **VS Code Integration**: Configured Visual Studio Code to correctly recognize and utilize the `phd_learning_env` as its Python interpreter for my projects.
* **GitHub Repository Management**: Addressed issues with my local `ml-generative-energy-design repository`, including untracked files and ensuring it was fully synchronized with my GitHub remote. Opted for a clean re-clone of the repository to establish a pristine and up-to-date local working copy.
* **Calculator Project (Day 10)**: Engaged in an iterative debugging process for the "Day 10 Calculator" program from Angela Yu's "100 Days of Code" bootcamp. This involved multiple rounds of identifying and fixing errors to achieve a fully functional calculator.

**Reflections**
* **Environment Management**: Gained a much clearer understanding of isolated Conda environments for different projects and how to manage them (conda env list, conda activate).
* **VS Code Interpreter Selection**: Linking VS Code to specific Conda environments, recognizing the role of the "Python: Select Interpreter" command and verifying activation in the integrated terminal.
* **Git Workflow**: Reinforced the practice of cloning a fresh repository from GitHub for a clean start, and the use of `git status` to understand the state of the working directory.
* **Function Arguments & Return Values**: Understanding of how arguments are passed to function parameters, and the necessity of capturing a function's `return` value in the calling scope to use it later in the program. This was a recurring challenge that led to significant learning.
* **Variable Scope**: The concept of variable scope, particularly how variables defined inside a function (like `answer` in `calculate`) are local to that function and are not directly accessible outside it without being returned and captured.
* **Loop Control**: Worked on the correct way to terminate a while loop  using a boolean flag (should_continue = False) instead of return False in the global script scope.
* **Data Type Conversion**: The importance of converting user input (strings from input()) to appropriate numeric types (float()) before performing mathematical operations.
* **Modular Design**: Applied principles of modularity by encapsulating the main program logic within a calculator() function and organizing arithmetic operations into separate, reusable functions. It still provides a great deal of work and understanding to get to this stage. But with time I hope to improve

**Challenge**
* **PowerShell Execution Policy**: Encountered and resolved a `PSSecurityException` in PowerShell that prevented Conda environments from activating correctly in the VS Code terminal, requiring a change in the `Set-ExecutionPolicy` setting.
* **Persistent Variable Scope Misunderstanding**: The concept of answer being local to calculate and needing to be captured in the main loop was a particularly challenging. This required multiple iterations of feedback and self-correction.
* **art Module Usage**: When trying to print(art) it doesn't print the desired ASCII art; print(art.logo) was required to access the specific art variable within the module.

**Improvements & Research (Self-Directed):**
* **Clean GitHub Clone**: Deleted and re-cloned the GitHub repository to ensure a clean, up-to-date starting point, avoiding potential conflicts from previous local work.
* **Robust Calculator Logic**: Implemented a continuous calculation flow where the previous result can be used as the first number for the next operation.
* **Input Type Handling**: Switched from `int()` to `float()` for user input to allow for decimal calculations.
* **Centralized Error Handling (for operations)**: Consolidated error messages for invalid operations and division by zero, returning `None` from lower-level functions and handling the display of the error in the main `calculator` function.
* **Standard Program Entry Point**: Incorporated the `if __name__ == "__main__":` block for best practice in Python script execution.
* **Refined art Import**: Corrected the print(art) to print(art.logo) to correctly display the ASCII art.

**Next Step:**
* **Prioritize "Python for Data Science and Machine Learning" bootcamp on Udemy**: Focus intensely on this bootcamp to build the specific skill set (especially `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`) directly relevant to the PhD research.
* **Integrate mini-projects with bootcamp learning**: Apply concepts learned in the bootcamp to the "EPW weather file parser and summary tool" and "CSV data visualizer" mini-projects as practical applications, rather than tackling them as separate, isolated tasks.
* **Pause "100 Days of Code" (Day 11 onwards) for now**: Dedicate full focus to the Data Science/ML bootcamp to ensure deep absorption and efficient progress towards PhD goals. This focused approach is expected to be more sustainable and effective than splitting time between two intensive learning paths. I will go back as a secondary priority for a broader Python proficiency. Probably after I have completed the EPW parser and CSV visualizer.

---

### 📆 24/07/2025 | 📘 Udemy - Python for Data Science and Machine Learning Bootcamp (Sections 1-4)

**What I did:**

* **Course Overview & Setup (Sections 1-3):**
  * Completed the initial course introduction and FAQ.
  * Reviewed environment setup, refreshing my knowledge even though I had a prior setup.
  * Explored Jupyter Notebook setup with Anaconda but opted to integrate its benefits with VS Code, directing environments within VS Code to remember folder-specific configurations.
* **Python Crash Course (Section 4):**
  * Gained an overview of Python basics.
  * Learned about **List Comprehensions** `[num**2 for num in x]` for concise list creation and transformation.
  * Explored `map()` **and** `filter()` functions for applying operations across sequences and selecting elements.
  * Introduced `lambda` **functions** for creating anonymous, single-expression functions to use with `map()`, `filter()`, etc.
  * Practiced **String methods** like `.split()` (e.g., `tweet.split("#")[1]` for extracting data).

**Reflections & Insights:**
* **Foundational Reinforcement**: My understanding of the Python crash course was largely without significant issues, which confirms that my previous learning efforts have established a solid foundation.
* **List Comprehensions vs. For Loops**: While a traditional `for` loop might initially seem easier to read for very complex logic, I've noted that list comprehensions (e.g., `[num**2 for num in x]`) are not only often more concise and efficient but are also considered highly "Pythonic." I realize that with increased familiarity, they will likely improve readability for common transformations. Given their prevalence and value in data science and machine learning (especially with Pandas and NumPy), I need to become more comfortable using them efficiently for data manipulation.
* **`map()` and `lambda` for Conciseness**: Using `list(map(lambda num:num*3, seq))` directly within functions like `map()` can significantly reduce the need for writing and defining full, named functions. I understand that `lambda` functions are specifically designed for quick, anonymous operations. Although they might initially appear more difficult to grasp, their conciseness is valued in data processing, particularly when performing simple transformations without excessive code. Their widespread use with Pandas' `.apply()` method further underscores their importance.
* **Data Preprocessing Fundamentals**: Understanding `filter()` for selective data extraction and `split()` for parsing strings (like extracting hashtags from tweets) are fundamental skills. These will be essential  for crucial data cleaning and preprocessing tasks when handling real-world building performance data.

**Challenges:**

* **Lambda Function Conceptual Hurdle**: While generally clear, `lambda` functions initially presented a slight conceptual hurdle. Their direct integration within `map()` or `filter()` represents a different programming paradigm compared to defining traditional named functions.

**How I Addressed It:**

* I repeated examples involving `lambda` functions and on grasping the core concept: a `lambda` is essentially a mini-function used where a function object is needed for a single, immediate operation. Practicing with various scenarios helped solidify this understanding.

**Next steps:**
* Continue with the "Python for Data Science and Machine Learning Bootcamp" by Jose Portilla, prioritizing upcoming sections to build the specific data science and machine learning skill set directly relevant to my PhD research.

* Begin to think about how these newly learned concepts (list comprehensions, `map`, `filter`, `lambda`) can be applied to mini-projects like the "EPW weather file parser" and "CSV data visualizer" as I progress through the bootcamp.


### 📆 30/07/2025 | 📘 Udemy - Python for Data Science and Machine Learning Bootcamp (NumPy section)
**What I did:**

**NumPy: Numerical Python for Efficient Array Operations (Core Data Science Libraries):**
* Gained a foundational understanding of `ndarray` objects and how NumPy provides highly optimized operations for multi-dimensional arrays (tensors).

  * Explored **Array Creation and Manipulation** using functions like `np.zeros()`, `np.ones()`, `np.arange()`, and `np.linspace()`, including `reshape()` for changing array dimensions.
  * Practiced **Array Indexing and Slicing** for data extraction and modification, including basic integer indexing and boolean masking.
  * Increase my understanding of **Array Operations (Element-wise & Aggregations)**, noting their speed advantage over Python loops.
  * Introduced to the concept of **Broadcasting** for simplifying operations between arrays of different (but compatible) shapes.
  * Explored **Linear Algebra Operations** like dot products and matrix multiplication (`@`), recognizing their fundamental role, especially for future ML applications.
  
**Reflections & Insights:**
  * **Efficiency is Key (Vectorization):** There is a speed difference between NumPy operations and traditional Python loops for numerical tasks. This concept of **vectorization**, powered by underlying C-implemented **Universal Functions (ufuncs)**, is important. I can see its relevance for handling large energy simulation outputs and climate datasets, where performance will be critical for rapid iteration and model training.
  * **Structured Data Representation:** NumPy's ability to represent data as 1-D vectors, 2-D matrices, and higher-dimensional tensors (arrays) aligns with how I'll need to structure building design parameters, spatial climate grids, and sequential simulation results in my PhD. This provides a clear framework for organizing complex data.
  * **Foundation for ML:** Even without diving deep into ML yet, the connection between NumPy's linear algebra capabilities and the future development of surrogate models and neural networks is evident. Understanding these foundational operations now will make the ML concepts much clearer when I get to them.
**Challenges:**
* **Visualizing Higher Dimensions:** While 1-D and 2-D arrays are straightforward, mentally conceptualizing how to work with 3-D and higher-dimensional tensors for things like building geometry or climate data proved a slight challenge but I'm sure once I practice applying this later, it will become easier.
* **Linear Algebra ML Context:** As anticipated, the specific application of linear algebra in neural networks (e.g., "weights and biases") is still abstract without prior ML knowledge. I am just aware that it will become more important later

**How I Addressed It:**
* For visualizing higher dimensions, I focused on relating them to real-world data structures (e.g., 3D grid as `[x, y, z]` for building volumes, or `[time, location, variable]` for climate data) and drawing simple diagrams.
* For the ML linear algebra, I added a specific note in my `note_python_fundamentals.md` to acknowledge that I'll revisit these examples once I researched into the ML sections of the bootcamp, ensuring I don't get stuck prematurely.

**Next steps:**
* Continue with the "Python for Data Science and Machine Learning Bootcamp" by Jose Portilla, moving into the Pandas section. I anticipate this will build directly on NumPy and provide even more powerful tools for data manipulation.
* Look for opportunities to apply NumPy's array creation, indexing, and vectorized operations to small practice problems or conceptual mini-projects related to building data, even before formally starting my PhD research.

---

### 📆 04/08/2025 | 📘 Learning from "Python for Data Analysis: Data Wrangling with pandas, NumPy, and Jupyter" by Wes McKinney
**What I did:**
* **Shifted Learning Approach:** I have switched from "Python for Data Science and Machine Learning Bootcamp" by Jose Portilla to Wes McKinney's "Python for Data Analysis" to get a more systematic, in-depth approach to data science fundamentals.
* **NumPy Deep Dive (Building on previous knowledge):**
  * I reaffirmed my understanding of core NumPy concepts, including `ndarray` objects as multi-dimensional arrays (tensors).
  * I went into more depth on key operations, recognizing the "how" and "why" behind the code.
  * I focused on the difference between slicing (view) and fancy indexing (copy) and how that impacts data manipulation.
  * I explored the use of `np.swapaxes()` for more granular control over axis manipulation compared to the simple `.T` transpose.
  * I connected the technical implementation of linear algebra (`A.T @ A`) to its statistical meaning: the calculation of a **covariance matrix** for understanding relationships between variables.
  * I also made a connection between `np.random.standard_normal()` and its statistical meaning as a distribution with a **mean of 0** and a **standard deviation of 1**, which is crucial for adding noise or initializing ML model weights.

**Reflections & Insights:**
* **Value of In-Depth Learning:** The change in learning resources has been beneficial, providing a more structured and detailed explanation of why these tools work the way they do, which is more suited to a research context. I believe this will create a stronger foundation for my PhD work.
* **Bridging the Gap (Code & Statistics):** A key insight from today's session was the importance of connecting the technical code with the underlying statistical principles. Understanding that a simple matrix multiplication can produce a covariance matrix gives a much deeper and more practical understanding of the tool.
* **Strategic Note-Taking:** My notes are becoming more robust by including both the code and the conceptual/statistical explanations in the same place, which will be a great reference later on.

**Next steps:**
* Finish the chapter on Numpy Basics: Arrays and Vectorized Computation.
* I will continue with the "Python for Data Analysis" book, moving into the pandas section, which builds directly on the NumPy concepts. I expect this to provide tools for structured data handling. I will also continue to relate these concepts to my PhD research areas as I learn them, making the notes as practical as possible.