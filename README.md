# Agrova

Agrova is a hackathon-ready browser-based AI farming assistant for plant disease detection and crop care. Farmers can upload a leaf image or use a camera, receive a Teachable Machine prediction, review treatment guidance, calculate spray dosage, inspect weather risk, and ask the farming assistant questions.

## Summary

Agrova turns a single leaf photo into a practical crop-care workflow. The prototype combines AI-assisted diagnosis, local-language access, treatment guidance, weather context, dosage calculation, and treatment-history export in one responsive interface designed for farmers.

### Demo Flow

1. Select the crop and upload a clear leaf image, or capture one with the camera.
2. Review the predicted disease, confidence level, severity, and recommended remedies.
3. Use the weather advisory and dosage calculator to plan the next action.
4. Save the treatment record and export the history as CSV or printable PDF.
5. Ask the multilingual farming assistant for additional crop-care guidance.

### Highlights

- Solves a clear field problem: early disease awareness and actionable next steps.
- Works as a lightweight single-page application with no build setup.
- Supports English, Malayalam, Hindi, Tamil, and Telugu experiences.
- Combines AI, camera, voice, geolocation, weather, and export workflows.
- Includes permission consent, low-confidence messaging, safety guidance, and responsive mobile UI.

## Current Features

- Leaf disease detection from uploaded images.
- Camera capture with front/rear camera switching.
- Teachable Machine image model integration.
- Confidence score and low-confidence warning.
- Disease-specific remedies and prevention guidance.
- Scan history stored in browser local storage.
- Crop-aware treatment history with date, disease, confidence, and remedy details.
- CSV export and print-to-PDF export for saved treatment history.
- Printable Agrova diagnostic health card.
- First-time user walkthrough for the detection workflow.
- Consent dialogs before camera, microphone, and location access.
- WhatsApp sharing and browser voice readout.
- Spray dosage calculator for cents, acres, and hectares.
- Weather and fungal-risk advisory by Kerala district.
- Crop calendar for tomato, banana, chilli, and ginger.
- Disease reference gallery.
- Photo-backed visual reference gallery with lazy loading and fallbacks.
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
- Gallery photos are visual references and must not be used as a substitute for diagnosis.
- The chatbot requires the configured worker endpoint and internet access.
- A Google Maps API key and service endpoints are visible in client-side code. This is not suitable for production deployment without server-side protection and key restrictions.
- The current disease model supports only the classes included in its Teachable Machine metadata.


## Safety Notice

Always follow the product label, wear appropriate protective equipment, observe pre-harvest intervals, and consult a qualified agricultural professional before applying pesticides or treating severe crop disease.
