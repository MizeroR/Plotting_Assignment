# Fuel Efficiency Data Analysis Project

## Overview
This project analyzes a fuel efficiency dataset focused on vehicle transport characteristics. The analysis was conducted as part of an assignment exploring relationships between various vehicle metrics, with particular emphasis on understanding factors influencing greenhouse gas scores and fuel economy.

## Dataset Description
The dataset contains various metrics related to vehicle fuel efficiency, including:

- `id`: Vehicle identification number
- `year`: Model year
- `cylinders`: Number of engine cylinders
- `displ`: Engine displacement volume
- `pv2` and `pv4`: Powertrain variables
- `city`: City driving fuel economy
- `UCity`: Urban city fuel economy
- `highway`: Highway driving fuel economy
- `UHighway`: Urban highway fuel economy
- `comb`: Combined fuel economy rating
- `co2`: Carbon dioxide emissions
- `feScore`: Fuel economy score
- `ghgScore`: Greenhouse gas score (target variable)

## Analysis Performed
The analysis consisted of multiple components:

1. **Data Loading and Preparation**
   - Loaded the fuel efficiency dataset from a CSV file
   - Selected appropriate numeric columns for analysis
   - Displayed initial rows to understand data structure

2. **Correlation Analysis**
   - Created a correlation heatmap to visualize relationships between variables
   - Used matplotlib and seaborn for visualization
   - Applied appropriate color mapping to highlight positive and negative correlations

3. **Data Interpretation**
   - Identified strong positive correlations between efficiency metrics
   - Found negative correlations between engine size and efficiency
   - Analyzed patterns showing how vehicle characteristics affect greenhouse gas scores

## Key Findings
The analysis revealed several important insights:

1. Larger engines (higher cylinder count and displacement) consistently result in worse fuel economy and higher emissions
2. City fuel economy, highway fuel economy, and emission scores are all strongly correlated
3. CO2 emissions are inversely related to efficiency metrics
4. Environmental scores (feScore and ghgScore) strongly reinforce each other
5. Vehicle model year shows relatively weak correlations with performance metrics

## Technologies Used
- Python 3
- Pandas for data manipulation
- Matplotlib and Seaborn for data visualization
- NumPy for numerical operations

## Setup and Execution
To run this analysis:

1. Ensure Python 3 and required libraries are installed
2. Load the dataset using pandas
3. Run visualization code to generate the correlation heatmap
4. Interpret results as documented in the analysis

## Example Code
```python
# Import required libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
# df = pd.read_csv('path_to_fuel_efficiency_data.csv')

# Create correlation heatmap
correlation_matrix = df.select_dtypes(include=['float64', 'int64']).corr()
plt.figure(figsize=(12, 10))
sns.heatmap(correlation_matrix, cmap='RdBu_r', annot=False)
plt.title('Correlation Heatmap of Fuel Efficiency Dataset')
plt.tight_layout()
plt.show()
```

## Conclusions
The analysis effectively illustrates the fundamental trade-off in vehicle design between engine performance (size/power) and environmental efficiency. The strong correlation patterns observed provide valuable insights for understanding vehicle efficiency characteristics and their environmental impact.

## Future Work
Potential extensions of this analysis could include:
- Predictive modeling to estimate greenhouse gas scores based on vehicle characteristics
- Time series analysis to track efficiency improvements over model years
- Feature importance analysis to identify which factors most influence environmental scores
- Cluster analysis to identify distinct vehicle efficiency profiles