# Weather App

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Contributions](#contributions)
- [License](#license)

## Overview
This project is a simple weather application built using Laravel. It allows users to enter a city name and view current and forecasted weather for the selected city. The app fetches weather data from the OpenWeatherMap API.

### Features
- **Current Weather**: Users can view the current weather for a specific city.
- **5-Day Forecast**: Users can view a 5-day weather forecast for the city they input.
- **Weather Icons**: Displays weather icons fetched from OpenWeatherMap.
- **Location Search**: Users can input any city name to fetch its weather details.

## Usage

1. **Setup and Deployment**:
    - Clone the repository to your local machine.
    - Ensure you have PHP 8.3+ installed.
    - Install dependencies by running `composer install` in the project root directory.
    - Set up your `.env` file by copying `.env.example` and adding your OpenWeatherMap API key:
      ```
      OPENWEATHERMAP_API_KEY=your_api_key_here
      ```
    - Run the application using PHP's built-in server or configure it with a web server like Apache or Nginx:
      ```
      php artisan serve
      ```
      This will start the app locally at `http://localhost:8000`.

2. **Interacting with the Application**:
    - **GET** `/`: View the homepage, where you can input a city to fetch current weather and forecast.
    - **POST** `/weather/today`: Fetch the current weather for the specified city.
    - **POST** `/weather/weekly`: Fetch the 5-day forecast for the specified city.

## File Structure

- `app/`: Contains the application's logic for controllers, models, and services.
    - `Http/Controllers/`: Contains the controller classes that handle user requests.
        - `WeatherController.php`: Handles the logic for fetching and displaying weather data.
    - `routes/web.php`: Defines routes for the application.
    - `resources/js/`: Contains JavaScript for handling interactions.
        - `app.js`: The main JavaScript file that imports `bootstrap.js`.
        - `bootstrap.js`: The bootstrap JavaScript file, included to set up the initial JS environment for the app. It configures libraries and resources needed across the app.
    - `resources/css/`: Contains the CSS files for styling the app.
        - `app.css`: The main stylesheet for the application, which imports `styles.css` for additional styles.
        - `styles.css`: Additional styling for customizing the layout and design.

- `resources/views/`: Contains Blade templates for rendering views.
    - `layouts/app.blade.php`: The main layout file that includes shared HTML structure, such as headers, footers, and stylesheets. It serves as a template for other views.
    - `home.blade.php`: The homepage that displays the weather form and results.
    - `today.blade.php`: The view displaying today's weather details.
    - `weekly.blade.php`: The view displaying the 5-day weather forecast.

- `tailwind.config.js`: Configuration file for Tailwind CSS, allowing you to customize the default design system. You can extend or override Tailwind's default settings, such as colors, fonts, and responsive breakpoints.

- `vite.config.js`: Configuration file for Vite, which is used to bundle and serve the assets of the application. This file includes configuration for using modern JavaScript features, and it works seamlessly with Tailwind CSS to optimize the development workflow.

- `.env`: Environment configuration file to store your OpenWeatherMap API key.
- `composer.json`: Composer configuration file for managing PHP dependencies.

## Contributions
Contributions are welcome! If you have any improvements or bug fixes, feel free to fork the repository and submit a pull request. Please also open an issue if you encounter any bugs or have suggestions for new features.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
