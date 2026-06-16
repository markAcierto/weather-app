# Weather App Visual Upgrade Plan

## Goal
Upgrade the visual appearance of the weather app in `index.html` with dynamic backgrounds, glassmorphism, weather icons, and animations.

## Implementation Details

### 1. Glassmorphism Design
Update the `.container` to create a "frosted glass" effect.
- **Properties**:
    - `background: rgba(255, 255, 255, 0.2)` (Semi-transparent white)
    - `backdrop-filter: blur(10px)` (Blurring the background)
    - `-webkit-backdrop-filter: blur(10px)` (Safari support)
    - `border: 1px solid rgba(255, 255, 255, 0.3)` (Subtle light border)
    - `box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37)` (Soft shadow for depth)
    - `border-radius: 15px` (Softer corners)
    - `color: white` (Ensure text visibility on dynamic backgrounds)

### 2. Dynamic Backgrounds
Change the `body` background based on the weather condition returned by OpenWeatherMap (`data.weather[0].main`).

- **Mapping Logic**:
    - `Clear` $\rightarrow$ `linear-gradient(to bottom, #4facfe 0%, #00f2fe 100%)`
    - `Clouds` $\rightarrow$ `linear-gradient(to bottom, #bdc3c7, #2c3e50)`
    - `Rain` $\rightarrow$ `linear-gradient(to bottom, #485563, #29323c)`
    - `Snow` $\rightarrow$ `linear-gradient(to bottom, #e6e9f0, #eef1f5)`
    - `Thunderstorm` $\rightarrow$ `linear-gradient(to bottom, #0f0c29, #302b63, #24243e)`
    - `Drizzle` $\rightarrow$ `linear-gradient(to bottom, #bdc3c7, #2c3e50)`
    - `Mist`/`Smoke`/`Haze` $\rightarrow$ `linear-gradient(to bottom, #757f9a, #d7dde8)`
    - Default $\rightarrow$ `linear-gradient(to bottom, #f0f8ff, #add8e6)`

- **CSS Transition**:
    - Add `transition: background 0.5s ease;` to `body` for smooth transitions between weather states.

### 3. Weather Icons
Integrate OpenWeatherMap's icon set.
- **HTML**: Add `<img id="weather-icon" src="" alt="Weather Icon">` inside `#weather-info`.
- **JS**: In `displayWeather`, update the image source using the icon code:
  `img.src = \`https://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png\`;`

### 4. Fade-in Animations
Add a smooth entry animation when the weather data is loaded.
- **CSS**:
    - Define `@keyframes fadeIn`:
      ```css
      @keyframes fadeIn {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
      }
      ```
    - Apply to `#weather-info`:
      - `opacity: 0;` (initial state)
      - `animation: fadeIn 0.6s ease-out forwards;` (applied when `display: block` is set in JS)

---

## Step-by-Step Execution Plan

### Step 1: HTML Modifications
- [ ] Add the weather icon image element inside the `#weather-info` div.

### Step 2: CSS Enhancements
- [ ] Update `body` styles: remove static background, add transition.
- [ ] Apply glassmorphism properties to `.container`.
- [ ] Update typography colors for better contrast (white/light grey).
- [ ] Define the `fadeIn` keyframes.
- [ ] Set the initial state and animation for `#weather-info`.

### Step 3: JavaScript Logic Implementation
- [ ] Create the weather-to-background mapping object.
- [ ] Update `displayWeather(data)` to:
    - Set the `src` for the `#weather-icon` element.
    - Apply the corresponding gradient to `document.body.style.background`.
    - Ensure `#weather-info` transition triggers correctly.

## Critical Files
- `index.html`
EOF`
