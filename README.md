# README for CRM Sales and Data Cleaning Project

## Overview
This repository encompasses the **CRM Sales and Data Cleaning Project**, including:
1. **Data Cleaning and Preprocessing Notebook**: Jupyter Notebook designed for cleaning and preparing CRM data.
2. **Power BI Dashboard Template**: Interactive template for analyzing CRM sales opportunities.
3. **Complete Workflow**: Combining Python scripts and Power BI dashboards to deliver actionable insights.

The project enables end-to-end CRM data management—from cleaning raw data to building insightful dashboards that track key sales metrics and opportunities.

## Project Components

### 1. **CRM Data Cleaning (Python Notebook)**
The notebook **crm_data_cleaning.ipynb** focuses on:
- Importing CRM datasets (CSV, Excel).
- Cleaning missing, duplicate, or invalid entries.
- Formatting columns and normalizing data.
- Performing exploratory data analysis (EDA).
- Preparing data for modeling and visualization.

#### **Key Steps in the Notebook**:
1. **Data Import**:
   ```python
   import pandas as pd
   data = pd.read_csv('crm_data.csv')
   ```
   - Reads raw data from a CSV file.

2. **Data Cleaning**:
   - Handles missing values:
     ```python
     data.fillna(method='ffill', inplace=True)
     ```
   - Removes duplicates:
     ```python
     data.drop_duplicates(inplace=True)
     ```

3. **Data Transformation**:
   - Normalizes columns for analysis:
     ```python
     data['Revenue'] = data['Revenue'] / 1000
     ```
   - Encodes categorical variables:
     ```python
     data['Region'] = data['Region'].astype('category').cat.codes
     ```

4. **EDA and Visualization**:
   - Summary statistics and anomaly detection.
   - Charts (e.g., revenue distribution):
     ```python
     import matplotlib.pyplot as plt
     data['Revenue'].hist(bins=20)
     plt.show()
     ```

5. **Data Export**:
   - Saves cleaned data for Power BI:
     ```python
     data.to_csv('cleaned_crm_data.csv', index=False)
     ```

### 2. **CRM Sales Dashboard (Power BI Template)**
The **crm_sales_project.pbit** provides dynamic dashboards to visualize cleaned CRM data. Key dashboards include:

#### **Dashboards and Features**:
1. **Sales Overview**:
   - Total revenue, sales growth, and lead conversion rates.
   - Filters: Time period, region, and sales team.

2. **Customer Insights**:
   - Customer segmentation based on revenue and engagement.
   - Drill-through feature for detailed customer profiles.

3. **Opportunity Tracking**:
   - Visualize sales opportunities by stage.
   - Conversion funnel tracking.

4. **Product Performance**:
   - Revenue breakdown by product category.
   - Highlight top-performing products.

5. **Trend Analysis**:
   - Monthly/Quarterly revenue trends.
   - Detect seasonal sales patterns.

#### **Key Technical Features**:
- **Dynamic Filters**: Enable data slicing for detailed insights.
- **Preconfigured Relationships**: Seamlessly integrate multiple tables (customers, sales, opportunities).
- **Customizable Themes**: Adapts to corporate branding.

### 3. **Combined Workflow**
The workflow involves:
1. **Data Cleaning (Python)**:
   - Clean raw CRM data and export as a CSV.
2. **Power BI Integration**:
   - Import cleaned CSV into Power BI.
   - Automatically refresh dashboards for updated insights.

### Folder Structure
```
project-root/
├── crm_data_cleaning.ipynb      # Jupyter Notebook for cleaning data
├── crm_sales_project.pbit       # Power BI template for sales dashboards
├── data/
│   ├── raw/                     # Raw datasets (e.g., CRM exports)
│   ├── cleaned/                 # Cleaned datasets for visualization
├── dashboards/                  # Exported Power BI dashboards
├── README.md                    # Project documentation
```

## Installation

### Prerequisites:
1. **Python Environment**:
   - Python 3.8+
   - Jupyter Notebook
   - Required Libraries: pandas, numpy, matplotlib, seaborn

   Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

2. **Power BI Desktop**:
   - Download from [Power BI](https://powerbi.microsoft.com/desktop/).

### Steps:
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```
2. Open the Jupyter Notebook for data cleaning:
   ```bash
   jupyter notebook crm_data_cleaning.ipynb
   ```
3. Open the Power BI template for visualization:
   ```
   crm_sales_project.pbit
   ```

## Example Workflow
1. **Load Data**:
   - Import your raw CRM data into the Jupyter Notebook.
2. **Clean and Transform Data**:
   - Execute each cell to preprocess the data.
   - Export the cleaned file for use in Power BI.
3. **Visualize in Power BI**:
   - Connect the template to your cleaned dataset.
   - Explore and customize the dashboards.

## Customization
- **Extend Data Cleaning**:
  Add Python scripts to address custom business rules.
- **Modify Dashboards**:
  Update visuals, KPIs, or relationships in Power BI.
- **Automate Refresh**:
  Schedule data refreshes using Power BI Service.

## Contributing
Fork the repository and submit pull requests for:
- New data cleaning modules.
- Enhanced visualizations or dashboards.
