# 30 Days DevOps Challenge - Weather Dashboard
## Day 1: Building a weather data collection system using AWS S3 and OpenWeather API

### Weather Data Collection System - DevOps Day 1 Challenge

### Project Overview
This project is a Weather Data Collection System that demonstrates core DevOps principles by combining:

* External API Integration (OpenWeather API)
* Cloud Storage (AWS S3)
* Infrastructure as Code
* Version Control (Git)
* Python Development
* Error Handling
* Environment Management

### Features
* Fetches real-time weather data for multiple cities
* Displays temperature (°C), humidity, and weather conditions
* Automatically stores weather data in AWS S3
* Supports multiple cities tracking
* Timestamps all data for historical tracking

### Technical Architecture
* Language: Python 3.x
* Cloud Provider: AWS (S3)
* External API: OpenWeather API

#### Dependencies:
boto3 (AWS SDK)
python-dotenv
requests

## Code Explanation 
This script defines a WeatherDashboard class that interacts with both the OpenWeather API and AWS S3 to fetch and store weather data for specific cities. Here's a quick summary:

Imports: Essential libraries for interacting with the environment variables (os, dotenv), AWS S3 (boto3), making HTTP requests (requests), and working with JSON and date-time data.

Environment Setup: It loads environment variables using load_dotenv() for sensitive info like the API key and AWS bucket name.

Class Initialization: The WeatherDashboard class initializes with an OpenWeather API key and an S3 bucket name, setting up an S3 client using boto3.

Bucket Creation: In the create_bucket_if_not_exists method, the script checks if the S3 bucket exists and creates it if not.

Fetch Weather Data: The fetch_weather method queries the OpenWeather API to retrieve weather information for a given city and returns the response as JSON.

Save Data to S3: The save_to_s3 method saves the fetched weather data to an S3 bucket, appending a timestamp to the file name and ensuring the data is saved as a JSON object.

Main Execution: In the main() function, the script initializes a WeatherDashboard object, creates the S3 bucket if needed, and fetches and prints weather data for a predefined list of cities ("Toronto", "Ottawa", "Barrie"). The weather data is also saved to S3.

Execution Check: The script runs the main() function if executed directly.

This code allows the automated fetching, display, and storage of weather data for specified cities.

```
## Project Structure
weather-dashboard/
  src/
    __init__.py
    weather_dashboard.py
  tests/
  data/
  .env
  .gitignore
  requirements.txt

## Setup Instructions
1. Clone the repository:
--bash
git clone https://github.com/ShaeInTheCloud/30days-weather-dashboard.git

3. Install dependencies:
bashCopypip install -r requirements.txt

4. Configure environment variables (.env):
CopyOPENWEATHER_API_KEY=your_api_key
AWS_BUCKET_NAME=your_bucket_name

4.Configure AWS credentials:
bashCopyaws configure

5. Run the application:
python src/weather_dashboard.py

What I Learned

AWS S3 bucket creation and management
Environment variable management for secure API keys
Python best practices for API integration
Git workflow for project development
Error handling in distributed systems
Cloud resource management

Future Enhancements

Add weather forecasting
Implement data visualization
Add more cities
Create automated testing
Set up CI/CD pipeline
```