````markdown
# Practical Lab Assignment: Weather Dashboard Application

**Student Name:** Rakhib Khan  
**Subject:** JavaScript  
**Project Name:** ClearSky Weather Dashboard  

---

## 1. Project Overview

This project is a responsive, single-page weather application built using **Vanilla JavaScript**, **HTML5**, and **Tailwind CSS**. The application fetches real-time weather data, air quality indices, and forecasts for any location worldwide without requiring backend servers or API keys.

The primary goal of this assignment was to demonstrate proficiency in:

- Asynchronous JavaScript (async/await)
- Fetching data from external APIs
- DOM Manipulation
- Browser Local Storage
- Geolocation API
- Favorites management

---

## 2. Key Features

- **Real-Time Weather:** Displays current temperature, weather condition, humidity, wind speed, and rain probability.
- **Air Quality Index (AQI):** Visual indicator (Green / Yellow / Red) for air quality.
- **7-Day Forecast:** Horizontal scrollable list (mobile) or grid layout (desktop).
- **Geolocation:** Automatically detects the user's position using the browser's Geolocation API.
- **City Search:** Allows users to search for any city globally via the Open-Meteo Geocoding API.
- **Favorites System:** Users can star locations. Favorites are saved in localStorage and persist after browser restarts.
- **Responsive UI:** Fully adaptive interface built using Tailwind CSS.

---

## 3. Technologies Used

- **HTML5:** Semantic structure
- **Tailwind CSS:** Utility-first styling for layout and responsiveness
- **JavaScript (ES6+):** Core logic, API handling, and state management
- **External APIs (Open Source):**
  - Open-Meteo – Weather and AQI data
  - BigDataCloud – Reverse Geocoding (Latitude/Longitude to City Name)
- **Phosphor Icons:** Visual weather representations

---

## 4. How to Run

1. Download the `index.html` file.
2. Open it in any modern web browser (Chrome, Firefox, Edge).

**Note:**  
No installation or local server is strictly required. However, using a Live Server extension is recommended for optimal Geolocation API support.

---

## 5. Code Explanation & Implementation Details

### A. Geolocation Logic

The application initializes by requesting the user's location using the browser’s Geolocation API.

```javascript
navigator.geolocation.getCurrentPosition(
  (position) => {
    // Success: Fetch weather for coordinates
  },
  (error) => {
    // Error: Fallback to default city
  }
);
````

---

### B. Asynchronous Data Fetching

The app uses async/await with Promise.all to fetch weather and AQI data simultaneously.

```javascript
async function fetchWeatherData() {
  const [weatherRes, aqiRes] = await Promise.all([
    fetch(weatherUrl),
    fetch(aqiUrl)
  ]);

  // Parse JSON and update UI
}
```

---

### C. Dynamic DOM Manipulation

The 7-day forecast is generated dynamically using JavaScript loops instead of hardcoded HTML.

```javascript
for (let i = 0; i < 7; i++) {
  const card = document.createElement('div');
  card.innerHTML = `Forecast for day ${i + 1}`;
  forecastContainer.appendChild(card);
}
```

---

### D. Local Storage (Favorites)

Favorites are stored persistently using the browser’s localStorage.

```javascript
// Save favorites
localStorage.setItem('cs_favorites', JSON.stringify(favorites));

// Load favorites on startup
const favorites = JSON.parse(localStorage.getItem('cs_favorites')) || [];
```

---

### E. Search Functionality

The search bar converts a city name into latitude and longitude using the Geocoding API, then fetches weather data for that location.

---

## 6. Conclusion

This lab assignment successfully implements a functional, API-driven web application. It demonstrates modern frontend development practices, including asynchronous operations, dynamic UI rendering, error handling, and persistent user preferences.

```

---

If you want, I can:
- Align this **exactly to your college lab rubric**
- Shorten it to **fit page limits**
- Convert it to **PDF / DOCX**
- Rewrite it in a **more “examiner-friendly” tone**

Just say the word.
```
