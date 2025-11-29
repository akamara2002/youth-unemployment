# Youth Employment Predictive Analysis for Africa

A comprehensive data science project analyzing youth employment indicators across African countries using World Bank Development Indicators data. This project includes exploratory data analysis, predictive modeling, and policy recommendations.

## 🚀 Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Start Jupyter Notebook
jupyter notebook

# 3. Open Youth_Employment_Africa_Analysis.ipynb and run all cells
```

That's it! The notebook will automatically detect your data and run the complete analysis.

## 📋 Table of Contents

- [Quick Start](#-quick-start)
- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Requirements](#requirements)
- [Installation](#installation)
- [Data Requirements](#data-requirements)
- [Usage](#usage)
- [Project Workflow](#project-workflow)
- [Output and Results](#output-and-results)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project performs a comprehensive analysis of youth employment challenges across 50 African countries. Using World Bank Development Indicators data, the project:

- **Dynamically detects** relevant socioeconomic indicators (youth unemployment, education, GDP, internet/ICT access)
- **Filters and cleans** data for African countries
- **Performs exploratory data analysis** with visualizations
- **Builds predictive models** (Linear Regression and Random Forest) to predict youth unemployment
- **Generates insights** and policy recommendations for African governments

The analysis is designed to be **robust and adaptive** - it automatically handles missing indicators, detects column names dynamically, and provides fallback options when specific data is unavailable.

## ✨ Features

### Data Processing

- ✅ Automatic encoding detection for CSV files
- ✅ Dynamic column name detection and cleaning
- ✅ Automatic handling of pivoted World Bank data format
- ✅ Intelligent merging of multiple datasets
- ✅ Comprehensive data cleaning (missing values, duplicates, type conversions)

### Analysis Capabilities

- ✅ **50 African Countries** included in analysis
- ✅ **Dynamic Indicator Detection**: Automatically finds youth unemployment, education, GDP, and internet/ICT indicators
- ✅ **Fallback Mechanisms**: Uses closest available indicators when exact matches aren't found
- ✅ **Exploratory Data Analysis**: Multiple visualizations including scatter plots, time series, correlation heatmaps
- ✅ **Predictive Modeling**: Two machine learning models with performance metrics
- ✅ **Feature Importance Analysis**: Identifies key predictors of youth unemployment

### Visualizations

- 📊 Youth unemployment vs education indicators
- 📊 Youth unemployment vs internet/ICT indicators
- 📊 Correlation heatmaps
- 📊 Time series trends by country
- 📊 Model performance comparisons
- 📊 Feature importance rankings

## 📁 Project Structure

```
youth/
│
├── Youth_Employment_Africa_Analysis.ipynb  # Main analysis notebook
├── file1.csv                                # World Bank indicators dataset
├── file2.csv                                # Country metadata dataset
├── README.md                                # This file
└── venv/                                    # Python virtual environment (optional)
```

## 🔧 Requirements

### Python Version

- Python 3.7 or higher

### Required Python Packages

- `pandas` >= 1.3.0
- `numpy` >= 1.20.0
- `matplotlib` >= 3.3.0
- `seaborn` >= 0.11.0
- `scikit-learn` >= 0.24.0
- `jupyter` >= 1.0.0 (for running the notebook)

## 📦 Installation

### Option 1: Using pip (Recommended)

1. **Clone or download this repository:**

   ```bash
   git clone <repository-url>
   cd youth
   ```

   Or simply download the project folder to your computer.

2. **Create a virtual environment (recommended):**

   ```bash
   python3 -m venv venv
   ```

3. **Activate the virtual environment:**

   On **Linux/Mac:**

   ```bash
   source venv/bin/activate
   ```

   On **Windows:**

   ```bash
   venv\Scripts\activate
   ```

4. **Install required packages:**

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

   Or install from a requirements file (if provided):

   ```bash
   pip install -r requirements.txt
   ```

### Option 2: Using conda

1. **Create a conda environment:**

   ```bash
   conda create -n youth_analysis python=3.9
   conda activate youth_analysis
   ```

2. **Install packages:**
   ```bash
   conda install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

## 📊 Data Requirements

The project requires two CSV files:

1. **file1.csv**: World Bank Development Indicators dataset

   - Should contain indicators with years as columns (pivoted format)
   - Must include columns: Country Name, Country Code, Indicator Name, Indicator Code
   - Years should be in columns (1960, 1961, ..., 2024)

2. **file2.csv**: Country metadata dataset
   - Should contain: Country Code, Region, IncomeGroup, and other metadata
   - Used for merging and filtering

### Data Format

- Both files should be in CSV format
- Encoding: UTF-8, Latin-1, ISO-8859-1, or CP1252 (auto-detected)
- World Bank format with metadata in first 4 rows (automatically skipped)

## 🚀 Usage

### Running the Notebook

1. **Start Jupyter Notebook:**

   ```bash
   jupyter notebook
   ```

   Or use JupyterLab:

   ```bash
   jupyter lab
   ```

2. **Open the notebook:**

   - Navigate to `Youth_Employment_Africa_Analysis.ipynb`
   - Click to open it

3. **Run all cells:**

   - Go to `Cell` → `Run All` in the menu
   - Or use the keyboard shortcut: `Shift + Enter` to run each cell sequentially

4. **View results:**
   - All outputs, plots, and analysis results will appear inline
   - Scroll through the notebook to see all visualizations and insights

### Running from Command Line (Alternative)

If you prefer to run the notebook programmatically:

```bash
jupyter nbconvert --to notebook --execute Youth_Employment_Africa_Analysis.ipynb --inplace
```

Or convert to HTML for viewing:

```bash
jupyter nbconvert --to html Youth_Employment_Africa_Analysis.ipynb
```

## 📈 Project Workflow

The notebook follows this structured workflow:

### 1. **Data Loading and Preprocessing**

- Detects file encoding automatically
- Loads both CSV files
- Cleans column names
- Identifies key columns (Country Name, Country Code, etc.)

### 2. **Data Transformation**

- Melts pivoted World Bank format to long format
- Merges both datasets on Country Code
- Filters for 50 African countries

### 3. **Indicator Detection**

- Searches for youth unemployment indicators
- Finds education-related indicators
- Locates GDP/income indicators
- Identifies internet/ICT indicators
- Logs all decisions and fallbacks

### 4. **Data Cleaning**

- Removes missing values
- Converts data types
- Removes duplicates
- Filters to recent years (2000+)
- Creates pivot table for multi-indicator analysis

### 5. **Exploratory Data Analysis**

- Youth unemployment vs education (scatter + time series)
- Youth unemployment vs internet/ICT (scatter + box plots)
- Correlation heatmap
- Top correlations analysis

### 6. **Predictive Modeling**

- Prepares features and target variable
- Splits data into train/test sets
- Trains Linear Regression model
- Trains Random Forest Regressor
- Evaluates both models (R², RMSE)
- Analyzes feature importance

### 7. **Insights and Recommendations**

- Summarizes key findings
- Interprets model results
- Provides policy recommendations
- Discusses limitations

## 📊 Output and Results

The notebook generates:

### Visualizations

- **Scatter plots**: Relationships between indicators
- **Time series plots**: Trends over time by country
- **Correlation heatmaps**: Feature relationships
- **Box plots**: Distribution analysis
- **Model performance plots**: Predictions vs actual, residual plots
- **Feature importance charts**: Key predictors visualization

### Metrics

- **R² Score**: Model fit quality
- **RMSE**: Prediction error
- **Correlation coefficients**: Feature relationships
- **Feature importance scores**: Predictor rankings

### Text Output

- Data summary statistics
- Indicator detection logs
- Model comparison tables
- Policy recommendations
- Limitations discussion

## 🔍 Key Findings

The analysis typically reveals:

1. **Youth Unemployment Patterns**: Varying levels across African countries with different trends
2. **Education Impact**: Correlation between education indicators and employment outcomes
3. **Digital Divide**: Internet/ICT access relationships with employment
4. **Socioeconomic Factors**: Multiple interacting factors affecting youth employment
5. **Model Performance**: Predictive capabilities and key features

_Note: Actual findings depend on the specific data in your CSV files._

## 🛠️ Technologies Used

- **Python 3**: Programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Matplotlib**: Basic plotting
- **Seaborn**: Statistical visualizations
- **Scikit-learn**: Machine learning models
- **Jupyter Notebook**: Interactive development environment

## 🎓 Educational Value

This project demonstrates:

- ✅ Data cleaning and preprocessing
- ✅ Exploratory data analysis
- ✅ Feature engineering
- ✅ Machine learning model training
- ✅ Model evaluation and comparison
- ✅ Data visualization best practices
- ✅ Handling real-world data challenges (missing values, encoding issues, etc.)

## ⚠️ Important Notes

1. **Data Availability**: Results depend on data quality and completeness in your CSV files
2. **Indicator Detection**: The notebook automatically finds the best available indicators, which may vary by dataset
3. **Model Performance**: Model accuracy depends on data quality and feature availability
4. **African Countries**: The project filters for 50 specific African countries - modify the list if needed

## 🔧 Troubleshooting

### Common Issues

**Issue**: `ModuleNotFoundError`

- **Solution**: Install missing packages using `pip install <package-name>`

**Issue**: File encoding errors

- **Solution**: The notebook auto-detects encoding, but you can manually specify if needed

**Issue**: No data found for African countries

- **Solution**: Check that country names in your CSV match the list in the notebook

**Issue**: Empty plots or no visualizations

- **Solution**: Ensure data has been loaded and filtered correctly. Check for missing values.

**Issue**: Model training fails

- **Solution**: Ensure sufficient data points and valid features. The notebook includes fallback mechanisms.

## 📝 Customization

You can customize the analysis by:

1. **Adding more countries**: Modify the `african_countries` list
2. **Changing indicators**: Adjust the keyword searches in indicator detection
3. **Modifying models**: Change hyperparameters or add new models
4. **Adjusting visualizations**: Modify plot styles, colors, or layouts
5. **Extending analysis**: Add new sections or analysis methods

## 🤝 Contributing

Contributions are welcome! Areas for improvement:

- Additional machine learning models
- More sophisticated feature engineering
- Enhanced visualizations
- Additional data sources
- Performance optimizations
- Documentation improvements

## 📄 License

This project is provided as-is for educational and research purposes. Please ensure you have appropriate rights to use the World Bank data.

## 🙏 Acknowledgments

- **World Bank**: For providing the Development Indicators data
- **Open Source Community**: For the excellent Python data science libraries

## 📧 Contact

For questions, issues, or suggestions, please open an issue in the repository or contact the project maintainer.

---

**Last Updated**: November 2024

**Status**: ✅ Production Ready

**Note**: This notebook is designed to run from top to bottom with zero errors. All cells should execute successfully when run sequentially.
