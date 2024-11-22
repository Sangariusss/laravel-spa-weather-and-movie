# Movies App

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Usage](#usage)
- [File Structure](#file-structure)
- [Contributions](#contributions)
- [License](#license)

## Overview
This project is a simple movie search application built using Laravel. Users can search for movies by title and view details like the year, genre, director, actors, plot, and poster. The app fetches movie data from the OMDB API.

### Features
- **Movie Search**: Users can input a movie title to search for its details.
- **Movie Information**: Displays detailed information including the title, year, genre, director, actors, plot, and poster.
- **Send Movie Details via Email**: Users can send the retrieved movie information, including title, year, genre, and plot, to a specified recipient via email.

## Usage

1. **Setup and Deployment**:
    - Clone the repository to your local machine.
    - Ensure you have PHP 8.3+ installed.
    - Install dependencies by running `composer install` in the project root directory.
    - Set up your `.env` file by copying `.env.example` and adding your OMDB API key:
      ```
      OMDB_API_KEY=your_api_key_here
      ```
    - Run the application using PHP's built-in server or configure it with a web server like Apache or Nginx:
      ```
      php artisan serve
      ```
      This will start the app locally at `http://localhost:8000`.

2. **Interacting with the Application**:
    - **GET** `/`: View the homepage where you can search for movies by title.
    - **POST** `/search`: Submit the movie title to fetch movie details like year, genre, director, actors, plot, and poster.
    - **POST** `/send-email`: Send an email with the movie details to a specified recipient.

## File Structure

- `app/`: Contains the application's logic for controllers, models, and services.
    - `Http/Controllers/`: Contains the controller classes that handle user requests.
        - `MovieController.php`: Handles the logic for searching, displaying movie data, and sending movie information via email.
    - `routes/web.php`: Defines routes for the application.
    - `resources/js/`: Contains JavaScript for handling interactions.
        - `app.js`: The main JavaScript file that imports `bootstrap.js`.
        - `bootstrap.js`: The bootstrap JavaScript file, included to set up the initial JS environment for the app. It configures libraries and resources needed across the app.
    - `resources/css/`: Contains the CSS files for styling the app.
        - `app.css`: The main stylesheet for the application, which imports `styles.css` for additional styles.
        - `styles.css`: Additional styling for customizing the layout and design.

- `resources/views/`: Contains Blade templates for rendering views.
    - `layouts/`: Contains the layout views used across the app.
        - `app.blade.php`: The main layout file that includes shared HTML structure, such as headers, footers, and stylesheets. It serves as a template for other views.
    - `movies/`: Contains the views related to displaying movie information.
        - `index.blade.php`: The homepage that displays the movie search form and results.
        - `result.blade.php`: The view displaying movie details including title, year, genre, director, actors, plot, and poster.
    - `emails/`: Contains the views for sending movie information via email.
        - `movie_result.blade.php`: The email view that sends the movie details to a recipient.

- `tailwind.config.js`: Configuration file for Tailwind CSS, allowing you to customize the default design system. You can extend or override Tailwind's default settings, such as colors, fonts, and responsive breakpoints.

- `vite.config.js`: Configuration file for Vite, which is used to bundle and serve the assets of the application. This file includes configuration for using modern JavaScript features, and it works seamlessly with Tailwind CSS to optimize the development workflow.

- `.env`: Environment configuration file to store your OMDB API key.
- `composer.json`: Composer configuration file for managing PHP dependencies.

## Contributions
Contributions are welcome! If you have any improvements or bug fixes, feel free to fork the repository and submit a pull request. Please also open an issue if you encounter any bugs or have suggestions for new features.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
