Weather Program
Overview

The Weather Program is a Python application designed to interact with the OpenWeatherMap web service to obtain and display weather data. The program prompts the user for their city or zip code and requests weather forecast data, displaying it in a readable format with options for Celsius, Fahrenheit, and Kelvin.
Features

    User input for city or zip code.
    Displays weather information in a readable format.
    Options for temperature units: Celsius, Fahrenheit, and Kelvin.
    Error handling for invalid inputs and connection issues.
    Allows multiple weather lookups in a single session.

Requirements

    Python 3
    Requests library

Installation

    Clone the repository:

    bash

git clone https://github.com/Joven0218/DSC680---Applied-Data-Science.git
cd DSC680---Applied-Data-Science/Weather Program

Install required libraries:

bash

    pip install requests

    Sign up for an API key at OpenWeatherMap.

Usage

Run the program:

bash

python WeatherProgram.py

Follow the prompts to enter a city or zip code and choose the temperature unit. The weather information will be displayed accordingly.
Example

bash

Welcome to WeatherApp! What US city or zip code would you like to see current weather conditions for?
For City, enter the number 1
For Zip Code, enter the number 2
Please choose number 1 or 2: 1
Please enter the city name: New York
What temperature type would you like to see?
Fahrenheit, enter the number 1
Celsius, enter the number 2
Kelvin, enter the number 3
Input temperature type of your choice: 1

Current weather conditions for New York, US in Fahrenheit (°F):
Current Temperature: 75°F
High Temperature: 80°F
Low Temperature: 70°F
Feels Like Temperature: 76°F
Cloud Cover: scattered clouds
Humidity: 65%
Pressure: 1015hPa
Wind Speed: 10mph

Notes

    Replace the placeholder API key in the code with your actual API key from OpenWeatherMap.
    Ensure proper error handling for invalid city names or zip codes and unsuccessful API requests.

Conclusion

This weather program is a practical application that demonstrates how to interact with web services, handle user input, and display data in a user-friendly format.
