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
    print(f"Simulation run {i}")
```

### while loops

```python
# Example
iteration = 0 # Initialize a variable 'iteration' with value 0
while iteration < 3:# Start a while loop that runs as long as 'iteration' is less than 3
    print(f"Looping: {iteration}")  # Print the current value of 'iteration' with the text 'Looping: 
    iteration += 1 # Increment 'iteration' by 1 after each loop iteration
```
🧠 Use Cases:

* Loop over multiple .idf files for batch simulations

* Filter through simulation results by condition

---

🧭 Functions and Scope

Functions help modularise energy-related tasks (e.g., pre-processing input, parsing output).

```python
# Example
def run_simulation(building_name): # Defines a function named 'run_simulation' that takes one parameter 'building_name'
    print(f"Running simulation for: {building_name}") # Prints a message to the console, inserting the value of 'building_name' into the string

run_simulation("TestBuilding") # Calls the function with argument "TestBuilding"
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

🔍 Next Topics to Add

* File I/O (open, .read(), with)

* Reading/writing .csv (with pandas)

* Running EnergyPlus with subprocess.run()

    Handling paths with os and pathlib
