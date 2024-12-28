I have built a web page that fetches and displays weather data from a weather API. The application allows users to get weather information based on their current location or by manually entering a location. Below is a summary of the work completed:

Weather Data Fetching:

Integrated an external weather API (e.g., OpenWeatherMap) to fetch real-time weather data based on either the user's location or a manually inputted location.
The data retrieved includes key weather metrics such as temperature, weather conditions, humidity, and the location name.
User Location Detection:

The application uses the browser's navigator.geolocation API to automatically detect and fetch the weather based on the user's current geographic location, ensuring a personalized experience.
The system gracefully handles scenarios where geolocation is not supported or when the user’s location cannot be determined.
User Input for Custom Location:

Users can input a city or place name into a text box. Upon pressing the "Get Weather" button, the app fetches weather data for that specific location from the weather API.
Proper validation is in place to handle cases where the user provides an incorrect or non-existent location.
Weather Information Display:

The application presents the current weather conditions in an easy-to-read format, displaying:
Temperature in Celsius
Weather condition (e.g., clear, cloudy, rainy)
Location name
The app updates dynamically, fetching new data each time the user interacts with it (either through input or location detection).
Error Handling:

Implemented error handling for invalid locations and failed API requests, ensuring the user receives clear feedback when something goes wrong (e.g., invalid location or API failure).
User-Friendly Interface:

Designed a clean and simple user interface with a text input for location entry and a button to trigger the weather data fetch.
Added CSS styling to make the page visually appealing, ensuring the weather data is easy to read and the user experience is intuitive.
Cross-Browser Compatibility:

Ensured the app works across different browsers and devices by using web standards like HTML5, CSS3, and JavaScript.
