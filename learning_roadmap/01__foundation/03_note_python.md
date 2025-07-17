# 🐍 Notes: Python for Energy and ML Foundations

> **Note:** All code examples in this file are written as part of my learning process, with an emphasis on how Python can be applied to architectural energy simulation and machine learning workflows relevant to my PhD research.
> The focus is not just on syntax, but on building intuition for practical use in energy modelling, generative design, and performance optimization.

---

# 🧰 1. Python Basics for Energy Simulation

These notes cover essential Python concepts needed to begin working with energy simulation workflows and prepare for integrating machine learning later. Each section highlights the relevance of the concept to architectural energy performance analysis and generative design.

---

## 📌 Data Types

Understanding Python's fundamental data types is crucial for accurately representing and manipulating various forms of building performance data, from numerical sensor readings and simulation outputs to descriptive material properties and operational statuses. Correct data typing ensures accurate calculations and avoids common errors.

#### Core Types:
- `int`: Integer values, used for discrete counts like number of occupants or simulation iterations. (e.g., `10`, `42`)
- `float`: Floating-point (decimal) values, essential for continuous measurements like temperature, energy consumption, or material U-values. (e.g., `3.14`, `-273.15`)
- `str`: Strings of characters, used for textual data such as building names, material descriptions, file paths, or error messages. (e.g., `"EnergyPlus"`, `"south_facade"`)
- `bool`: Boolean values (`True`, `False`), representing logical states like whether a window is open, an HVAC system is active, or a design constraint is met.

```python
# Example: Representing building data with core types
outdoor_temp_celsius = 28.5      # float: A continuous environmental measurement
building_name = "EcoHouse_Design_A" # str: Textual identifier for a design variant
has_natural_ventilation = True  # bool: A binary operational state
number_of_occupants = 4         # int: A discrete count

print(f"Type of outdoor_temp_celsius: {type(outdoor_temp_celsius)}") # <class 'float'>
print(f"Type of building_name: {type(building_name)}") # <class 'str'>
print(f"Type of has_natural_ventilation: {type(has_natural_ventilation)}") # <class 'bool'>
print(f"Type of number_of_occupants: {type(number_of_occupants)}") # <class 'int'>

# Type conversion example: Often needed when parsing data from files
sensor_reading_str = "23.7"
sensor_reading_float = float(sensor_reading_str)
print(f"Converted sensor reading: {sensor_reading_float}, Type: {type(sensor_reading_float)}") # 23.7, Type: <class 'float'>
Useful Tip: I'll often use float and str types when handling energy simulation data like weather files or .csv output tables.
```
**Useful Tip:** I'll often encounter `float` and `str` types when handling energy simulation data, such as parsing numerical outputs from `.csv` tables or reading descriptive parameters from input files. Explicit type conversion is frequently required to ensure data is in the correct format for calculations or model inputs.

---
## 📌 `input()` and Type Conversion
`input()` allows users to enter data which is always a **string**. You often need to convert this for use in simulation parameters- like temperture threasholds, airflow rates, or building size.

```python
# Example: input for room dimensions used in a simulation
width = float(input("Enter room width (in meters): "))
length = float(input("Enter room length (in meters): "))
area = width * length
print("Room area: " + str(area) + " m²")
```
This is useful for interactive scripts where users set design parameters before running energy moddels.

---

## 📌 Truthy and Falsy Values
Falsy values can help check if input values, model settings, or sensor arrays are empty or invalid.

```python
# Example: checking if a weather data list is empty
weather_data = []

if not weather_data:
    print("⚠️ No weather data provided — simulation cannot proceed.")
```

----

## 📌 The `random` Module (for Stochastic Simulation)
Use `random` to **introduce variation in design parameters**, for **Monte Carlo simulations**, or **test robustness** of your models.

```python
import random

# Example: randomly assign insulation thickness for uncertainty testing
insulation_thickness = random.uniform(0.05, 0.15)  # in meters
print("Randomized insulation thickness:", round(insulation_thickness, 3), "m")
```
This is good for sensitivity analysis or generating synthetic scenarios.

---

## 🔁 Control Structures
Control structures are fundamental for implementing dynamic behavior and decision-making logic in energy models and generative design scripts. They allow programs to respond to different conditions and process data iteratively.

### `if` statements

Conditional statements (`if`, `elif`, `else`) are crucial for creating rule-based design behaviors, defining climate adaptation thresholds, or managing operational schedules in energy simulations. They enable systems to react intelligently to changing conditions.


```python
# Mock temperature data (e.g., from an energy model or sensor reading)
current_temperature = 28.5  # in °C
# Assigns a temperature reading (28.5°C) to the variable 'current_temperature'

# Define thresholds for building system control
cooling_threshold = 25.0
# If temperature is above this, cooling is needed
heating_threshold = 18.0
# If temperature is below this, heating is needed

# Simple rule-based logic to trigger system action based on temperature
if current_temperature > cooling_threshold:
    # Checks if current temperature is above the cooling threshold
    print('Cooling system ON: Temperature too high.')
    # If true, prints that the cooling system should be turned on
elif current_temperature < heating_threshold:
    # If not above cooling threshold, checks if it's below the heating threshold
    print('Heating system ON: Temperature too low.')
    # If true, prints that the heating system should be turned on
else:
    # If neither condition is true (i.e., temp is between 18.0°C and 25.0°C)
    print('System OFF – Temperature within comfort range.')
    # Prints that no heating or cooling is needed
```
---

### `for` loops (loop over sequences)

`for` loops are indispensable for iterating over collections of data, such as lists of simulation inputs, hourly weather data, or lists of design alternatives. They enable efficient batch processing and analysis.

```python
# Example 1: Basic iteration
for i in range(3):
    print("Simulation run " + str(i))

# Example 2: Iterating through characters in a string (from Caesar Cipher)
message = "hello world"
for char in message:
    print(char)
# Output:
# h
# e
# l
# l
# o
#
# w
# o
# r
# l
# d

# Example 3: Iterating with conditional checks for characters
alphabet_str = 'abcdefghijklmnopqrstuvwxyz' # Using a string for alphabet
for letter in message:
    if letter in alphabet_str:
        print(letter + " is a letter.")
    else:
        print(letter + " is NOT a letter.")
```

### `while` loops

`while` loops are useful when the number of iterations is not known beforehand, such as in iterative optimization processes or when waiting for a certain condition to be met in a simulation.

#### Example 1 (Basic Iteration)

```python
iteration = 0  # Initialize a variable 'iteration' with value 0
while iteration < 3:  # Start a while loop that runs as long as 'iteration' is less than 3
    print("Looping: " + str(iteration))  # Convert 'iteration' to a string and print with label
    iteration += 1  # Increment 'iteration' by 1 after each loop (same as iteration = iteration + 1)
```
#### Example 2 (Continuous Program Execution)

```python
# Example: Continuous program execution based on user input (from Caesar Cipher)
should_continue_program = True
while should_continue_program:
    user_input = input("Do you want to continue (yes/no)? ").lower()
    if user_input == "no":
        should_continue_program = False
        print("Exiting program.")
    else:
        print("Continuing...")
# This demonstrates how a while loop can keep a program running until a specific
# condition (user typing 'no') is met.
```

---

## 📌 Modulo Operator (%)

The modulo operator (%) returns the remainder of a division. It's particularly useful for operations that involve cycles or checking divisibility
```python
# Basic Usage:
print("10 % 3 =", 10 % 3) # Output: 1 (10 divided by 3 is 3 with remainder 1)
print("10 % 2 =", 10 % 2) # Output: 0 (10 is even)
print("7 % 2 =", 7 % 2)   # Output: 1 (7 is odd)

# Application: Wrapping around a sequence (like an alphabet or time)
alphabet_length = 26
current_pos = 25 # 'z'
shift_by = 3
new_pos = (current_pos + shift_by) % alphabet_length
print("New position after wrap-around: " + str(new_pos)) # (25 + 3) % 26 = 28 % 26 = 2 (which is 'c')

# Use Case: Essential for any cyclical data processing, like working with hours
# in a day (0-23) or days in a week (0-6). For example, finding the hour of day
# after several hours have passed: (current_hour + hours_passed) % 24.
```

---

## `range(start, stop, step)` and reverse iteration with negative step

The `range()` function generates a sequence of numbers, which is commonly used to control the number of iterations in `for` loops or to generate indices. It's incredibly versatile for managing sequential data.
* `range(stop)`: Generates numbers from 0 up to (but not including) stop.
* `range(start, stop)`: Generates numbers from start up to (but not including) stop.
* `range(start, stop, step)`: Generates numbers from start up to (but not including) stop, incrementing by step each time. A negative step allows for reverse iteration.
```python
# Example: Iterating through simulation time steps
print("Forward iteration:")
for i in range(0, 10, 2): # Start at 0, stop before 10, step by 2
    print("Time step: " + str(i))
# Output:
# Time step: 0
# Time step: 2
# Time step: 4
# Time step: 6
# Time step: 8

print("\nReverse iteration:")
for i in range(10, 0, -2): # Start at 10, stop before 0, step by -2
    print("Time step: " + str(i))
# Output:
# Time step: 10
# Time step: 8
# Time step: 6
# Time step: 4
# Time step: 2
```
🧠 Use Cases:
* Loop over multiple `.idf` files for batch simulations or parametric studies.
* Filter through large simulation results datasets based on specific conditions (e.g., finding all hours where indoor temperature exceeded 30°C).
* Iteratively refine design parameters in a generative design process until a performance target is met.

---

## 🧩 Decision Logic in Control Flow (from Projects)

Recent exercises like Hangman and Reeborg's Maze reinforced the value of clean, modular control flow for simulations and logical agents.

**Hangman-style: input validation and guess tracking**
```python
# Check whether a guessed letter is valid (not guessed before)
def is_valid_input(letter, guessed_letters):
    if letter in guessed_letters:
        print("Already guessed.")
        return False
    return True
```
>🔎 Useful for validating user inputs in simulation GUIs, checking for repeated inputs in generative loops, or filtering sensor data events.

**Reeborg-style: movement logic using if/elif/else**
```python
# Example maze logic from Day 6: conditional decision-making in a loop
def decide_next_move():
    if right_is_clear():
        turn_right()
    elif front_is_clear():
        move()
    else:
        turn_left()
```
> 🧠  In energy simulations or design optimizations, similar decision structures are used in simulation agents, reinforcement learning (RL), and climate adaptation rule trees — where agents navigate choices based on changing inputs or spatial conditions.

---

## 📝 State Tracking with Lists and Conditions

```python
guessed_letters = []
guess = input("Guess a letter: ")

if guess in guessed_letters:
    print("You already guessed that.")
else:
    guessed_letters.append(guess)
```
> ✅ Managing state is essential in iterative solvers, simulation result handling, or tracking convergence criteria.
For example, in energy modeling, a list could track which rooms have been simulated, which design variants are completed, or which constraint checks have passed.

---

## 🧭 Functions and Scope

Functions are critical for modularizing energy-related tasks, such as pre-processing input data, parsing simulation output files, or calculating performance metrics. They promote code reusability and maintainability, which is vital for complex energy models and ML workflow

```python
# Example: Defining a reusable function for a simulation task
def run_simulation(building_name): # Defines a function named 'run_simulation' that takes one parameter 'building_name'
    """
    Simulates the energy performance for a given building name.
    In a real scenario, this would trigger an energy simulation engine.
    """
    print(f'Running energy simulation for: {building_name}') # Prints a message with the value of 'building_name'

# Calling the function for different building designs
run_simulation('TestBuilding_VariantA')
run_simulation('OfficeBuilding_Scenario2')
```
**Scope Notes:**
* **Local Scope:** Variables defined inside a function are local to that function and are not accessible from outside it. This prevents unintended side effects and promotes modularity.
* Use return to pass values back
* **Global Scope:** Variables defined outside of any function are global and can be accessed (but generally not directly modified without `global` keyword, which should be used sparingly) by functions.
* **Return Values:** Use `return` to pass values calculated within a function back to the part of the code that called the function.

```python
# Example
def calculate_heating_load(temp_inside, temp_outside):
# Defines a function 'calculate_heating_load' that takes inside and outside temperatures as inputs
    delta = temp_inside - temp_outside
# Calculates the temperature difference (delta) between inside and outside
    return delta * 1.5  # Arbitrary coefficient for example
# Returns the heating load estimate by multiplying the temperature difference by 1.5


result = calculate_heating_load(21, 4) # Calls the function with inside temp = 21°C and outside temp = 4°C, stores the result
print("Estimated load:", result) # Prints the string "Estimated load:" followed by the calculated result
```
### Function Design and Reusability

Designing functions that perform a single, clear task and return results (rather than printing them directly) makes code more modular and easier to integrate into larger systems. The principle of "separation of concerns" helps keep functions focused.
```python
# Example: Refactored Caesar Cipher function
# This function calculates the shifted text and returns it,
# allowing the calling code to decide how to use or display the result.
def caesar_cipher_transform(text_to_shift, shift_amount, mode):
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    transformed_text = ""

    if mode == "decode":
        shift_amount *= -1 # Reverse shift for decoding

    for char in text_to_shift:
        if char in alphabet:
            # Calculate new position, using modulo for wrap-around
            original_index = alphabet.index(char)
            new_index = (original_index + shift_amount) % len(alphabet)
            transformed_text += alphabet[new_index]
        else:
            # Keep non-alphabet characters as they are (robust input handling)
            transformed_text += char
    return transformed_text

# How to use the reusable function:
original_message = "hello world"
encrypted_message = caesar_cipher_transform(original_message, 5, "encode")
print("Encrypted: " + encrypted_message) # Encrypted: mjqqt btwqi

decrypted_message = caesar_cipher_transform(encrypted_message, 5, "decode")
print("Decrypted: " + decrypted_message) # Decrypted: hello world

# Use Case: Imagine this function as a core "data transformation" utility
# in an energy workflow, e.g., standardizing sensor IDs or anonymizing data fields.
```

---

## 🚀 Program Structure and Best Practices

Organizing Python code into well-defined functions and controlling the script's execution flow improves readability, maintainability, and makes projects scalable. This is particularly important as scripts grow from simple exercises to robust tools for energy modeling and ML workflows.

Using `main()` Functions and `if __name__ == "__main__":`

This standard Python idiom defines the primary entry point for a script. Code inside `main()` is executed when the file is run directly, but not when it's imported as a module into another script. This is crucial for building libraries and larger applications, ensuring that utility functions don't run automatically when imported elsewhere.
# Example: Structured program from Caesar Cipher or any command-line tool
import art # Assuming 'art' module provides the logo or similar functionality

# Core logic (e.g., a function to calculate energy use, clean data, or run a simulation step)
# (This would be defined elsewhere or imported, like caesar_cipher_transform above)
def calculate_daily_energy(hourly_data):
    """Calculates total daily energy from a list of hourly values."""
    total = sum(hourly_data)
    # print("Daily total calculated!") # Example of output within a core function
    return total

# Main function to handle user interaction, orchestrate calls to core logic, and manage program flow
```python
def main():
    # Use art.logo if available, otherwise a default message
    if 'art' in globals() and hasattr(art, 'logo'):
        print(art.logo)
    else:
        print("Welcome to the Program!")

    while True:
        # Example: Simulating user interaction or loading data
        user_option = input("Choose an option: (C)alculate Energy, (R)un Caesar Cipher, (Q)uit: ").lower()

        if user_option == 'c':
            sensor_readings_today = [10.5, 12.1, 11.8, 9.9, 13.0, 10.2, 11.5, 9.5, 12.3, 10.8]
            energy_sum = calculate_daily_energy(sensor_readings_today)
            print("Total energy for today: " + str(energy_sum) + " kWh")
        elif user_option == 'r':
            direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n").lower()
            text = input("Type your message:\n").lower()
            shift = int(input("Type the shift number:\n"))
            # Assume caesar_cipher_transform function is defined/imported
            output = caesar_cipher_transform(text, shift, direction) # Calling the function from 'Functions and Scope' section
            print("Here is the {}d result: {}".format(direction, output))
        elif user_option == 'q':
            print("Exiting program. Goodbye!")
            break
        else:
            print("Invalid input. Please choose 'C', 'R', or 'Q'.")

# This block ensures 'main()' runs only when the script is executed directly
# It's a standard and professional way to structure executable Python scripts.
if __name__ == "__main__":
    main()

# Use Case: All energy simulation scripts, ML model training scripts, or generative
# design tools should ideally be structured this way for professionalism and clarity.
```
---

## Debugging
Debugging is an essential skill for any developer, especially in complex domains like energy simulation and machine learning where models can be intricate and data flows complex. A systematic approach to finding and fixing errors saves significant time and ensures the reliability of your code.

#### 🔑 Key Concepts

* **Syntax errors vs. runtime errors**:
  * *Syntax errors:* Prevent code from running at all (e.g., missing colons, misspelled keywords). These are typically caught by your IDE or Python interpreter before execution..
  * *Runtime errors(Exceptions):* Occur while the code runs (e.g., `ZeroDivisionError` if you try to divide by zero, `TypeError` if you perform an operation on incompatible types, `FileNotFoundError` if a file doesn't exist).
* **Exceptions:** Are events that disrupt the normal flow of a program. Python raises them when something goes wrong. Understanding common exception types helps diagnose problems.
* **Tracebacks:** When an unhandled exception occurs, Python prints a "traceback" (or call stack). This detailed report shows where the error occurred in your code, line by line, leading back to the original function call. Learning to read tracebacks is crucial for diagnosing problems step-by-step.

---

#### 🧰 Debugging Techniques

* **Print-based debugging**
  * Use `print()` to inspect values, types, and program flow.
  * Place strategically before/after key logic to trace how data changes.
  * Remember to remove or comment out debug prints once bugs are fixed to keep code clean.

* **Asertions**
  * Use `assert` to catches invalid or unrealistic values early — vital for trustworthy energy predictions.:
```python
# Example: checking heating setpoint range
heating_setpoint = 10  # in °C

assert 15 <= heating_setpoint <= 23, "❌ Setpoint outside thermal comfort range!"
```
* **Input validation**
  * Always check input types, ranges and format to prevent unexpected bugs.
```python
if not isinstance(data, list): 
    raise TypeError("Expected a list")
```
* **Error Handling with `try` / `except`**
Simulation workflows often involve reading files, calculating with uncertain inputs, or parsing outputs. Avoid crashes using try blocks.

```python
# Example: safe division for air change rate
try:
    room_volume = float(input("Enter room volume (m³): "))
    airflow_rate = float(input("Enter airflow rate (m³/h): "))
    ach = airflow_rate / room_volume  # air changes per hour
    print("ACH:", round(ach, 2))
except ZeroDivisionError:
    print("❌ Room volume can't be zero.")
except ValueError:
    print("❌ Please enter valid numeric values.")
```
Protects your script from crashing on bad input and helps debug early.

* **Using the Python Debugger `(pdb)` in VS Code**
VS Code offers a built-in debugger, so you don’t usually need to insert `import pdb; pdb.set_trace()` manually.

How to debug in VS Code:

1. **Set breakpoints:**
Click in the gutter (left margin) next to the line numbers in your Python file to add a red dot — this marks where the debugger will pause.

2. **Start debugging:**

   * Open the Run and Debug panel (`Ctrl+Shift+D` or click the ▶️ icon on the left sidebar).

   * Select Python: Current File and press the green ▶️ button.

   * The debugger will start and pause execution at your breakpoints.

3. **Use the debug controls:**

   * Continue (F5): Runs until the next breakpoint or program end.

   * Step Over (F10): Executes the current line and pauses on the next line.

   * Step Into (F11): Steps inside a function call to debug it line-by-line.

   * Step Out (Shift+F11): Runs the rest of the current function and pauses after returning.

   * Restart (Ctrl+Shift+F5): Restarts debugging session.

   * Stop (Shift+F5): Stops debugging.

4. **Inspect variables:**

   * Hover over variables in the editor to see their current values.

   * Use the Variables pane to watch all current variables and their values.

   * Use the Debug Console to evaluate expressions and run commands (similar to `p var` in pdb).

# 2. 🧰 Manipulating Lists
Lists are fundamental data structures in Python, essential for organizing and managing collections of related data. In energy and ML workflows, lists are perfect for handling sequences like hourly sensor readings, simulation output rows, collections of design alternatives, or even sequences of layers in a building material assembly. Their mutability and flexibility make them powerful tools for data processing.

## 📌 What are Lists?
Lists are ordered, mutable collections of items. They can store items of different data types (heterogeneous) and are defined by square brackets `[]`

These are fantastic notes! They are well-structured, comprehensive, and tailored to your specific PhD research interests. You've clearly put a lot of thought into connecting Python concepts to energy modeling and machine learning.

Here are the Python notes on Manipulating Lists, following your excellent format and integrating the "Coin Flip Streak" lessons:

#### Relevance to Energy/ML:
* **Time-Series Data**: Storing sequences of hourly temperatures, energy consumption, or CO2 levels.
* **Design Variants**: Holding a collection of proposed building designs or material choices.
* **Simulation Outputs**: Representing rows or columns of data from energy simulation result files.
* **Machine Learning Data**: Often used to store features or labels for training models before conversion to more specialized structures like NumPy arrays.
* 
```python
# Example: Various lists for energy and building data

# Hourly temperature readings (time-series data)
hourly_temperatures_c = [22.5, 23.1, 24.0, 23.8, 22.9, 21.5]

# Material properties for a building envelope assembly (mixed types)
wall_assembly = ["Drywall", 0.0127, "Insulation", 0.15, "Brick", 0.10, "Air Gap", 0.05]
# [Material Name (str), Thickness (float), ...]

# Simulation outputs (e.g., peak loads from different design runs)
peak_cooling_loads_kw = [15.2, 16.1, 14.8, 17.5, 15.9]

# A list of boolean design features
has_feature_list = [True, False, True, True, False]
# True: System is active, False: System is inactive
# This could represent HVAC zones, lighting controls, or natural ventilation states.

# Printing list contents directly (simplest way if no custom message is needed)
print(hourly_temperatures_c)
print(wall_assembly)
print(peak_cooling_loads_kw)

# Printing with a descriptive message using string concatenation (+)
# Note: You need to convert non-string types to string using str() before concatenating
print("System status: " + str(system_status))

# Printing the type of a list
print('Type of hourly_temperatures_c: ' + str(type(hourly_temperatures_c))) # <class 'list'>
```

## 📌 Accessing List Elements (Indexing & Slicing)
Accessing specific data points or subsets of data is crucial for analysis.
* **Indexing:** Access individual elements using square brackets [] and their position (index). Python uses 0-based indexing. Negative indices count from the end (-1 is the last element).
* **Slicing:** Extract sub-lists (portions) of a list using a colon `:`. `[start:end:step]` where `end` is *exclusive*.

#### Relevance to Energy/ML:
* Retrieving a specific hour's temperature reading (hourly_temperatures_c[3]).
* Extracting a portion of daily data from a longer time series (daily_data[12:24]).
* Sampling specific features from a larger dataset for model training.

```python
simulation_results = [10.5, 12.1, 11.8, 9.9, 13.0, 10.2, 11.5, 9.5, 12.3, 10.8] # 10 data points

# Accessing elements by index
# Using string concatenation (+) and str() to convert numbers to strings
print("First result: " + str(simulation_results[0]))      # 10.5 (index 0)
print("Fifth result: " + str(simulation_results[4]))      # 13.0 (index 4)
print("Last result: " + str(simulation_results[-1]))      # 10.8 (last element)
print("Second to last: " + str(simulation_results[-2])) # 12.3 (second to last)

# Slicing lists
# Using string concatenation (+) and str() to convert lists to strings
print("Results from index 2 to 5 (exclusive of 5): " + str(simulation_results[2:5])) # [11.8, 9.9, 13.0]
print("First 3 results: " + str(simulation_results[:3])) # [10.5, 12.1, 11.8]
print("Results from index 5 to end: " + str(simulation_results[5:])) # [10.2, 11.5, 9.5, 12.3, 10.8]
print("Every second result: " + str(simulation_results[::2])) # [10.5, 11.8, 13.0, 11.5, 12.3]
print("Copy of the whole list: " + str(simulation_results[:])) # [10.5, ..., 10.8]
```
## 📌 List Methods: Modifying and Querying Lists
Lists are mutable, meaning their contents can be changed after creation. Various methods allow in-place modification or queries about their content.

* `append(item)`: Adds `item` to the end of the list.

* `insert(index, item)`: Inserts `item` at a specific `index`.

* `remove(item)`: Removes the first occurrence of `item`. Raises `ValueError` if item is not found.

* `pop([index]`): Removes and returns the `item` at index (defaults to last item).

* `sort()`: Sorts the `list` in-place (ascending by default).

* `reverse()`: Reverses the order of elements in-place.

* `count(item)`: Returns the number of times `item` appears in the list.

* `index(item)`: Returns the index of the first `item`. Raises ValueError if not found.

* `clear()`: Removes all `items` from the list.

```python
design_variants = ["Design_A", "Design_B", "Design_C"]

# Adding new design variants
design_variants.append("Design_D")
print("After append(): " + str(design_variants)) # ['Design_A', 'Design_B', 'Design_C', 'Design_D']

design_variants.insert(1, "Design_X_New") # Insert at index 1
print("After insert(): " + str(design_variants)) # ['Design_A', 'Design_X_New', 'Design_B', 'Design_C', 'Design_D']

# Removing a variant
design_variants.remove("Design_C")
print("After remove(): " + str(design_variants)) # ['Design_A', 'Design_X_New', 'Design_B', 'Design_D']

popped_variant = design_variants.pop() # Removes and returns 'Design_D'
# Here, we concatenate three parts: a string, the list converted to string, and the popped item converted to string
print("After pop(): " + str(design_variants) + ", Popped: " + str(popped_variant)) # ['Design_A', 'Design_X_New', 'Design_B'], Popped: Design_D

# Sorting (requires all items to be comparable, e.g., all numbers or all strings)
numerical_data = [5.2, 1.1, 9.8, 3.4]
numerical_data.sort()
print("After sort(): " + str(numerical_data)) # [1.1, 3.4, 5.2, 9.8]

# Reversing
numerical_data.reverse()
print("After reverse(): " + str(numerical_data)) # [9.8, 5.2, 3.4, 1.1]

# Querying
print("Count of 1.1: " + str(numerical_data.count(1.1))) # 1
print("Index of 5.2: " + str(numerical_data.index(5.2))) # 1
```

#### Relevance to Energy/ML:
* Adding new sensor readings to a log (`append()`).
* Inserting a new design parameter at a specific point in a sequence (`insert()`).
* Removing outlier data points or failed simulation runs (`remove()`, `pop()`).
* Sorting simulation results by performance metric (`sort()`).
* Counting occurrences of specific conditions (e.g., `count('overheating_hour')`).

## 📌 Mutability and References (Crucial for ML/Simulations)
Lists are mutable, meaning their content can be changed in-place. When you assign one list to another variable, you are creating a reference to the same list in memory, not a copy. This is a common source of subtle bugs.

#### Relevance to Energy/ML:

* If you're generating design variations or manipulating simulation inputs, accidentally modifying the "original" list (because you didn't copy it properly) can lead to incorrect results or unexpected model behavior.
* Understanding references is vital when passing lists to functions or working with nested data structures.

```python
original_inputs = [10, 20, 30]
# Scenario 1: Reference (not a copy)
bad_copy = original_inputs # bad_copy points to the SAME list as original_inputs
bad_copy.append(40)
print("Original after bad_copy append: " + str(original_inputs)) # [10, 20, 30, 40] - OOPS!

# Scenario 2: Slicing for a shallow copy
good_copy_shallow = original_inputs[:] # Creates a new list with copies of elements
good_copy_shallow.append(50)
print("Original after good_copy_shallow append: " + str(original_inputs)) # [10, 20, 30, 40] - Original is unaffected
print("Good shallow copy: " + str(good_copy_shallow)) # [10, 20, 30, 40, 50]

# Scenario 3: Using copy module for explicit copying
import copy
good_copy_method = copy.copy(original_inputs) # Another way for shallow copy
good_copy_method.append(60)
print("Original after good_copy_method append: " + str(original_inputs)) # [10, 20, 30, 40]
print("Good copy via method: " + str(good_copy_method)) # [10, 20, 30, 40, 60]

# Scenario 4: Deep copy (for nested lists)
# Important for complex energy models or ML datasets where lists contain other lists
nested_data = [[1, 2], [3, 4]]
deep_copy = copy.deepcopy(nested_data)
nested_data[0].append(5) # Modify a list INSIDE the original nested list
print("Original nested after deep copy change: " + str(nested_data)) # [[1, 2, 5], [3, 4]]
print("Deep copy after original change: " + str(deep_copy)) # [[1, 2], [3, 4]] - Deep copy is unaffected
```

**Scenario 2**
**What’s happening?**
The slice operator (`[:]`) creates a new top-level list with the same elements. Changes to the new list won’t affect the original.
**Use this when:**
You're duplicating flat data like temperature sets, daylight factors, or simulation inputs you want to modify independently.

**Scenario 3**
**What’s happening?**
Same effect as slicing — `copy.copy()` gives a shallow top-level copy, good for flat lists or objects that don’t contain nested structures.
**When to use:**
When you want to be explicit in your code (e.g. during testing or collaboration) that you’re intentionally making a shallow copy.

---

## 📌 Iterating with for Loops and Membership (in/not in)
`for` loops are essential for processing each item in a list. Membership operators (`in`, `not in`) check for an item's presence.

#### Relevance to Energy/ML:
* Processing hourly data points from a simulation output.
* Checking if a specific material is in a building's material list.
* Validating input parameters against a list of allowed values.
* Iterating through design alternatives to run simulations for each.

```python
sensor_readings = [21.3, 22.1, 20.9, 23.5, 22.8]

# Iterating through elements
print("Processing sensor readings:")
for reading in sensor_readings:
    # Concatenate the string parts and convert 'reading' to string
    print("Current reading: " + str(reading) + "°C")

# Iterating with index (when you need both index and value)
print("\nProcessing readings with index:")
for i in range(len(sensor_readings)):
    # Concatenate multiple string parts, converting numbers to strings
    print("Reading at index " + str(i) + ": " + str(sensor_readings[i]) + "°C")

# Membership testing
target_temperature = 22.1
if target_temperature in sensor_readings:
    # Concatenate the string parts and convert 'target_temperature' to string
    print("\n" + str(target_temperature) + "°C was recorded.")
else:
    # Concatenate the string parts and convert 'target_temperature' to string
    print("\n" + str(target_temperature) + "°C was not found.")

unusual_material = "Aerogel"
allowed_materials = ["Concrete", "Steel", "Glass", "Wood"]
if unusual_material not in allowed_materials:
    # Concatenate the string parts, enclosing 'unusual_material' in quotes
    print("'" + str(unusual_material) + "' is not a standard allowed material.")
```

### 🧠 Coin Flip Streak: A Practical Application of List Manipulation and Iteration

The "**Coin Flip Streak**" problem from "**Automate the Boring Stuff with Python**" is a good exercise for practicing list generation, iteration, and conditional logic. It highlights how even seemingly simple patterns can appear frequently in random data.

Problem Summary: Simulate 100 coin flips (`H` or `T`), then check if there's a streak of 6 identical flips. Repeat this 100 times and calculate the percentage of experiments with a streak.

#### Relevance to Energy/ML:
* **Pattern Recognition**: Similar logic could be used to detect patterns in sensor data (e.g., 6 consecutive hours above a set temperature threshold).
* **Data Quality Control**: Identifying repeated, potentially erroneous, data points or flat lines in time series.
* **Statistical Analysis**: Understanding the probability of specific events occurring in random or pseudo-random sequences (e.g., chance of consecutive sunny days for solar analysis).

```python
import random

number_of_streaks = 0 # Counter for experiments that contain a streak

# Running 100 experiments (as implied by the original print statement's divisor)
for experiment_number in range(100): 
    # 1. Code that creates a list of 100 'heads' or 'tails' values.
    coin_flips = []
    num_flips_per_experiment = 100
    for _ in range(num_flips_per_experiment): # Loop 100 times for each experiment
        if random.randint(0, 1) == 0:
            coin_flips.append('H') # Heads
        else:
            coin_flips.append('T') # Tails
    
    # 2. Code that checks if there is a streak of 6 heads or tails in a row.
    has_a_streak = False # Flag for the current experiment
    streak_length = 6 # Target streak length

    # Using the iterative method with separate counters (more robust for this specific problem)
    current_streak_H = 0
    current_streak_T = 0

    for flip in coin_flips: # Iterate through each flip in the generated list
        if flip == 'H':
            current_streak_H += 1 # Increment Heads streak
            current_streak_T = 0  # Reset Tails streak
        else: # flip == 'T'
            current_streak_T += 1 # Increment Tails streak
            current_streak_H = 0  # Reset Heads streak
        
        # Crucial check: Is either streak long enough?
        # Note: The 'or' operator correctly evaluates both conditions.
        # This was a common bug: 'if current_streak_H or current_streak_T == streak_length:' is incorrect.
        # The correct way is to explicitly compare both sides of the 'or'.
        if current_streak_H >= streak_length or current_streak_T >= streak_length:
            has_a_streak = True
            break # Once a streak is found in this experiment, stop checking and move on
    
    if has_a_streak:
        number_of_streaks += 1

# Calculate and print the chance of streak based on 100 experiments
print('Chance of streak: %s%%' % (number_of_streaks / 100))
```

---

## 🧱 Dictionaries and Structured Data

Dictionaries are ideal for storing named simulation parameters, configuration settings, or simulation outputs with descriptive keys.
```python
simulation_inputs = {
    "insulation_R_value": 3.5,
    "window_U_value": 1.1,
    "thermal_mass": "high"
}
print(simulation_inputs["window_U_value"])  # ➝ 1.1
```
###📌 Dictionary Methods and Safe Access
* Loop over data using `.keys()`, `.values()`, `.items()`: These methods provide views of a dictionary's keys, values, or key-value pairs respectively, which are very useful for iteration
```python
print("\n--- Iterating over simulation_inputs ---")
for key, value in simulation_inputs.items():
    # Using string concatenation here instead of f-string
    print(str(key) + ": " + str(value))
```
* Use get() to safely retrieve values: The get() method allows you to retrieve a value associated with a key, providing a default value if the key is not found, preventing KeyError exceptions. This is safer than direct key access (dictionary[key]) when a key might be missing.
```python
# Example: Safely getting an optional parameter
air_change_rate = simulation_inputs.get("air_change_rate", 0.5) # Default to 0.5 if not found
print("\nAir change rate (retrieved safely): " + str(air_change_rate))

# Example: Getting an existing key
window_u_value = simulation_inputs.get("window_U_value", 0.0) # Will get 1.1, default not used
print("Window U-value (retrieved safely): " + str(window_u_value))
```
>📌 **Why it matters**:  Structured key–value data is central in defining reusable inputs for parametric runs, multi-zone models, and simulation frameworks. get() is crucial for robust code that handles missing optional parameters without crashing.

---

## 🪜 Nested Dictionaries for Hierarchical Data
Dictionaries can contain other dictionaries (or lists, etc.), allowing you to represent hierarchical or complex structured data. This is common in energy simulation for organizing data by building zones, systems, or detailed component properties.
```python
# Example: Multi-zone simulation data
building_data = {
    "zone1": {
        "temperature": 21,
        "humidity": 40,
        "occupancy": 4,
        "sensors": {"temp_sensor_id": "TS001", "rh_sensor_id": "HS001"}
    },
    "zone2": {
        "temperature": 23,
        "humidity": 45,
        "occupancy": 2,
        "sensors": {"temp_sensor_id": "TS002", "rh_sensor_id": "HS002"}
    },
    "building_params": {
        "building_type": "Office",
        "total_area_sqm": 250.5
    }
}

# Accessing data in nested dictionaries
print("\n--- Accessing nested data ---")
print("Zone1 temperature: " + str(building_data["zone1"]["temperature"]) + "°C")
print("Zone2 humidity sensor ID: " + str(building_data["zone2"]["sensors"]["rh_sensor_id"]))
print("Building type: " + str(building_data["building_params"]["building_type"]))

# Iterating over nested dictionaries
print("\n--- Iterating over zones ---")
for zone_name, zone_details in building_data.items():
    # Check if the current item is a zone (e.g., contains 'temperature' key)
    if "temperature" in zone_details:
        # Using string concatenation
        print(str(zone_name) + ": Temp=" + str(zone_details["temperature"]) + "°C, Humid=" + str(zone_details["humidity"]) + "%")
```
> 🧠 **Use for**: Multi-zone simulation data, storing results by room and sensor type, defining complex material layers, or representing configurations of building systems. This structure mirrors the complexity of real-world building models and energy inputs.



🔍 Next Topics to Add

* File I/O (open, .read(), with)

* Reading/writing .csv (with pandas)

* Running EnergyPlus with subprocess.run()

    Handling paths with os and pathlib
