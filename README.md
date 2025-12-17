# 🚀 Galactic Archives Hackathon - Android App

<div align="center">

![Galactic Archives Logo](https://galacticarchives.space/images/logo.png)

**Android mobile app for Galactic Archives Hackathon participants**

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![Android](https://img.shields.io/badge/Android-7.0%2B-green.svg)](https://developer.android.com)
[![Kotlin](https://img.shields.io/badge/Kotlin-1.9%2B-purple.svg)](https://kotlinlang.org)

[Features](#features) • [Installation](#installation) • [Tech Stack](#tech-stack) • [Documentation](#documentation)

</div>

---

## 🌌 About

The Galactic Archives Hackathon mobile app connects participants during the 5-day innovation challenge focused on space exploration data from NASA and SpaceX. Build groundbreaking applications, collaborate with teams, and venture into the cosmic data streams.

## ✨ Features

### 👤 Personal Profiles
- User authentication with Discord OAuth2
- Customizable space-themed avatars
- Bio and skills showcase
- Team assignment and role display
- **Stella Command** special role access
- Real-time profile synchronization

### 🎮 Discord Integration
- Single sign-on with Discord
- Automatic avatar and username sync
- Guild/server information display
- Community verification
- Access to **Stella Command** channels
- Seamless authentication flow

### 🎥 Virtual Meeting Rooms
- Create and schedule collaboration meetings
- Video conferencing powered by Jitsi Meet
- Real-time participant tracking
- **Stella Command broadcast rooms**
- Meeting history and analytics
- Screen sharing capabilities
- Direct meeting links

### 👥 Friend Request System
- Send friend requests to participants
- Accept/reject/cancel requests
- Maintain friend list
- Connect with **Stella Command** members
- Real-time synchronization
- Direct messaging via Discord

### ⚡ Stella Command
**Stella Command** is the elite leadership team for the hackathon:
- **Admiral** role - Event leadership
- **Chief Engineering** role - Technical oversight
- Special badge display in profiles
- Access to broadcast meeting rooms
- Priority notifications for announcements
- Command center dashboard

## 🛠️ Tech Stack

- **Language**: Kotlin 1.9+
- **UI Framework**: Jetpack Compose 1.6+
- **Architecture**: MVVM (Model-View-ViewModel)
- **Dependency Injection**: Hilt
- **Backend**: Firebase (Firestore, Auth, Storage)
- **Authentication**: Discord OAuth2
- **Video Conferencing**: Jitsi Meet SDK
- **Networking**: Retrofit + OkHttp
- **Image Loading**: Coil
- **Min SDK**: 24 (Android 7.0)
- **Target SDK**: 35 (Android 15)

## 📦 Installation

### Prerequisites
- Android Studio Iguana (2023.2.1) or later
- JDK 17 or later
- Android SDK with API 35
- Firebase account
- Discord Developer account

### Setup Steps

1. **Clone the repository**
```bash
git clone https://github.com/Galactic-Archives/galactic-archives-android.git
cd galactic-archives-android
```

2. **Configure Firebase**
- Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
- Enable Firebase Auth, Firestore, and Storage
- Download `google-services.json`
- Place it in `app/` directory

3. **Setup Discord OAuth**
- Create Discord app at [discord.com/developers](https://discord.com/developers)
- Add OAuth2 redirect URI: `com.galacticarchives.hackathon://oauth2-callback`
- Copy Client ID and Secret

4. **Configure credentials**
Create/Edit `app/src/main/java/com/galacticarchives/hackathon/utils/Constants.kt`:
```kotlin
object Constants {
    const val DISCORD_CLIENT_ID = "your-discord-client-id"
    const val DISCORD_CLIENT_SECRET = "your-discord-client-secret"
    const val DISCORD_REDIRECT_URI = "com.galacticarchives.hackathon://oauth2-callback"
}
```

5. **Build and Run**
```bash
./gradlew assembleDebug
# Or open in Android Studio and click Run
```

## 🏗️ Project Structure

```
app/
├── src/
│   ├── main/
│   │   ├── java/com/galacticarchives/hackathon/
│   │   │   ├── data/          # Data layer (repositories, models)
│   │   │   ├── di/            # Dependency injection modules
│   │   │   ├── ui/            # UI layer (screens, components)
│   │   │   │   ├── auth/      # Authentication screens
│   │   │   │   ├── profile/   # Profile management
│   │   │   │   ├── meetings/  # Meeting rooms
│   │   │   │   ├── friends/   # Friend system
│   │   │   │   └── stella/    # Stella Command dashboard
│   │   │   ├── utils/         # Utilities and constants
│   │   │   └── MainActivity.kt
│   │   ├── res/               # Resources (layouts, drawables)
│   │   └── AndroidManifest.xml
│   └── test/                  # Unit tests
└── build.gradle.kts
```

## 🎨 Design System

Follows the [Galactic Archives Brand Guide](https://galacticarchives.space/brand-guide.html):

**Colors:**
- Deep Space Black: `#0A1929`
- Midnight Blue: `#1A237E`
- Cyber Cyan: `#00D4FF` (Primary accent)
- Nebula Purple: `#7C3AED`
- Cosmic Pink: `#FF6B9D`
- Stellar Gold: `#FFD700` (Stella Command)

**Typography:**
- Headers: Orbitron Bold
- Body: Inter Regular

## 🔒 Security

- Firebase Security Rules implemented
- OAuth2 token validation
- Data encryption in transit (TLS)
- User-specific data isolation
- No sensitive data in logs
- ProGuard obfuscation enabled

## 🚀 Deployment

### Debug Build
```bash
./gradlew assembleDebug
```

### Release Build
```bash
./gradlew assembleRelease
# Or for Play Store:
./gradlew bundleRelease
```

### Google Play Store
1. Generate signing key
2. Configure `keystore.properties`
3. Build release AAB
4. Upload to Play Console
5. Complete store listing

## 📱 Screenshots

_Coming soon: Screenshots of main features_

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🌟 Acknowledgments

- **Galactic Archives Team** - For organizing the hackathon
- **Stella Command** - For leadership and guidance
- **All Participants** - For pushing the boundaries of space tech
- **Firebase** - Backend infrastructure
- **Jitsi** - Video conferencing platform
- **Discord** - Community platform

## 📞 Support

- **Documentation**: [Full Docs](https://github.com/Galactic-Archives/galactic-archives-android/wiki)
- **Issues**: [GitHub Issues](https://github.com/Galactic-Archives/galactic-archives-android/issues)
- **Discord**: [Join our server](https://discord.gg/galactic-archives)
- **Email**: support@galacticarchives.space

## 🔗 Related Projects

- [iOS App](https://github.com/Galactic-Archives/galactic-archives-ios)
- [Web Platform](https://github.com/Galactic-Archives/admiral-Gal-Arch.io)
- [API Backend](https://github.com/Galactic-Archives/galactic-aggregator-backend)

---

<div align="center">

**Made with ❤️ for space exploration enthusiasts**

[Website](https://galacticarchives.space) • [Hackathon](https://the-galactic-archives-2026.devpost.com) • [Brand Guide](https://galacticarchives.space/brand-guide.html)

</div>
