<div align="center">

# ☕ CaffioLens
### AI-Powered Coffee Pack Identifier

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)

**ITE120 Final Project • CSUCC**

[Features](#-features) • [Screenshots](#-screenshots) • [Tech Stack](#%EF%B8%8F-tech-stack) • [Installation](#-installation)

</div>

<br>

## 📖 About

CaffioLens is an intelligent mobile application that uses **TensorFlow Lite AI** to identify coffee packs through your smartphone camera. Built with **Flutter** for seamless cross-platform performance and integrated with **Firebase** for real-time cloud synchronization.

> 🎯 **94%+ accuracy** in coffee pack classification  
> ⚡ **Under 2 seconds** processing time  
> ☁️ **Cloud-synced** scan history

<br>

## 📦 Project Resources

<table>
<tr>
<td align="center" width="50%">

### 💻 Full Project Code
[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)](https://github.com/carlo1monoy/Full_project_code)

Complete Flutter source code including all Dart files, screens, and configurations.

**[View Repository →](https://github.com/carlo1monoy/Full_project_code)**

</td>
<td align="center" width="50%">

### 🎨 Assets & Resources
[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)](https://github.com/carlo1monoy/Monoy_InstantCoffee_Classification_FinalProject)

TensorFlow Lite model, screenshots, training data, and all project assets.

**[View Repository →](https://github.com/carlo1monoy/Monoy_InstantCoffee_Classification_FinalProject)**

</td>
</tr>
</table>

<br>

## ✨ Features

<table>
<tr>
<td width="50%">

### 📸 Real-Time Scanning
Instant coffee pack identification using your device camera with live preview and automatic focus.

### 🤖 AI Classification  
TensorFlow Lite model processes images on-device for fast, private coffee type recognition.

### 🖼️ Gallery Support
Select and analyze coffee pack images from your photo library with same AI accuracy.

</td>
<td width="50%">

### 📊 Smart Dashboard
Track total scans, success rates, and daily activity with real-time statistics.

### 📜 Scan History
Browse complete history with thumbnails, timestamps, and confidence scores.

### ☁️ Cloud Sync
Automatic Firebase backup ensures your data is safe and accessible anywhere.

</td>
</tr>
</table>

<br>

## 📸 Screenshots

<div align="center">

| 🏠 Home | 📷 Scanner | 🖼️ Gallery | ✅ Results | 📜 History |
|:---:|:---:|:---:|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/56fc7d8c-9c8f-4ff3-a65a-8da746eab709" width="150"> | <img src="https://github.com/user-attachments/assets/ba9815bd-3b3d-4d20-ad10-952e032a43b3" width="150"> | <img src="https://github.com/user-attachments/assets/748e1be9-41dc-46fe-ae32-78cf946cb879" width="150"> | <img src="https://github.com/user-attachments/assets/c76f0f75-fbfa-4426-81ec-4b7df0a4aa96" width="150"> | <img src="https://github.com/user-attachments/assets/73413462-815b-4990-b173-55c41637afdb" width="150"> |
| Real-time stats & activity | Live preview & instant capture | Pick from device library | AI accuracy & details | Cloud-synced scan log |

</div>

### 📱 Screen Details

<details>
<summary><b>🏠 Home Dashboard</b></summary>

<br>

<img src="https://github.com/user-attachments/assets/56fc7d8c-9c8f-4ff3-a65a-8da746eab709" width="250">

**Key Functions:**
- 📊 Real-time statistics (Total Scans, Success Rate, Today's Count)
- 📜 Recent scans list with thumbnails and confidence scores
- ⚡ Live Firebase updates
- 🧭 Quick navigation to all app sections

</details>

<details>
<summary><b>📷 Camera Scanner</b></summary>

<br>

<img src="https://github.com/user-attachments/assets/ba9815bd-3b3d-4d20-ad10-952e032a43b3" width="250">

**Key Functions:**
- 📸 Live camera viewfinder with auto-focus
- 🎯 One-tap capture button
- � Instant processing for identified items
- 🧭 Persistent bottom navigation

</details>

<details>
<summary><b>🖼️ Gallery Selection</b></summary>

<br>

<img src="https://github.com/user-attachments/assets/748e1be9-41dc-46fe-ae32-78cf946cb879" width="250">

**Key Functions:**
- 📁 Access device photo library
- 🔍 Analyze previously captured coffee packs
- 🤖 Same AI accuracy as live scanning
- ⚡ Quick processing of stationary images

</details>

<details>
<summary><b>✅ Scan Results</b></summary>

<br>

<img src="https://github.com/user-attachments/assets/c76f0f75-fbfa-4426-81ec-4b7df0a4aa96" width="250">

**Key Functions:**
- 🎯 AI-powered coffee type identification
- 📈 Confidence score percentage (0-100%)
- 🕒 Timestamp of scan
- 💾 Automatic save to Firebase
- 🔄 Quick "Scan Again" action

</details>

<details>
<summary><b>📜 Scan History</b></summary>

<br>

<img src="https://github.com/user-attachments/assets/73413462-815b-4990-b173-55c41637afdb" width="250">

**Key Functions:**
- 📋 Complete log of all scans
- 🖼️ Thumbnail previews
- 📊 Color-coded confidence badges (Green = Success, Orange = Low confidence)
- 🕒 Date and time stamps
- ☁️ Real-time Firebase synchronization

</details>

<br>

## 🛠️ Tech Stack

```
Frontend        Flutter 3.0+ • Dart 3.0+ • Material Design
AI/ML          TensorFlow Lite 0.12.0 • On-device inference
Backend        Firebase Firestore • Firebase Core
Camera         Camera Plugin 0.10.5+ • Image Picker 1.1.2
Analytics      FL Chart 0.68.0 • Real-time statistics
Design         Google Fonts (Lato) • Coffee-themed palette
```

<details>
<summary><b>📦 View All Dependencies</b></summary>

```yaml
dependencies:
  flutter: sdk
  camera: ^0.10.5+9
  tflite_flutter: ^0.12.0
  firebase_core: ^2.31.0
  cloud_firestore: ^4.17.3
  image_picker: ^1.1.2
  fl_chart: ^0.68.0
  google_fonts: ^6.2.1
  permission_handler: ^11.3.1
  image: ^4.2.0
  path_provider: ^2.1.1
  intl: ^0.19.0
```

</details>

<br>

## 🚀 Quick Start

```bash
# 1. Clone repository
git clone https://github.com/yourusername/caffiolens.git
cd caffiolens

# 2. Install dependencies
flutter pub get

# 3. Run the app
flutter run
```

### Prerequisites
- Flutter SDK 3.0+
- Dart SDK 3.0+
- Android Studio / Xcode
- Firebase account (for cloud features)

<br>

## ⚙️ How It Works

```mermaid
graph LR
    A[📱 Launch App] --> B[📸 Capture/Select Image]
    B --> C[🤖 TFLite Processing]
    C --> D[✅ AI Classification]
    D --> E[📊 Display Results]
    E --> F[☁️ Save to Firebase]
    F --> G[📜 Update History]
```

1. **Capture** - Take photo or select from gallery
2. **Process** - TensorFlow Lite analyzes image features
3. **Classify** - AI identifies coffee pack with confidence score
4. **Save** - Results automatically saved to Firebase
5. **Track** - View statistics and history anytime

<br>

## 💻 Source Code

<details>
<summary><b>📄 main.dart</b> - Main Application</summary>

```dart
// Paste your complete main.dart code here
// Includes: HomeScreen, CameraScreen, ResultsScreen, PredictionsScreen
```

</details>

<details>
<summary><b>🤖 tflite_helper.dart</b> - AI Model Integration</summary>

```dart
// Paste your tflite_helper.dart code here
// TensorFlow Lite model loading and image processing
```

</details>

<details>
<summary><b>🔥 firebase_options.dart</b> - Firebase Config</summary>

```dart
// Paste your firebase_options.dart code here
// Platform-specific Firebase initialization
```

</details>

<br>

## 📊 Project Stats

- **Language:** Dart
- **Framework:** Flutter
- **ML Model:** TensorFlow Lite
- **Accuracy:** 94%+
- **Processing Time:** < 2 seconds
- **Platform Support:** Android, iOS

<br>

## 📄 License

This project is licensed under the **MIT License**.

<br>

## 👨‍💻 Author

<div align="center">

**Anthony Charles Monoy**

📧 anthonycharles.monoy@csucc.edu.ph  
🎓 ITE120 Final Project  
🏫 CSUCC

<br>

---

<sub>Made with ❤️ and ☕ using Flutter</sub>

**⭐ Star this repository if you find it helpful!**

</div>
