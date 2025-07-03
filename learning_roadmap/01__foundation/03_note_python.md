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
# Example
# Mock temperature data (e.g., from an energy model or sensor reading)
current_temperature = 28.5  # in °C

# Define thresholds
cooling_threshold = 25.0
heating_threshold = 18.0

# Simple rule-based logic to trigger system
if current_temperature > cooling_threshold:
    print('Cooling system ON')
elif current_temperature < heating_threshold:
    print('Heating system ON')
else:
    print('System OFF – Temperature within comfort range')

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
iteration = 0
while iteration < 3:
    print(f"Looping: {iteration}")
    iteration += 1
```
🧠 Use Cases:

* Loop over multiple .idf files for batch simulations

* Filter through simulation results by condition

---

🧭 Functions and Scope

Functions help modularise energy-related tasks (e.g., pre-processing input, parsing output).

```python
# Example
def run_simulation(building_name):
    print(f"Running simulation for: {building_name}")

run_simulation("TestBuilding")
```

Scope Notes:

* Variables defined inside a function are not available outside
* Use return to pass values back

```python
# Example
def calculate_heating_load(temp_inside, temp_outside):
    delta = temp_inside - temp_outside
    return delta * 1.5  # Arbitrary coefficient for example

result = calculate_heating_load(21, 4)
print("Estimated load:", result)
```

🔍 Next Topics to Add

* File I/O (open, .read(), with)

* Reading/writing .csv (with pandas)

* Running EnergyPlus with subprocess.run()

    Handling paths with os and pathlib
