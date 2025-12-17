# 📦 Complete Project Files - Android & iOS Apps

## 🚀 Quick Start Guide

This document contains all essential files needed to set up production-ready mobile apps for the Galactic Archives Hackathon.

---

## 📱 ANDROID PROJECT FILES

### Directory Structure
```
GalacticArchivesHackathon/
├── build.gradle.kts (✅ already created)
├── settings.gradle.kts (✅ already created)
├── gradle.properties
├── .github/workflows/android.yml
└── app/
    ├── build.gradle.kts
    ├── proguard-rules.pro
    ├── google-services.json (add your own)
    └── src/main/
        ├── AndroidManifest.xml
        ├── java/com/galacticarchives/hackathon/
        │   ├── MainActivity.kt
        │   ├── HackathonApplication.kt
        │   ├── data/
        │   │   ├── model/
        │   │   │   ├── User.kt
        │   │   │   ├── Meeting.kt
        │   │   │   ├── FriendRequest.kt
        │   │   │   └── StellaCommand.kt
        │   │   └── repository/
        │   │       ├── AuthRepository.kt
        │   │       ├── UserRepository.kt
        │   │       ├── MeetingRepository.kt
        │   │       └── FriendRepository.kt
        │   ├── di/
        │   │   ├── AppModule.kt
        │   │   └── NetworkModule.kt
        │   ├── ui/
        │   │   ├── theme/
        │   │   │   ├── Color.kt
        │   │   │   ├── Theme.kt
        │   │   │   └── Type.kt
        │   │   ├── auth/
        │   │   │   ├── LoginScreen.kt
        │   │   │   └── AuthViewModel.kt
        │   │   ├── profile/
        │   │   │   ├── ProfileScreen.kt
        │   │   │   └── ProfileViewModel.kt
        │   │   ├── meetings/
        │   │   │   ├── MeetingsScreen.kt
        │   │   │   └── MeetingsViewModel.kt
        │   │   ├── friends/
        │   │   │   ├── FriendsScreen.kt
        │   │   │   └── FriendsViewModel.kt
        │   │   └── stella/
        │   │       ├── StellaCommandScreen.kt
        │   │       └── StellaCommandViewModel.kt
        │   └── utils/
        │       ├── Constants.kt
        │       └── Extensions.kt
        └── res/
            ├── values/
            │   ├── strings.xml
            │   ├── colors.xml
            │   └── themes.xml
            └── drawable/
```

### 1. `gradle.properties`

```properties
org.gradle.jvmargs=-Xmx2048m -Dfile.encoding=UTF-8
org.gradle.caching=true
org.gradle.parallel=true

android.useAndroidX=true
android.enableJetifier=true

kotlin.code.style=official
```

### 2. `app/build.gradle.kts`

```kotlin
plugins {
    id("com.android.application")
    id("org.jetbrains.kotlin.android")
    id("com.google.gms.google-services")
    id("com.google.dagger.hilt.android")
    kotlin("kapt")
}

android {
    namespace = "com.galacticarchives.hackathon"
    compileSdk = 35

    defaultConfig {
        applicationId = "com.galacticarchives.hackathon"
        minSdk = 24
        targetSdk = 35
        versionCode = 1
        versionName = "1.0.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
        vectorDrawables {
            useSupportLibrary = true
        }
    }

    buildTypes {
        release {
            isMinifyEnabled = true
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
    
    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_17
        targetCompatibility = JavaVersion.VERSION_17
    }
    
    kotlinOptions {
        jvmTarget = "17"
    }
    
    buildFeatures {
        compose = true
    }
    
    composeOptions {
        kotlinCompilerExtensionVersion = "1.5.4"
    }
    
    packaging {
        resources {
            excludes += "/META-INF/{AL2.0,LGPL2.1}"
        }
    }
}

dependencies {
    // AndroidX Core
    implementation("androidx.core:core-ktx:1.12.0")
    implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.7.0")
    implementation("androidx.activity:activity-compose:1.8.2")

    // Jetpack Compose
    implementation(platform("androidx.compose:compose-bom:2024.01.00"))
    implementation("androidx.compose.ui:ui")
    implementation("androidx.compose.ui:ui-graphics")
    implementation("androidx.compose.ui:ui-tooling-preview")
    implementation("androidx.compose.material3:material3")
    implementation("androidx.navigation:navigation-compose:2.7.6")

    // Firebase
    implementation(platform("com.google.firebase:firebase-bom:32.7.0"))
    implementation("com.google.firebase:firebase-auth-ktx")
    implementation("com.google.firebase:firebase-firestore-ktx")
    implementation("com.google.firebase:firebase-storage-ktx")
    implementation("com.google.firebase:firebase-analytics-ktx")

    // Hilt for Dependency Injection
    implementation("com.google.dagger:hilt-android:2.48")
    kapt("com.google.dagger:hilt-compiler:2.48")
    implementation("androidx.hilt:hilt-navigation-compose:1.1.0")

    // Retrofit for API calls
    implementation("com.squareup.retrofit2:retrofit:2.9.0")
    implementation("com.squareup.retrofit2:converter-gson:2.9.0")
    implementation("com.squareup.okhttp3:logging-interceptor:4.12.0")

    // Coil for Image Loading
    implementation("io.coil-kt:coil-compose:2.5.0")

    // Jitsi Meet SDK
    implementation("org.jitsi.react:jitsi-meet-sdk:9.2.2")

    // Testing
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.test.espresso:espresso-core:3.5.1")
    androidTestImplementation(platform("androidx.compose:compose-bom:2024.01.00"))
    androidTestImplementation("androidx.compose.ui:ui-test-junit4")
    debugImplementation("androidx.compose.ui:ui-tooling")
    debugImplementation("androidx.compose.ui:ui-test-manifest")
}

kapt {
    correctErrorTypes = true
}
```
