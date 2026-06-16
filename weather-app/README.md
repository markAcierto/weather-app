# Daily Weather App

A simple web application that shows the daily weather for your current location using the OpenWeatherMap API.

## Features

- Automatically detects your location using the Geolocation API
- Displays current temperature, weather description, humidity, and wind speed
- Simple, clean, and responsive design

## How to Use

1. **Get an OpenWeatherMap API Key**:
   - Sign up for a free account at [OpenWeatherMap](https://openweathermap.org/api)
   - Create an API key (free tier available)

2. **Configure the API Key**:
   - Open `index.html` in a text editor
   - Replace `'YOUR_OPENWEATHERMAP_API_KEY'` with your actual API key
   - Save the file

3. **Run the App**:
   - Open `index.html` in any modern web browser
   - Allow the browser to access your location when prompted
   - The weather information for your location will be displayed

## File Structure

- `index.html`: Main HTML file containing the app structure, styling, and JavaScript
- `README.md`: This file

## How It Works

1. When the page loads, it requests access to your location using the Geolocation API
2. Once location is obtained, it fetches weather data from the OpenWeatherMap API using your latitude and longitude
3. The weather data is then displayed in a user-friendly format

## Customization

- To change the temperature units (metric/imperial), modify the `units` parameter in the API URL
- To change the styling, edit the CSS within the `<style>` tag in `index.html`
- To display additional weather data, modify the JavaScript to use other fields from the API response

## Note

- The OpenWeatherMap API key should be kept private. In a production environment, you would want to use a backend server to hide the API key.
- For demonstration purposes, this client-side implementation is sufficient.

## Browser Support

This app uses modern web APIs and should work in:
- Chrome
- Firefox
- Safari
- Edge
- Any browser that supports Geolocation API and Fetch API

## License

This project is open source and available under the MIT License.