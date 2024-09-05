
# Redbus Data Scraping with Selenium & Dynamic Filtering using Streamlit

## Overview

This project aims to revolutionize the transportation industry by providing a comprehensive solution for collecting, analyzing, and visualizing bus travel data. Through the use of Selenium for web scraping, this project automates the extraction of detailed information from Redbus, including bus routes, schedules, prices, and seat availability. By streamlining data collection and offering powerful data-driven tools, the project enables improved operational efficiency and strategic decision-making in the transportation sector.

## Table of Contents

- [Usage](#usage)
- [Approach](#approach)
- [Technology Used](#technology-used)
- [Installation](#installation)
- [Results](#results)
- [References](#references)

## Usage

This solution can be applied in various business scenarios, such as:

- **Travel Aggregators**: Offering real-time bus schedules and seat availability for customers.
- **Market Analysis**: Analyzing travel patterns and preferences for market research.
- **Customer Service**: Enhancing user experience with customized travel options based on data insights.
- **Competitor Analysis**: Comparing pricing and service levels with competitors.

## Approach

1. **Data Scraping**  
   Automate the extraction of Redbus data, including routes, schedules, prices, and seat availability using Selenium.

2. **Data Storage**  
   Store the scraped data in a SQL database for further processing.

3. **Streamlit Application**  
   - Develop an interactive Streamlit application to display and filter the scraped data.
   - Implement filters for bus type, route, price range, star rating, and seat availability.

4. **Data Analysis**  
   - Use SQL queries to retrieve and filter data based on user inputs.
   - Allow users to interact with and filter data through the Streamlit application.

## Technology Used

Before starting, ensure you have the following installed:

- **Python 3.x**: A versatile programming language widely used for web scraping, data analysis, and web application development.
- **ChromeDriver**: A separate executable that Selenium WebDriver uses to control Chrome for automating web tasks.
- **Selenium**: A powerful tool for web automation that enables programmatic control of web browsers, crucial for web scraping.
- **SQLite3**: A lightweight SQL database engine known for its simplicity and portability.
- **Streamlit**: A tool for displaying and filtering scraped data in a web interface.

## Installation

### I. Selenium

Selenium enables the automation of web browsers for tasks like web scraping and testing.

**Setup Selenium:**

1. Install the Selenium package:
   ```bash
   pip install selenium
   ```

2. Download and set up the appropriate browser drivers (e.g., ChromeDriver). [Driver download links](https://pypi.org/project/selenium/#drivers).

### II. SQLite

SQLite3 is used as the database engine for storing scraped data. You can manage SQLite databases using DB Browser for SQLite.

**Setup SQLite:**

1. Install SQLite or use DB Browser for SQLite for a graphical interface.
2. Connect to the database and create a table:
   ```python
   conn = sqlite3.connect('redbus.db')
   c = conn.cursor()

   # Create table
   c.execute('''
   CREATE TABLE IF NOT EXISTS redbuscsv (
       route_name TEXT,
       route_url TEXT,
       bus_name TEXT,
       departure TEXT,
       arrival TEXT,
       depart_time TEXT,
       arrival_time TEXT,
       duration TEXT,
       bus_type TEXT,
       star_rating TEXT,
       price TEXT,
       seats_available TEXT
   )
   ''')

   # Commit and close connection
   conn.commit()
   conn.close()
   ```

### III. Streamlit

Streamlit allows you to turn Python scripts into interactive web applications.

**Install Streamlit:**
```bash
pip install streamlit
```

**Example Usage:**

Create a new file called `streamlit_app.py` with the following code:
```python
import streamlit as st
x = st.slider("Select a value")
st.write(x, "squared is", x * x)
```

Run the application:
```bash
streamlit run streamlit_app.py
```

Visit the Streamlit [documentation](https://docs.streamlit.io/get-started) for more details.

## Results

The key objectives of this project include:

- Successfully scraping data from a minimum of 10 government state bus transport services on the Redbus website using Selenium, alongside private bus data for the selected routes.
- Storing the data in a structured SQL database.
- Developing an interactive and user-friendly Streamlit application for data filtering.
- Ensuring the application delivers a seamless user experience and operates efficiently.

### Evaluation Criteria

- **Data Scraping Accuracy**: The completeness and correctness of the scraped data.
- **Database Design**: The effectiveness and efficiency of the database schema.
- **Application Usability**: The user experience and ease of use of the Streamlit application.

## References

- [Selenium Documentation](https://www.selenium.dev/documentation/webdriver/elements/locators/)
- [SQL Documentation](https://dev.mysql.com/doc/)
- [Streamlit Documentation](https://docs.streamlit.io)
```
