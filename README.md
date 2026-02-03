Big Data Analysis using PySpark – E-Commerce Sales

📌 Project Overview
    This project demonstrates scalable data analysis using PySpark on a large e-commerce transaction dataset. The objective is to perform end-to-end data profiling, cleaning, feature engineering, and business analysis on a high-volume dataset and derive meaningful business insights using distributed processing.

The project is designed as an internship-level big data analytics task, focusing on correctness, scalability, and explainability rather than unnecessary complexity.

📂 Dataset
      Source: Kaggle – Online Retail Dataset
      Description: Transaction-level e-commerce data containing invoice details, products, quantities, prices, customers, countries, and order dates.
      Size:
        Raw dataset (augmented for learning): ~1.5 million rows
        Cleaned dataset: ~723K rows

  Note: The dataset was lightly augmented with additional inconsistent records to demonstrate real-world data cleaning scenarios. The original dataset source remains Kaggle.

🛠️ Tools & Technologies
    Python
    PySpark
    Google Colab
    Parquet (for optimized storage)

🔎 Project Workflow
    1. Data Loading & Profiling
        Loaded large CSV dataset using PySpark
        Inspected schema, datatypes, and row counts
        Verified time range of the data (Dec 2010 – Dec 2011)
        Identified duplicates, null values, and invalid records
    
    2. Data Cleaning & Standardization
        Removed fully duplicated records
        Filtered invalid transactions (zero or negative quantity and unit price)
        Handled missing customer identifiers by labeling them as “Guest”
        Standardized country values for consistency:
            RSA → South Africa
            EIRE → Ireland
            European Community → EU-Other
            Unspecified → Unknown
        Performed post-cleaning validation checks to ensure data quality
    
    3. Feature Engineering
        Created derived columns for analysis:
            Revenue
            Year
            MonthNo
            MonthName
            year_month
        Cached the cleaned dataset for performance optimization
    
    4. Business Analysis & KPIs
        Key metrics and analysis performed:
            Total Orders
            Total Revenue
            Total Quantity Sold
            Average Order Value (AOV)
            Best-selling products (by quantity and revenue)
            Top customers by revenue
            Best-performing countries
            Monthly revenue trends
            Top-performing products per country using window functions
        Revenue values were formatted into human-readable units (K, M, B) for better interpretability.
    
    5. Advanced Analysis
        Used window functions (row_number) to identify:
            Top-revenue product per country
            Top-selling product per country by quantity
        This enabled group-level ranking without collapsing detailed data.
    
    6. Data Persistence
        The cleaned and enriched dataset was saved in Parquet format to demonstrate performance-optimized storage commonly used in big data pipelines.

📈 Key Insights
    ~20K orders generated 15.2M revenue from 8.23M units sold
    A small number of products contribute disproportionately to total sales
    Guest customers account for a significant share of revenue, indicating strong anonymous purchasing behavior
    The United Kingdom is the dominant market in both volume and revenue
    Revenue peaks in November 2011, highlighting seasonal demand patterns

✅ Conclusion
    This project showcases how PySpark can be effectively used for large-scale data cleaning and analysis on e-commerce transactions. By leveraging distributed processing, aggregation, and window functions, the analysis delivers actionable insights into product performance, customer behavior, and seasonal trends, demonstrating real-world big data analytics practices.


📌 How to Run the Project
    Open the notebook in Google Colab
    Install PySpark
    Upload the dataset
    Run the notebook top-to-bottom

👤 Author
Harshitha Salian
Aspiring Data Analyst | SQL | Excel | Power BI | Python
