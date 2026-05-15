# Yoga App iOS

A beautifully designed iOS application for yoga teachers and students to discover nearby yoga classes, schedule sessions, and connect with the yoga community. Built with Swift and SwiftUI, featuring real-time updates, location-based search, and seamless user experience.

## 🧘 Features

- **Nearby Class Discovery** - Find yoga classes within your location radius
- **Real-time Scheduling** - Instant booking confirmation and availability updates
- **Instructor Profiles** - View instructor credentials, experience, and student reviews
- **Class Filtering** - Filter by yoga style, level, time, and price
- **Calendar Integration** - Add booked classes to Apple Calendar
- **Push Notifications** - Class reminders and community updates
- **Rating & Reviews** - Rate classes and read community feedback
- **Instructor Chat** - Direct messaging with yoga teachers
- **Class Search** - Advanced search with multiple filter options
- **Favorites** - Save favorite instructors and classes

## 🛠 Tech Stack

- **Language**: Swift
- **UI Framework**: SwiftUI
- **Architecture**: MVVM + Coordinator Pattern
- **Database**: Firebase Firestore
- **Authentication**: Firebase Authentication
- **Maps**: Apple MapKit
- **Networking**: URLSession + Combine
- **Real-time**: Firebase Cloud Messaging (FCM)
- **Build Tool**: Xcode 14+
- **Minimum iOS**: iOS 14.0+

## 📁 Project Structure

```
YogaApp/
├── App/
│   ├── YogaApp.swift           # App entry point
│   └── SceneDelegate.swift     # Scene configuration
├── Features/
│   ├── Authentication/
│   │   ├── Views/
│   │   ├── ViewModels/
│   │   └── Services/
│   ├── ClassDiscovery/
│   │   ├── Views/
│   │   ├── ViewModels/
│   │   └── Models/
│   ├── Scheduling/
│   ├── UserProfile/
│   ├── Messaging/
│   └── Favorites/
├── Core/
│   ├── Models/                 # Shared data models
│   ├── Networking/             # API services
│   ├── Database/               # Firebase services
│   ├── Location/               # Location services
│   └── Utilities/              # Helper functions
├── Resources/
│   ├── Assets.xcassets/
│   ├── Localizable.strings/
│   └── Colors.xcassets/
└── Supporting Files/
    ├── GoogleService-Info.plist
    └── Info.plist
```

## 🚀 Getting Started

### Prerequisites

- Xcode 14.0+
- Swift 5.7+
- iOS 14.0+ deployment target
- CocoaPods or Swift Package Manager
- Firebase account

### Installation

1. Clone the repository:
```bash
git clone https://github.com/eranCat/Yoga-app-ios.git
cd Yoga-app-ios
```

2. Install dependencies via CocoaPods:
```bash
pod install
```

3. Set up Firebase:
   - Create Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
   - Download `GoogleService-Info.plist`
   - Add to Xcode project (ensure added to targets)
   - Enable Firestore, Authentication, Storage, and Cloud Messaging

4. Open workspace:
```bash
open YogaApp.xcworkspace
```

5. Select target device and run ⌘R

### CocoaPods Dependencies

Key pods in Podfile:
- Firebase/Core
- Firebase/Auth
- Firebase/Firestore
- Firebase/Storage
- Firebase/Messaging
- Google-Maps-iOS-Utils
- Kingfisher (image caching)
- Combine-based networking

## 📱 App Architecture

### MVVM Pattern

**View** → **ViewModel** → **Model** → **Service**

- **Views**: SwiftUI components for UI
- **ViewModels**: Manages state and business logic
- **Models**: Data structures (Codable)
- **Services**: API calls and Firebase operations

### Coordinator Pattern

Navigation is managed through Coordinators for complex flows:
- Authentication Coordinator
- Main App Coordinator
- Class Discovery Coordinator
- Booking Coordinator

## 🗺️ Key Screens

### Authentication
- **Login Screen**: Email/password authentication
- **Sign Up Screen**: New user registration
- **Profile Setup**: Select user type (student/instructor)

### Class Discovery
- **Map View**: Interactive map showing nearby studios
- **Class List**: Browse all available classes
- **Class Details**: Full information with reviews
- **Search & Filter**: Advanced search options

### Scheduling
- **Calendar View**: User's booked classes
- **Class Details**: Booking information
- **Confirmation**: Secure booking flow
- **Receipt**: Digital receipt display

### User Profile
- **My Profile**: User information and preferences
- **Booking History**: Past and upcoming bookings
- **Favorites**: Saved classes and instructors
- **Settings**: App preferences and notifications

### Messaging
- **Conversations**: Direct messages with instructors
- **Chat Screen**: Real-time messaging interface
- **Notifications**: Message alerts

## 🌍 Location Services

- **MapKit Integration**: Display yoga studios on map
- **Current Location**: Request location permissions
- **Geofencing**: Notify users of nearby classes
- **Route Navigation**: Integrate Apple Maps for directions

## 🔔 Push Notifications

Firebase Cloud Messaging (FCM) for:
- Class reminders (15 min, 1 hour, 1 day before)
- New message notifications
- Special offers and events
- Community announcements

## 💾 Data Models

### User
```swift
struct User: Codable {
    let id: String
    let email: String
    let name: String
    let userType: UserType  // student, instructor
    let location: CLLocationCoordinate2D
    let profileImage: URL?
    let bio: String
    let rating: Double
    let joinDate: Date
}
```

### YogaClass
```swift
struct YogaClass: Codable, Identifiable {
    let id: String
    let instructorId: String
    let title: String
    let style: YogaStyle
    let level: YogaLevel
    let startTime: Date
    let endTime: Date
    let location: Location
    let capacity: Int
    let enrolled: Int
    let price: Double
    let description: String
    let imageURL: URL?
    let rating: Double
}
```

### Booking
```swift
struct Booking: Codable {
    let id: String
    let userId: String
    let classId: String
    let bookingDate: Date
    let status: BookingStatus
    let paymentMethod: String
}
```

## 🔐 Security

- **Keychain Integration**: Secure credential storage
- **Firebase Authentication**: Built-in security
- **Network Security**: SSL/TLS encryption
- **Data Validation**: Input sanitization
- **Permission Handling**: Proper iOS privacy requests

## 🧪 Testing

### Unit Tests
```bash
# Run unit tests
cmd + U
```

### UI Tests
```swift
// Example test
func testClassDiscoveryLoads() {
    let app = XCUIApplication()
    app.launch()
    
    let mapView = app.maps.firstMatch
    XCTAssertTrue(mapView.exists)
}
```

## 📊 Performance

- **Image Caching**: Kingfisher library
- **Lazy Loading**: ScrollView with onAppear
- **Network Optimization**: Request batching
- **Database Indexing**: Firestore indexes
- **Memory Management**: Proper @State cleanup

## 🎨 Design System

- **Color Palette**: Zen-inspired colors (greens, purples, whites)
- **Typography**: Clear hierarchy with SF Pro Display
- **Spacing**: 8pt base grid system
- **Components**: Reusable SwiftUI components
- **Dark Mode**: Full support for system theme

## 🚀 Build & Release

### Staging Build
```bash
# Archive for testing
Product → Scheme → Edit Scheme → Run
# Set configuration to Debug/Staging
```

### App Store Release
1. Create App ID in Apple Developer
2. Configure app capabilities
3. Set up provisioning profiles
4. Archive app: Product → Archive
5. Validate and upload to App Store Connect
6. Submit for review

## 🌐 Localization

Supported languages:
- English
- Hebrew (עברית)
- Spanish

Managed via `Localizable.strings` files

## 📈 Analytics

Integration with Firebase Analytics:
- Screen views tracking
- User engagement metrics
- Booking conversion funnel
- Search analytics

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/NewFeature`
3. Commit changes: `git commit -m 'Add new feature'`
4. Push: `git push origin feature/NewFeature`
5. Open Pull Request

## 📝 License

MIT License - See [LICENSE](./LICENSE) for details

## 👤 Author

**Eran Karaso** - Full-Stack Developer  
GitHub: [@eranCat](https://github.com/eranCat)

## 🔗 Resources

- [Swift Documentation](https://swift.org/documentation)
- [SwiftUI Tutorials](https://developer.apple.com/tutorials/swiftui)
- [Firebase iOS SDK](https://firebase.google.com/docs/ios)
- [MapKit Documentation](https://developer.apple.com/mapkit)
- [iOS App Development](https://developer.apple.com/ios)

## 📞 Support & Feedback

Have feedback or found a bug? Open an [issue](https://github.com/eranCat/Yoga-app-ios/issues)

## 🚀 Future Enhancements

- [ ] Video streaming for online classes
- [ ] Apple Watch integration
- [ ] Siri Shortcuts support
- [ ] HealthKit integration for activity tracking
- [ ] Social sharing with iMessage
- [ ] In-app payment integration
- [ ] Offline mode for saved classes
- [ ] AR class previews