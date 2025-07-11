# Flight Price Prediction - EDA and Feature Engineering

This project performs Exploratory Data Analysis (EDA) and Feature Engineering on flight price data to understand patterns and prepare the dataset for machine learning models.

## Dataset Information

The dataset is sourced from Kaggle: [Flight Price Prediction Dataset](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction)

### Dataset Features

The cleaned dataset contains the following features:

1. **Airline**: The name of the airline company (categorical, 6 different airlines)
2. **Flight**: Flight code information (categorical)
3. **Source City**: Departure city (categorical, 6 unique cities)
4. **Departure Time**: Derived categorical feature with grouped time periods (6 unique time labels)
5. **Stops**: Number of stops between source and destination (categorical, 3 distinct values)
6. **Arrival Time**: Derived categorical feature with grouped time intervals (6 distinct time labels)
7. **Destination City**: Landing city (categorical, 6 unique cities)
8. **Class**: Seat class information - Business or Economy (categorical, 2 values)
9. **Duration**: Total travel time between cities in hours (continuous)
10. **Days Left**: Derived feature calculated by subtracting booking date from trip date
11. **Price**: Target variable containing ticket price information

## Project Structure

```
flight_price_eda/
│
├── flight_price_eda.ipynb    # Main analysis notebook
├── flight_price.xlsx         # Dataset file
└── README.md                 # This file
```

## Analysis Overview

The notebook includes comprehensive data analysis and preprocessing:

### 1. Data Loading and Initial Exploration
- Loading the dataset from Excel file
- Basic data information and statistics
- Data shape and structure analysis

### 2. Feature Engineering
- **Date Processing**: Extracted Date, Month, and Year from Date_of_Journey
- **Time Processing**: 
  - Split Arrival_Time into hour and minute components
  - Split Departure_Time into hour and minute components
- **Stops Mapping**: Converted text stops to numerical values
- **Data Type Conversions**: Converted string features to appropriate data types

### 3. Data Cleaning
- Handled missing values in Total_Stops using mode imputation
- Removed unnecessary columns (Date_of_Journey, Route, Arrival_Time, Dep_Time)
- Applied categorical encoding using OneHotEncoder

### 4. Categorical Data Processing
- One-hot encoding for categorical variables (Airline, Source, Destination)
- Mapped stop categories to numerical values:
  - 'non-stop' → 0
  - '1 stop' → 1
  - '2 stops' → 2
  - '3 stops' → 3
  - '4 stops' → 4

## Dependencies

The following Python libraries are required:

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/SurajK221b/flight_price_eda
cd flight_price_eda
```

2. Install required dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```

3. Run the Jupyter notebook:
```bash
jupyter notebook flight_price_eda.ipynb
```

## Usage

1. Ensure the `flight_price.xlsx` dataset is in the same directory as the notebook
2. Open and run the `flight_price_eda.ipynb` notebook cell by cell
3. The notebook will guide you through:
   - Data loading and exploration
   - Feature engineering steps
   - Data cleaning and preprocessing
   - Categorical encoding

## Key Insights

The analysis reveals important patterns in:
- Airlines operating in different routes
- Price variations across different cities
- Impact of stops on flight pricing
- Time-based patterns in flight schedules
- Class-wise price distributions

## Future Work

This EDA serves as the foundation for:
- Building machine learning models for price prediction
- Advanced feature engineering
- Statistical analysis of price patterns
- Visualization of trends and correlations

## Contributing

Feel free to contribute to this project by:
1. Forking the repository
2. Creating a feature branch
3. Making your changes
4. Submitting a pull request

## License

This project is available under the MIT License.

## Contact

For questions or suggestions, please open an issue in this repository.

---

**Note**: This is an educational project focused on understanding flight pricing patterns through data analysis and feature engineering techniques.
