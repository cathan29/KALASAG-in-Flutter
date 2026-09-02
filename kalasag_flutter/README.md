# Kalasag Flutter

This folder is the standalone Flutter migration of the original React Native app. The React Native source in the repository root is intentionally untouched.

## Included

- Five-tab Material 3 interface: Weather, Alerts, Radar, Ready, and SOS
- GPS permission, reverse-geocoded location, Open-Meteo multi-model forecast
- Live Philippine-area alerts from GDACS, USGS, and NASA EONET
- Alert filtering, detail pages, and official-source links
- Embedded Windy rain, wind, temperature, and cloud layers
- Persistent saved places, go-bag checklist, family plan, and alert preferences
- OpenStreetMap/Overpass evacuation-center search with radius filters
- Offline verified hotline directory and first-aid/evacuation guides
- Light/dark themes and Android/iOS location configuration

## Run

```powershell
cd kalasag_flutter
flutter pub get
flutter run
```

Choose an Android emulator or USB-connected Android device when prompted. Location and network access are required for live weather, radar, alerts, and shelter search. Emergency data and readiness plans work locally.

## Validate and build

```powershell
flutter analyze
flutter test
flutter build apk --debug
```

The generated debug APK is at `build/app/outputs/flutter-apk/app-debug.apk`.

## Notes

- The Android wrapper uses Gradle 9.1 because this development machine currently uses Java 25.
- Alert preferences are persisted. OS background/push delivery still requires a production notification provider or backend; live alerts refresh when the app starts or the user refreshes.
- Windy is embedded through its public map page, matching the network-dependent radar behavior of the original app.
