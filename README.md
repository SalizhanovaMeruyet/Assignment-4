# Weather 
Welcome to a  mobile application that displays weather information from various sources. Write the name of your city and know what is the weather outside today.

## Installation and Running Instructions
**Note:** Before starting, make sure you have a valid OpenWeatherMap API key, which you can obtain by signing up on their website (https://openweathermap.org/api). Replace **"YOUR_API_KEY"** with your actual API key in the code.

1. Clone the Repository from GitHub
2. Navigate to the Project Directory
3. Compile the Java Code
4. Run the Application


## How to Use

### Customize the Location (Optional)
You can configure the location for which you want to receive weather data by changing the fetchWeatherData method call in the main function in WeatherAdapter.java file. Replace the name of the location (the place where it written "Astana") in the 64th line with the desired location for which you want to get weather information. Save the changes and re-launch the application using the java Weather Adapter command.

### Viewing weather data
The project will display general weather data in the console, including location, temperature, humidity, and status.



## Main Methods Explanation

The Weather Adapter project consists of two main methods that serve distinct purposes: **‘fetchWeatherData’** and **‘mapToCommonModel’**. These methods are essential for fetching and processing weather data. Below, we provide a detailed explanation of each method's functionality:

### ‘public JSONObject fetchWeatherData(String APIName, String location)’
The **‘fetchWeatherData’** method is responsible for fetching weather data from the OpenWeatherMap API. It takes two parameters:

'APIName': A string specifying the API to be used (in this case, "OpenWeatherMap").
'location': A string representing the location for which you want to fetch weather data.

Here's an overview of how this method works:
1. It checks if the specified 'APIName' is "OpenWeatherMap." If not, it won't proceed with the request.
2. It constructs the API URL with the provided 'location' and a predefined OpenWeatherMap API key.
3. It establishes an HTTP connection to the API using the 'HttpURLConnection' class.
4. It sends a GET request to the API to retrieve weather data.
5. It checks the HTTP response code, and if the response code is 200 (indicating success), it proceeds to process the received data.
6. It reads the response from the API, converts it to a JSON object ('APIData'), and calls the 'mapToCommonModel' method to convert and format the weather data into a common model.
7. It returns the common model JSON object containing temperature, humidity, condition, and location.


### ‘private JSONObject mapToCommonModel(JSONObject apiData)’
The **mapToCommonModel** method is responsible for mapping and formatting the raw weather data obtained from the OpenWeatherMap API into a common model. It takes one parameter:

'apiData': A JSON object representing the raw weather data.

Here's an explanation of how this method functions:
1. It initializes a new JSON object called 'commonData' to store the processed weather data in a common format.
2. It extracts the temperature data from the 'apiData' JSON object and converts it from Kelvin to Celsius by subtracting 273.15. The temperature is then rounded to two decimal places.
3. It retrieves the humidity, condition (weather description), and location from the 'apiData' JSON object.
4. It populates the 'commonData' JSON object with the formatted temperature, humidity, condition, and location data.
5. Finally, it returns the 'commonData' JSON object.


### Running the ‘Main’ Method
The **'public static void main(String[] args)'** method serves as the entry point for executing the Weather Adapter project. It demonstrates how to use the **'fetchWeatherData'** and **'mapToCommonModel'** methods by fetching weather data for a predefined location ("Astana") from the OpenWeatherMap API.

The method does the following:
1. Creates an instance of the 'WeatherAdapter' class.
2. Calls the 'fetchWeatherData method' with "OpenWeatherMap" as the API name and "Astana" as the location.
3. Checks if the weather data was successfully fetched (not null).
4. If data is available, it displays the common weather data, including the location, temperature, humidity, and condition in the console.

This main method provides an example of how to use the Weather Adapter project to fetch and display weather data.




