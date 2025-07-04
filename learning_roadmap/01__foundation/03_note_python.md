 🐍 Notes: Python for Energy and ML Foundations
> **Note:** All code examples in this file are written as part of my learning process, with an emphasis on how Python can be applied to architectural energy simulation and machine learning workflows relevant to my PhD research.  
> The focus is not just on syntax, but on building intuition for practical use in energy modelling, generative design, and performance optimization.
---

## 🧰 1. Python Basics for Energy Simulation

These notes cover essential Python concepts needed to begin working with energy simulation workflows and prepare for integrating machine learning later.

---

### 📌 Data Types

#### Core Types:
- `int`: Integer values (e.g., `10`, `42`)
- `float`: Decimal values (e.g., `3.14`, `-273.15`)
- `str`: Strings of characters (e.g., `"EnergyPlus"`)
- `bool`: Boolean values (`True`, `False`)

```python
# Example
a = 3.14
b = "Simulation"
c = True

print(type(a))  # <class 'float'>
print(type(b))  # <class 'str'>
print(type(c))  # <class 'bool'>
```
Useful Tip: I'll often use float and str types when handling energy simulation data like weather files or .csv output tables.

---

##🔁 Control Structures

### if statements

```python
# Mock temperature data (e.g., from an energy model or sensor reading)
current_temperature = 28.5  # in °C
# Assigns a temperature reading (28.5°C) to the variable 'current_temperature'

# Define thresholds
cooling_threshold = 25.0
# If temperature is above this, cooling is needed
heating_threshold = 18.0
# If temperature is below this, heating is needed

# Simple rule-based logic to trigger system
if current_temperature > cooling_threshold:
    # Checks if current temperature is above the cooling threshold
    print('Cooling system ON')
    # If true, prints that the cooling system should be turned on

elif current_temperature < heating_threshold:
    # If not above cooling threshold, checks if it's below the heating threshold
    print('Heating system ON')
    # If true, prints that the heating system should be turned on

else:
    # If neither condition is true (i.e., temp is between 18.0°C and 25.0°C)
    print('System OFF – Temperature within comfort range')
    # Prints that no heating or cooling is needed

```

---

### for loops (loop over sequences)

```python
# Example
for i in range(3):
    print("Simulation run " + str(i))
```

### while loops

# Example

```python
iteration = 0  # Initialize a variable 'iteration' with value 0
while iteration < 3:  # Start a while loop that runs as long as 'iteration' is less than 3
    print("Looping: " + str(iteration))  # Convert 'iteration' to a string and print with label
    iteration += 1  # Increment 'iteration' by 1 after each loop (same as iteration = iteration + 1)
```

🧠 Use Cases:

* Loop over multiple .idf files for batch simulations

* Filter through simulation results by condition

---

🧭 Functions and Scope

Functions help modularise energy-related tasks (e.g., pre-processing input, parsing output).

```python
# Example
def run_simulation(building_name):  # Defines a function named 'run_simulation' that takes one parameter 'building_name'
    print('Running simulation for: ' + building_name)  # Prints a message with the value of 'building_name'

run_simulation('TestBuilding')  # Calls the function with argument 'TestBuilding'
```

Scope Notes:

* Variables defined inside a function are not available outside
* Use return to pass values back

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

### Debugging

#### 🔑 Key Concepts

* **Syntax errors vs. runtime** errors:
  * *Syntax errors* prevent code from running at all (e.g., missing colon).
  * *Runtime errors* occur while the code runs (e.g., `ZeroDivisionError`, `TypeError`).
* **Exceptions** are errors that Python raises when something goes wrong.
* **Tracebacks** show where errors occurred and are useful for diagnosing the problem step-by-step.

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
