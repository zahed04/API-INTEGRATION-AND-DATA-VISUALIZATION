# API-INTEGRATION-AND-DATA-VISUALIZATION

COMPANY:CODETECH IT SOLUTIONS

NAME:ZAHED HUSSAIN

INTERN ID:CT04DZ1510

DOMAIN:PYTHON PROGRAMMING

DURATION:4 WEEKS

MENTOR:NEELA SANTOSH

DESCRIPTION:
Weather Forecast Dashboard Script Overview
This Python script fetches and visualizes a 5-day weather forecast for a given city using data from the OpenWeatherMap API. It processes the forecasted weather data and presents it through two visual plots: a temperature trend and a combined humidity/condition chart. The visualizations help users intuitively understand weather changes over time.

🧰 Tools and Libraries Used
1. requests
Purpose: Makes HTTP requests to external APIs.

Used For: Sending a GET request to the OpenWeatherMap API to retrieve forecast data in JSON format.

This library is essential for connecting your Python application to any web-based API.

2. datetime
Purpose: Handles date and time manipulation in Python.

Used For: Converting UNIX timestamps (provided by the API) into human-readable datetime objects.

This makes time data usable and readable on the x-axis of the plots.

3. matplotlib.pyplot
Purpose: The foundational Python plotting library.

Used For: Creating and customizing figures and axes for line and scatter plots.

Handles layout settings like figure size, subplot arrangement, and axis labeling.

4. seaborn
Purpose: A statistical data visualization library built on top of Matplotlib.

Used For:

Plotting aesthetically pleasing line charts and scatter plots.

Applying a dark grid theme to enhance readability.

Seaborn is especially helpful for quick exploratory data analysis (EDA).

🌐 API Interaction
OpenWeatherMap API:
The script uses the 5-day forecast endpoint, which provides weather data in 3-hour intervals.

You specify:

City name (e.g., 'London')

API key (required to authenticate)

Units (metric for Celsius, imperial for Fahrenheit)

python
Copy
Edit
url = f'https://api.openweathermap.org/data/2.5/forecast?q={CITY}&appid={API_KEY}&units={UNITS}'
response = requests.get(url)
data = response.json()
🔍 Data Extraction and Preparation
From the returned JSON data:

Timestamps are extracted and converted using datetime.fromtimestamp()

Temperature, humidity, and main weather condition (e.g., Rain, Clouds) are pulled from nested dictionaries inside each forecast entry.

All data is stored in separate lists:

python
Copy
Edit
times, temperatures, humidities, conditions
These are used as the basis for plotting.

📊 Data Visualization
Plot 1: Temperature Trend
A line plot showing how temperature fluctuates over the 5-day period.

sns.lineplot() is used for a smooth visual.

The x-axis is rotated for clarity since the timestamps are dense.

Plot 2: Humidity + Weather Conditions
A dual-axis chart:

Left Y-axis: Humidity line plot

Right Y-axis: Weather conditions as a categorical scatter plot

twinx() is used to allow two different y-axis scales on the same subplot.

Conditions are displayed using colored scatter points (e.g., "Clear", "Rain").

🎓 What You Learn From This Script
How to consume REST APIs:

Use the requests library to pull live data from OpenWeatherMap or similar services.

Parsing JSON structures:

Extract nested values such as timestamps and weather parameters.

Working with timestamps:

Convert and format UNIX timestamps to readable formats using datetime.

Visualizing time series data:

Plot meaningful trends using seaborn and matplotlib.

Handle axis rotation and labeling for better readability.

Dual-axis plots:

Use twinx() to visualize different data scales on the same timeline.

✅ Conclusion
This weather dashboard is a compact yet powerful example of integrating API consumption, data processing, and visualization. It's ideal for developers and analysts who want to learn how to:

Build real-time data dashboards,

Work with public APIs,

Create insightful visuals for presentations or reports

OUTPUT:

