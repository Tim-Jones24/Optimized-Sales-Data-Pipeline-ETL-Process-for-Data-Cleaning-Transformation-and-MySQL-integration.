# Optimized Sales Data Pipeline: ETL Process for Data Cleaning Transformation and MySQL integration
This ETL(Extract, Transform, Load) project is designed to clean, transform, and enrich sales data from multiple Excel sources before loading it into a MySQL database for efficient querying and analysis.


#### Overview
This project is an ETL pipeline designed to extract, clean, and transform sales storing it in a MySQL database. The goal is to ensure data accuracy,integrity, and usability for business analytics and reporting. The project addresses common data quality issues such as missing values, inconsistent data entries, incorrect formatting, and enhances readability by deriving meaningful insights. The goal is to provide businessess with structured and accurate data,enabling informed decision-making.

#### Technologies and Libraries Used
* **Pandas**: Data manipulation and transformation
* **Openpyxl**: Reading Excel files
* **MySQL Connector,PyMySQL, and SQLAlchemy**: Database connection and loading into MySQL
* **Calendar**: Deriving month names from numerical month values
* **Regular Expressions (re)**: Cleaning and formatting data values

#### Data Overview
The project processes two datasets with the following columns:

* **City**: Locations of coffee shops(Southampton,Blackpool,Portsmouth) with spelling corrections.
  * **Transformation**: Standardized naming conventions.

* **Year**: Sales year (2020-2022).
  * **Transformation**: Fixed incorrect entries(e.g., "2032" corrected to "2022").
 
* **Month**: Unique month number (1-12).
  * **Transformation**: Extracted missing values during preprocessing.

* **Product**: Various product categories (Coffee,Cakes,Pastry, etc.).
  * **Transformation**: Renamed from "Product Category" for clarity.
 
* **Quantity**: Sales volume of each product.
  * **Transformation**: Renamed from "Sales Volume Sales".
 
* **Value**: Revenue of each product.
  * **Transformation**: Cleaned by removing the "£" the delimeter.
 
* **Month_Name**: Derived column for readability (January- December).

 
 #### ETL Process Breakdown
  1. **Extraction**:
      * Loaded data from Excel files using Pandas and Openpyxl.

 2. **Transformation**:
      * Cleaned incorrect city names.
      * Corrected erroneous year values.
      * Derived msiing month values.
      * Standardized product categories and column names.
      * Converted numerical types to integers for accurate analysis.
      * Used regular expressions to clean the revenue column by removing the "£" delimeter.
      * Enriched data by generating **Month Name** using Lambda functions and the Calendar libary.
      * Consolidated data into **single DataFrame** for a unified dataset.

 3. **Loading**:
      * Established a connection to MySQL using **SQLAlchemy, MySQL Connector, and PyMySQL**.
      * Inserted the cleaned and structured data into a MySQL table for efficient querying.
   
#### **Importance of This Project to Businessess and Organizations**:

1. **Improved Data Quality**:
    * Corrects inconsistencies in city names, product categories and sales years.
    * Removes outliers and ensures clean, standardized data.
      
2. **Enahanced Readability and Usability**:
    * Derives **Month Names** from numerical values for better reporting.
    * Converts data types to appropriate formats (e.g., sales volume as integers).
      
3. **Efficient Storage and Retrieval**:
    * Loads cleaned and structured data into a **MySQL database** for fast querying.
    * Enalbles businessess to track sales performance across locations, time periods, and product categories.
      
4. **Scalability and Integration**:
    * Provides a structured data pipeline that can be extended for support additional data sources or analytics tools.

#### Conclusion:
This ETL pipeline ensures data consistency, reliablity, and accessibility empowering businessess with accurate insights for better decision-making.
