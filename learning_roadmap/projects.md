# Detailed Project Guide for PhD Readiness Roadmap  
*Integrating ML, Generative Design & Energy Simulation for Architecture*

---

## Phase 1: Foundations Mini-Projects

### Project 1.1: Python Parser for EPW Weather Files
**Objective:**  
Learn how to read and extract useful climate data from EPW (EnergyPlus Weather) files using Python. Gain practical skills in file parsing, data cleaning, time series handling, and visualization — foundational for energy simulation and building performance analysis. 
**Background:** 
 EPW files store Typical Meteorological Year (TMY) weather data used in building energy modeling.  
- They contain hourly records of weather parameters like temperature, humidity, solar radiation, wind speed, and more.  
- EPW files are text-based with metadata headers followed by CSV-like data rows.  
- Understanding EPW format and parsing it is crucial for working with building simulation tools and custom weather analysis.
**Input:** 
 | Input                         | Output                                         |
|-------------------------------|------------------------------------------------|
| EPW weather file (e.g., London.epw) downloaded from [EnergyPlus Weather](https://energyplus.net/weather) | - Cleaned CSV file with key weather parameters per hour  <br> - JSON file with structured weather data  <br> - Visualizations of hourly temperature over selected periods |
)  
**Tools:** 
- Python 3.x  
- `pandas` (data handling)  
- `numpy` (numerical operations)  
- `matplotlib` or `seaborn` (visualization)  


---

### Step-by-Step Tasks

#### Step 1: Setup Your Environment

- Create a dedicated project folder for managing files and scripts.  
- Install required Python libraries:  
  ```bash
  pip install pandas numpy matplotlib seaborn
  ```  
- Download an EPW file for your location or any city of interest from the [EnergyPlus Weather Data site](https://energyplus.net/weather).

#### Step 2: Explore EPW File Format

- Open the `.epw` file with a text editor or viewer.  
- Note the first 8 lines are metadata (location info, source, etc.).  
- Starting from line 9, each line corresponds to hourly weather data.  
- Understand key columns:  
  - Dry Bulb Temperature (°C) — Column 7  
  - Relative Humidity (%) — Column 9  
  - Global Horizontal Radiation (Wh/m²) — Column 14  
  - Direct Normal Radiation (Wh/m²) — Column 15  
  - Wind Speed (m/s) — Column 21  
- Refer to the [EPW format specification](https://energyplus.net/weather) for detailed column descriptions.

#### Step 3: Read EPW File into Python DataFrame

```python
import pandas as pd

epw_file = 'path_to_your_epw_file.epw'
weather_df = pd.read_csv(epw_file, skiprows=8, header=None)
print(weather_df.head())
```

- Skip the first 8 metadata lines to directly read data.  
- Inspect initial rows to confirm successful loading.

#### Step 4: Assign Meaningful Column Names

```python
columns = [
    'Year', 'Month', 'Day', 'Hour', 'Minute', 'Data Source and Uncertainty Flags',
    'Dry Bulb Temperature', 'Dew Point Temperature', 'Relative Humidity',
    'Atmospheric Station Pressure', 'Extraterrestrial Horizontal Radiation',
    'Extraterrestrial Direct Normal Radiation', 'Horizontal Infrared Radiation',
    'Global Horizontal Radiation', 'Direct Normal Radiation', 'Diffuse Horizontal Radiation',
    'Global Horizontal Illuminance', 'Direct Normal Illuminance', 'Diffuse Horizontal Illuminance',
    'Zenith Luminance', 'Wind Direction', 'Wind Speed', 'Total Sky Cover',
    'Opaque Sky Cover', 'Visibility', 'Ceiling Height', 'Present Weather Observation',
    'Present Weather Codes', 'Precipitable Water', 'Aerosol Optical Depth',
    'Snow Depth', 'Days Since Last Snowfall', 'Albedo', 'Liquid Precipitation Depth',
    'Liquid Precipitation Quantity'
]

weather_df.columns = columns
print(weather_df[['Year', 'Month', 'Day', 'Hour', 'Dry Bulb Temperature', 'Relative Humidity']].head())
```

#### Step 5: Clean and Prepare the Data

- Adjust `Hour` column: EPW hours run 1 to 24, but Python expects 0 to 23 for time series.

```python
weather_df['Hour'] = weather_df['Hour'] - 1
```

- Create a datetime index for easy time series manipulation.

```python
weather_df['Datetime'] = pd.to_datetime(weather_df[['Year', 'Month', 'Day', 'Hour']])
weather_df.set_index('Datetime', inplace=True)
```

- Keep only the columns essential for your analysis.

```python
weather_df = weather_df[['Dry Bulb Temperature', 'Relative Humidity', 'Global Horizontal Radiation', 'Direct Normal Radiation', 'Wind Speed']]
```

#### Step 6: Export Cleaned Data

```python
weather_df.to_csv('cleaned_weather_data.csv')
weather_df.to_json('cleaned_weather_data.json', orient='records', date_format='iso')
```

#### Step 7: Visualize Key Weather Parameters

- Plot hourly dry bulb temperature for a sample week (first 7 days):

```python
import matplotlib.pyplot as plt
import seaborn as sns

one_week = weather_df.iloc[:168]  # 24 hrs x 7 days

plt.figure(figsize=(12, 6))
sns.lineplot(data=one_week, x=one_week.index, y='Dry Bulb Temperature')
plt.title('Hourly Dry Bulb Temperature for First Week')
plt.xlabel('Date and Hour')
plt.ylabel('Temperature (°C)')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

---

### Bonus Extensions (Optional)

- Plot additional weather variables such as humidity, solar radiation, and wind speed on the same graph or separate plots.  
- Calculate and plot daily averages to observe broader trends.  
- Use interactive plotting libraries like Plotly or Bokeh for richer visual analysis.  
- Handle missing or suspicious data points using interpolation or forward/backward fill methods.  
- Develop a reusable Python function or module to parse any EPW file with ease.

---

### Deliverables

- Python script or Jupyter notebook parsing EPW file into a structured DataFrame.  
- Cleaned and exported CSV and JSON weather data files.  
- Line plots showing hourly temperature trends.  
- Optional: Interactive visualizations and data handling enhancements.  
- Well-documented code with comments explaining each step.

---

### Summary

This project builds essential skills in:

- Reading and parsing complex text-based data files.  
- Time series data handling with `pandas`.  
- Data cleaning and transformation.  
- Visualizing environmental data.  
- Understanding a critical file format used in energy-efficient building simulation workflows.



---

### Project 1.2: CSV Data Visualizer  
**Objective:** Create a reusable Python tool to visualize data trends from CSV files. This project will help you practice data loading, filtering, and plotting techniques for time series or tabular data.  
**Input:** ny CSV file containing time series or tabular data (e.g., weather data, energy consumption data)  
**Output:** Static or interactive plots showing key trends, such as line charts, histograms, and scatter plots. Optional: filtered views based on date/time or variables  
**Tools:** 
- Python 3.x  
- `pandas` (for data handling)  
- `matplotlib` and `seaborn` (for static plotting)  
- Optional: `plotly` or `bokeh` (for interactive visualization)  

#### Tasks:
- Write Python functions to load CSV files into DataFrames  
- Implement plotting functions for line plots, histograms, scatter plots  
- Add options for filtering data by date/time or variables  
- Experiment with adding moving averages or smoothing  
- Create a simple command-line interface or Jupyter notebook for user interaction  

---

### Project 1.3: File I/O Practice (JSON, CSV, IDF)  
**Objective:** Gain proficiency in reading and writing common architectural data formats.  
**Input:** Sample JSON, CSV, and EnergyPlus IDF files  
**Output:** Scripts demonstrating parsing and modification of files  
**Tools:** Python, `pandas`, `json`, `eppy` or `idfreader`

#### Tasks:
- Load and parse JSON files; access nested data  
- Read CSV files with various delimiters and encodings  
- Explore EnergyPlus IDF file structure using `eppy` or `idfreader`  
- Modify IDF parameters programmatically (e.g., change material properties)  
- Save modified files back to disk  
- Document scripts with comments explaining each step  

---

## Phase 2: Machine Learning Mini-Projects

### Project 2.1: Energy Consumption Prediction Model  
**Objective:** Build a supervised ML model to predict building energy use based on weather and design inputs.  
**Input:** Dataset with weather variables, building parameters, and recorded energy use  
**Output:** Trained ML model and performance evaluation report  
**Tools:** Python, `scikit-learn`, `pandas`, `matplotlib`

#### Step-by-Step Guide

### Step 1: Setup Environment

Install the necessary Python libraries if you haven't already:

```bash
pip install pandas matplotlib seaborn
```

Optional for interactive plots:

```bash
pip install plotly bokeh
```

### Step 2: Load CSV File into DataFrame

Write a function to load CSV files flexibly:

```python
import pandas as pd

def load_csv(file_path):
    df = pd.read_csv(file_path)
    print(f"Loaded data with {len(df)} rows and {len(df.columns)} columns.")
    return df

# Example usage
# data = load_csv('your_data.csv')
```

### Step 3: Implement Basic Plotting Functions

Create reusable plotting functions for common visualizations:

```python
import matplotlib.pyplot as plt
import seaborn as sns

def plot_line(df, x_col, y_col, title="Line Plot"):
    plt.figure(figsize=(10,6))
    sns.lineplot(data=df, x=x_col, y=y_col)
    plt.title(title)
    plt.xlabel(x_col)
    plt.ylabel(y_col)
    plt.xticks(rotation=45)
    plt.tight_layout()
    plt.show()

def plot_histogram(df, col, bins=30, title="Histogram"):
    plt.figure(figsize=(8,5))
    sns.histplot(df[col].dropna(), bins=bins, kde=True)
    plt.title(title)
    plt.xlabel(col)
    plt.ylabel("Frequency")
    plt.tight_layout()
    plt.show()

def plot_scatter(df, x_col, y_col, title="Scatter Plot"):
    plt.figure(figsize=(8,6))
    sns.scatterplot(data=df, x=x_col, y=y_col)
    plt.title(title)
    plt.xlabel(x_col)
    plt.ylabel(y_col)
    plt.tight_layout()
    plt.show()
```

### Step 4: Add Data Filtering Options

Filter data by date ranges or variable conditions:

```python
def filter_by_date(df, date_col, start_date=None, end_date=None):
    df[date_col] = pd.to_datetime(df[date_col])
    if start_date:
        df = df[df[date_col] >= pd.to_datetime(start_date)]
    if end_date:
        df = df[df[date_col] <= pd.to_datetime(end_date)]
    return df
```

### Step 5: Experiment with Moving Averages or Smoothing

Add a simple moving average to smooth time series data:

```python
def add_moving_average(df, col, window=3):
    df[f"{col}_MA"] = df[col].rolling(window=window).mean()
    return df
```

### Step 6: Create a Simple User Interface

You can run the tool as a script or use Jupyter Notebook to interact with the functions, for example:

```python
if __name__ == "__main__":
    data = load_csv('your_data.csv')
    filtered = filter_by_date(data, 'Date', '2023-01-01', '2023-01-31')
    smoothed = add_moving_average(filtered, 'Temperature', window=5)
    plot_line(smoothed, 'Date', 'Temperature_MA', title="Smoothed Temperature in Jan 2023")
```

---

## Bonus Extensions (Optional)

- Use **Plotly** or **Bokeh** for interactive plots with zoom and hover features.  
- Add command-line arguments to specify input file, plot type, columns to plot, and date filters.  
- Export generated plots as image files (PNG, SVG).  
- Support multiple CSV input formats (with different delimiters or encodings).  
- Implement error handling and input validation for robustness.

---

## Summary of Deliverables

- Python script or Jupyter notebook with reusable functions for loading CSV data, filtering, and plotting  
- Example usage demonstrating loading data, filtering dates, smoothing, and plotting  
- Optional advanced features for interactivity and CLI support  

---

## References

- [pandas Documentation](https://pandas.pydata.org/docs/)  
- [matplotlib Documentation](https://matplotlib.org/stable/contents.html)  
- [seaborn Documentation](https://seaborn.pydata.org/)  
- [plotly Documentation](https://plotly.com/python/)  
- [bokeh Documentation](https://docs.bokeh.org/en/latest/)  


---

### Project 2.2: Feature Engineering and Model Improvement  
**Objective:** Enhance the baseline model by creating new features and improving data quality.  
**Input:** Existing energy prediction dataset  
**Output:** Improved model with documented feature engineering process  
**Tools:** Python, `scikit-learn`, `pandas`

#### Tasks:
- Analyze feature correlations and distributions  
- Create new features (e.g., lag variables, interaction terms)  
- Apply dimensionality reduction if appropriate (PCA)  
- Test feature selection methods to reduce overfitting  
- Retrain models with engineered features  
- Compare performance to baseline  
- Document all changes and results  

---

## Phase 3: ML-Integrated Generative Design Mini-Projects

### Project 3.1: Parametric Model of Building Element  
**Objective:** Build a parametric architectural element using Grasshopper or equivalent, controlled by adjustable inputs.  
**Input:** Concept sketch or architectural reference  
**Output:** Parametric 3D model with adjustable parameters (e.g., window size, facade pattern)  
**Tools:** Rhino + Grasshopper, Ladybug Tools

#### Tasks:
- Design a simple parametric model (e.g., facade panel or shading device)  
- Create sliders or inputs for key parameters  
- Visualize the effect of parameter changes in real-time  
- Export geometry for simulation (if applicable)  
- Add environmental context like sun path analysis  

---

### Project 3.2: ML Surrogate Model Integration  
**Objective:** Connect a trained ML energy prediction model to your parametric design to evaluate energy performance on the fly.  
**Input:** Parametric model inputs, ML model from Phase 2  
**Output:** Workflow where design changes update predicted energy metrics instantly  
**Tools:** Python, Grasshopper (with Python or GhPython), Ladybug Tools

#### Tasks:
- Export parametric inputs to Python script  
- Load ML model in Python and make predictions from design parameters  
- Link predictions back to Grasshopper for real-time feedback  
- Create visual feedback (e.g., color-coded energy scores) on the model  
- Test with multiple design variations  

---

### Project 3.3: Feedback Loop Implementation  
**Objective:** Implement a basic iterative design refinement loop using ML predictions to guide parameter updates.  
**Input:** Parametric model + ML model  
**Output:** Script that updates design parameters based on predicted energy improvements  
**Tools:** Python, Grasshopper

#### Tasks:
- Define objective function (minimize predicted energy)  
- Automate parameter adjustments to reduce energy use  
- Run multiple iterations and record improvements  
- Visualize convergence or improvement trends  
- Discuss potential for designer-in-the-loop interventions  

---

## Phase 4: Simulation-ML Feedback Loop Mini-Projects

### Project 4.1: Automated EnergyPlus Simulation Workflow  
**Objective:** Automate batch simulations with EnergyPlus/OpenStudio and extract key outputs for ML retraining.  
**Input:** Multiple IDF models with varying parameters  
**Output:** Scripts running simulations and collecting results into a dataset  
**Tools:** Python, EnergyPlus, OpenStudio API, `eppy`

#### Tasks:
- Write Python scripts to modify IDF parameters programmatically  
- Automate batch runs of EnergyPlus simulations  
- Parse simulation output files (CSV or SQLite) to extract energy metrics  
- Store outputs linked with input parameters for ML training  
- Handle errors and logs robustly  

---

### Project 4.2: ML Model Retraining Pipeline  
**Objective:** Build a retraining pipeline that updates ML models with new simulation data after smoothing.  
**Input:** Initial ML model, new simulation results  
**Output:** Updated ML model with improved accuracy  
**Tools:** Python, `scikit-learn`, smoothing libraries (e.g., Savitzky–Golay filter)

#### Tasks:
- Develop data smoothing/preprocessing for simulation results  
- Merge new data with existing training set  
- Retrain ML model incrementally or fully  
- Validate updated model performance  
- Document workflow and version control models  

---

### Project 4.3: Multi-objective Optimization Case Study  
**Objective:** Optimize design parameters balancing energy efficiency and carbon footprint.  
**Input:** Parametric model, ML models for energy and carbon prediction  
**Output:** Pareto front or best compromise solutions  
**Tools:** Python, optimization libraries (e.g., `DEAP`, `PyGMO`), ML models

#### Tasks:
- Define multiple objectives (e.g., minimize energy, minimize carbon)  
- Setup evolutionary algorithm or gradient-based optimizer  
- Run optimization on parameter space  
- Visualize trade-offs and Pareto front  
- Analyze and document design solutions  

---

## Phase 5: GitHub Portfolio & Advanced Projects

### Project 5.1: Publish Portfolio of Projects  
**Objective:** Prepare and publish all completed projects with documentation on GitHub.  
**Input:** Code, notebooks, reports from previous phases  
**Output:** Professional GitHub repository with README, issues, and wiki  
**Tools:** Git, GitHub, Markdown

#### Tasks:
- Organize projects into separate folders with clear README files  
- Write detailed documentation and usage instructions  
- Add example data and scripts to reproduce results  
- Setup version control with commits and branches  
- Publish repository and share link  

---

### Project 5.2: Cloud-based Energy Simulation Demo  
**Objective:** Deploy a demo running energy simulations or ML inference in a cloud environment.  
**Input:** Simulation scripts or ML models  
**Output:** Web app or service accessible remotely  
**Tools:** AWS/GCP/Azure, Docker, Flask/Django (optional)

#### Tasks:
- Containerize simulation or ML scripts with Docker  
- Setup cloud environment and deploy containers  
- Create simple web interface or API endpoint  
- Test remote access and performance  
- Document setup and usage  

---

### Project 5.3: Explainable AI (XAI) Demo  
**Objective:** Build an interactive demo explaining predictions of an ML energy model.  
**Input:** Trained ML model, sample inputs  
**Output:** Visual explanations (e.g., SHAP plots, feature importance)  
**Tools:** Python, `shap`, `lime`, `matplotlib`

#### Tasks:
- Integrate SHAP or LIME libraries for explanation generation  
- Create visualizations showing contribution of features to predictions  
- Build interactive notebook or web app to explore explanations  
- Write interpretive notes to explain results to users  

---

### Project 5.4: User-in-the-Loop Design Interface Prototype  
**Objective:** Prototype an interface allowing designers to adjust parameters guided by ML and simulation feedback.  
**Input:** Parametric model, ML prediction feedback  
**Output:** Interactive tool or plugin supporting iterative design  
**Tools:** Rhino + Grasshopper, Python scripting, web frameworks (optional)

#### Tasks:
- Design UI components for parameter adjustment  
- Display ML/simulation feedback dynamically  
- Allow user to override or suggest design changes  
- Log design iterations and outcomes  
- Evaluate usability and document feedback  

---

# Notes
- Each project builds on prior knowledge and tools  
- Document your process and learnings carefully for PhD applications  
- Feel free to combine or customize projects based on interests or data availability  

---