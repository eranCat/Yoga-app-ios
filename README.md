# 🧘 Yoga App — iOS

An iOS yoga app built in Swift that lets users discover yoga classes nearby, view instructor profiles, and schedule sessions by location.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Language | Swift |
| UI | UIKit / Storyboard |
| Backend | Firebase Firestore |
| Auth | Firebase Authentication |
| Maps | MapKit / Core Location |

## Features

- **Class discovery** — find yoga classes by type, level, and location
- **Instructor profiles** — bios, photos, ratings, and upcoming schedules
- **Location-based search** — map view with nearby class pins
- **Scheduling** — book and manage upcoming sessions
- **Firebase auth** — secure email/Apple sign-in

## Getting Started

### Prerequisites
- Xcode 14+
- iOS 14+ deployment target
- Firebase project with Firestore and Auth enabled
- CocoaPods

### Setup

```bash
git clone https://github.com/eranCat/Yoga-app-ios.git
cd Yoga-app-ios
pod install
open YogaApp.xcworkspace
```

1. Add your `GoogleService-Info.plist` from Firebase console to the project
2. Build & run on simulator or device

## Companion App

This app has an Android companion: [Yoga_app_android](https://github.com/eranCat/Yoga_app_android)

## Author

**Eran Karaso** — [Portfolio](https://erancat.github.io/portfolio-site) · [GitHub](https://github.com/eranCat)
