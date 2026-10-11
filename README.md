# Earthquake Map

A Flutter mobile app that lists recent Turkey earthquakes and plots them on Google Maps.

## About

Built in July 2021 as a learning project to practice Flutter state management (GetX), XML
parsing, local persistence and Google Maps integration. It fetches live earthquake data from
the Kandilli Observatory (Boğaziçi University) RSS feed and shows each event on a map and in a
list.

## Features

- Fetches and parses the real-time earthquake RSS feed from `koeri.boun.edu.tr`
- Lists earthquakes with magnitude and location
- Plots earthquake locations as markers on Google Maps
- Local SQLite storage for saved/favorite entries
- Percent indicator UI element for magnitude visualization

## Tech stack

- Flutter / Dart
- `get` (GetX) for state management and navigation
- `google_maps_flutter` for the map view
- `http`, `xml2json`, `xml_parser` for fetching and parsing the RSS feed
- `sqflite` for local storage
- `google_fonts`, `percent_indicator` for UI

## Project structure

```
lib/
  core/
    constants/   # shared string helpers
    models/      # earthquake data model
    services/    # RSS fetch + SQLite service
  ui/
    view/        # pages: map, list, database
    viewModels/  # GetX controllers
android/
ios/
web/
```

## Getting started

1. Install Flutter and run `flutter pub get`.
2. Add a Google Maps API key, required for the map view on Android:
   - create `android/local.properties` (gitignored) if it does not exist
   - add a line: `MAPS_API_KEY=your_google_maps_api_key`
   - the key is injected into `AndroidManifest.xml` at build time via a Gradle
     manifest placeholder (see `android/app/build.gradle`), so it is never
     committed to the repository.
3. Run `flutter run`.

## Status

Learning project, not actively maintained.

## Related projects

- [depremdayanisma](https://github.com/tolgazorlu/depremdayanisma): earthquake solidarity project
