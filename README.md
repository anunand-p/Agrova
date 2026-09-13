# Agrova

Agrova is a browser-based AI farming assistant for plant disease detection and crop care. Farmers can upload a leaf image or use a camera, receive a Teachable Machine prediction, review treatment guidance, calculate spray dosage, inspect weather risk, and ask the farming assistant questions.

## Current Features

- Leaf disease detection from uploaded images.
- Camera capture with front/rear camera switching.
- Teachable Machine image model integration.
- Confidence score and low-confidence warning.
- Disease-specific remedies and prevention guidance.
- Scan history stored in browser local storage.
- Printable Agrova diagnostic health card.
- WhatsApp sharing and browser voice readout.
- Spray dosage calculator for cents, acres, and hectares.
- Weather and fungal-risk advisory by Kerala district.
- Crop calendar for tomato, banana, chilli, and ginger.
- Disease reference gallery.
- Nearby agricultural shop search using geolocation and Google Maps.
- Farming chatbot with text input, voice input, multiple languages, and voice output.
- English, Malayalam, Hindi, Tamil, and Telugu interface options.
- Dark mode, glassmorphism styling, responsive layout, and mobile navigation.

## Project Structure

```text
Agrova/
|-- index.html    Main application, styles, markup, and JavaScript
|-- README.md     Project documentation
```

This is currently a single-file frontend application. No build step or package installation is required for the basic experience.

## Run Locally

Because camera and geolocation features work more reliably over HTTP, serve the folder with a local web server instead of opening the file directly.

### Python

```bash
python -m http.server 8765 --directory .
```

Open:

```text
http://127.0.0.1:8765/index.html
```

### VS Code Live Server

1. Open the project folder in VS Code.
2. Install or use the Live Server extension.
3. Right-click `index.html`.
4. Select **Open with Live Server**.

## Browser Requirements

- A modern browser with JavaScript enabled.
- Camera permission for camera scanning.
- Location permission for nearby shops and live weather lookup.
- Internet access for TensorFlow.js, the Teachable Machine model, Google Fonts, maps, weather data, and chatbot requests.
- A secure context such as `localhost` or HTTPS for camera and geolocation APIs.

## External Services

The application currently uses:

- TensorFlow.js from jsDelivr.
- Teachable Machine image model hosting.
- Open-Meteo weather API.
- Google Maps Embed API.
- A Cloudflare Worker chatbot endpoint.
- Google Fonts.

If any external service is unavailable, the related feature may fail while the rest of the interface continues to work.

## Important Limitations

- AI predictions are estimates and are not a replacement for a local agronomist or laboratory diagnosis.
- Remedy and dosage information must be checked against the pesticide label and local agricultural regulations.
- Weather district values are demo or advisory data unless refreshed through the live weather flow.
- Scan history is local to the current browser and device.
- The chatbot requires the configured worker endpoint and internet access.
- A Google Maps API key and service endpoints are visible in client-side code. This is not suitable for production deployment without server-side protection and key restrictions.
- The current disease model supports only the classes included in its Teachable Machine metadata.

## Recommended Next Features

### Priority 1: Production Safety

1. Move Google Maps and chatbot credentials behind a backend or serverless proxy.
2. Restrict API keys by domain, API, quota, and referrer.
3. Add request timeouts, retry handling, and offline error states.
4. Add server-side logging without storing private images or location data unnecessarily.
5. Add a clear consent notice before using camera, location, or voice features.

### Priority 2: Better Diagnosis

1. Add image quality checks for blur, darkness, and leaf visibility before prediction.
2. Show the top three predictions instead of only the highest prediction.
3. Add crop selection before analysis to improve model accuracy.
4. Add a feedback workflow for incorrect predictions.
5. Expand and version the disease model with verified regional images.
6. Add a recommendation to consult an expert when confidence is low or symptoms are severe.

### Priority 3: Farmer Workflow

1. Add editable crop, farm, and location profiles.
2. Add scheduled reminders for scouting, watering, and treatment follow-up.
3. Add a treatment log with product, date, dosage, and application status.
4. Allow history export as CSV or PDF.
5. Add cloud sync with optional account login.
6. Add offline support as a Progressive Web App.

### Priority 4: User Experience

1. Add real plant images to the disease gallery.
2. Replace emoji-only controls with a consistent icon set and tooltips.
3. Add a clearer first-use empty state and a sample image option.
4. Improve translations across all sections, not only the primary detection flow.
5. Add keyboard-friendly star ratings and more complete screen-reader labels.
6. Add loading, offline, permission-denied, and service-unavailable states consistently.

### Priority 5: Local Agriculture Intelligence

1. Add district-specific crop calendars and regional disease alerts.
2. Add local-language treatment instructions reviewed by agricultural experts.
3. Add nearby Krishi Bhavan, KVK, and certified input dealer data.
4. Add crop-stage-aware dosage guidance.
5. Add rainfall forecasts and treatment-window recommendations.

## Safety Notice

Always follow the product label, wear appropriate protective equipment, observe pre-harvest intervals, and consult a qualified agricultural professional before applying pesticides or treating severe crop disease.
