# Yoga App - iOS

iOS application for yoga teachers and students to find and schedule classes by location with real-time booking.

## Features

- **Location-based Search**: Find yoga classes near you
- **Real-time Scheduling**: Book classes instantly
- **Teacher Profiles**: Browse instructor details and specialties
- **Class Types**: Filter by yoga style (Hatha, Vinyasa, Kundalini, etc.)
- **Schedule Management**: Manage your bookings and favorites
- **Ratings & Reviews**: Community feedback on classes
- **Push Notifications**: Get reminders for upcoming classes
- **In-app Payments**: Secure payment processing

## Tech Stack

- **Language**: Swift
- **Framework**: UIKit / SwiftUI
- **Backend**: Firebase
- **Maps**: Apple Maps / Google Maps SDK
- **Payments**: Stripe or Apple Pay
- **Analytics**: Firebase Analytics

## Project Structure

```
├── App/
│   ├── Views/              # SwiftUI views
│   ├── ViewModels/         # MVVM view models
│   ├── Models/             # Data models
│   ├── Services/           # Network & Firebase services
│   └── Utilities/          # Helper functions
├── Assets/                 # Images, colors, strings
└── YogaApp.swift          # App entry point
```

## Getting Started

### Requirements

- Xcode 14+
- iOS 14+
- CocoaPods or SPM

### Installation

```bash
# Install dependencies
pod install

# Open workspace
open YogaApp.xcworkspace
```

### Configuration

1. Add Firebase config to `GoogleService-Info.plist`
2. Configure location permissions in `Info.plist`
3. Add API keys for maps and payments

## Features in Detail

### Class Discovery
- Search by location, style, and time
- Filter by teacher level and class duration
- Save favorite classes and teachers

### Booking System
- One-tap booking with confirmation
- View class calendar
- Get cancellation details and refund policies

### Class Reminders
- Push notifications 24 hours before
- In-app reminders
- Calendar integration

### Teacher Tools
- Manage class schedule
- View student roster
- Communicate with students

## API Endpoints

- `GET /classes?location=lat,lng` - Find nearby classes
- `POST /bookings` - Book a class
- `GET /teachers/:id` - Get teacher profile
- `GET /schedules/:classId` - Get class schedule

---

**Namaste - Connect with yoga near you** 🧘‍♀️