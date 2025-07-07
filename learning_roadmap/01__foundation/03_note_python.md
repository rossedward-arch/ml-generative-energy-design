# 🐍 Notes: Python for Energy and ML Foundations

> **Note:** All code examples in this file are written as part of my learning process, with an emphasis on how Python can be applied to architectural energy simulation and machine learning workflows relevant to my PhD research.
> The focus is not just on syntax, but on building intuition for practical use in energy modelling, generative design, and performance optimization.

---

## 🧰 1. Python Basics for Energy Simulation

These notes cover essential Python concepts needed to begin working with energy simulation workflows and prepare for integrating machine learning later. Each section highlights the relevance of the concept to architectural energy performance analysis and generative design.

---

### 📌 Data Types

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
**Useful Tip:** I'll often encounter float and str types when handling energy simulation data, such as parsing numerical outputs from .csv tables or reading descriptive parameters from input files. Explicit type conversion is frequently required to ensure data is in the correct format for calculations or model inputs.

---

##🔁 Control Structures
Control structures are fundamental for implementing dynamic behavior and decision-making logic in energy models and generative design scripts. They allow programs to respond to different conditions and process data iteratively.

### `if` statements

Conditional statements (if, elif, else) are crucial for creating rule-based design behaviors, defining climate adaptation thresholds, or managing operational schedules in energy simulations. They enable systems to react intelligently to changing conditions.


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
# Example
for i in range(3):
    print("Simulation run " + str(i))
```

### `while` loops

`while` loops are useful when the number of iterations is not known beforehand, such as in iterative optimization processes or when waiting for a certain condition to be met in a simulation.

# Example

```python
iteration = 0  # Initialize a variable 'iteration' with value 0
while iteration < 3:  # Start a while loop that runs as long as 'iteration' is less than 3
    print("Looping: " + str(iteration))  # Convert 'iteration' to a string and print with label
    iteration += 1  # Increment 'iteration' by 1 after each loop (same as iteration = iteration + 1)
```

🧠 Use Cases:
* Loop over multiple `.idf` files for batch simulations or parametric studies.
* Filter through large simulation results datasets based on specific conditions (e.g., finding all hours where indoor temperature exceeded 30°C).
* Iteratively refine design parameters in a generative design process until a performance target is met.

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

###Scope Notes:

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
  * Use `assert` to check that conditions hold true while code runs:
```python
assert temp > 0, "Temperature must be positive"
```
* **Input validation**
  * Always check input types, ranges and format to prevent unexpected bugs.
```python
if not isinstance(data, list): 
    raise TypeError("Expected a list")
```
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



🔍 Next Topics to Add

* File I/O (open, .read(), with)

* Reading/writing .csv (with pandas)

* Running EnergyPlus with subprocess.run()

    Handling paths with os and pathlib
