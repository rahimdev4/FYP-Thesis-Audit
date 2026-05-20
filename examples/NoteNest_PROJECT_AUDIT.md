# NoteNest — FYP Project Information (For Thesis Writing)

> This document captures all project details, features, architecture, packages, and reference thesis structure needed to write the FYP thesis.

---

## 1. Project Overview

- **Project Name:** NoteNest
- **Type:** Mobile Application (Android & iOS)
- **Framework:** Flutter (Dart)
- **SDK:** `^3.8.1`
- **Architecture Pattern:** MVVM (Model-View-ViewModel) with Riverpod state management
- **University:** University of Malakand
- **Department:** Computer Science
- **Project Type:** Final Year Project (FYP)

---

## 2. Project Description

NoteNest is an AI-powered academic note management mobile application designed for university students. It enables students to organize their academic materials by **subjects** and **lectures**, capture notes through multiple input methods (text, camera, file upload, and AI-generated content), and securely back up all data to Google Drive for cross-device access.

---

## 3. Core Features

### 3.1 Authentication (Firebase Auth)
- **Email/Password** sign up and login
- **Google Sign-In** integration
- **Forgot Password** flow via email reset
- **Change Password** from settings
- **Profile Setup** after registration (name, department, semester)
- **Per-user data isolation** — each user gets their own Hive boxes scoped by UID

### 3.2 Home Screen (Subject Management)
- User clicks **"+"** to create a new subject
- Popup asks for: **Subject Name**, **Department** (optional), **Semester** (optional)
- Subjects displayed as cards with **department-based gradient colors**
- **Edit** and **Delete** subjects with confirmation dialogs
- **Staggered animations** for smooth UI transitions
- Subjects sorted by creation date (newest first)

### 3.3 Subject Detail (Lecture Management)
- Inside a subject, user clicks **"+"** to create a new lecture
- Enter lecture **title** (e.g., "OOP – Inheritance")
- Lectures sorted by date (newest first)
- Can **rename** or **delete** lectures
- Deleting a lecture also deletes all its child notes

### 3.4 Lecture Detail (Note Content Management)
User can add content to a lecture through multiple methods:
- **Add Text** — opens popup, user types text content manually
- **Generate with AI** — uses the subject name + lecture title to auto-generate quick notes via **Gemini API** (Google Generative AI)
- **Take Photo** — opens high-quality camera, captures and saves photo to lecture
- **Upload File** — picks any file from phone storage and saves into the lecture
- Notes displayed in order with a rich content system (text, images, files)
- Notes can be **edited**, **renamed**, and **deleted**
- Files/images can be **viewed** (full-screen image viewer, PDF viewer, etc.)
- Notes support three types: `text`, `image`, `file`

### 3.5 Files Screen
- Separate screen for general file management (not tied to subjects/lectures)
- User clicks **"+"** to:
  - **Upload File** — pick any file from phone
  - **Take Photo** — capture with camera
- Files displayed with tiles showing name, type, size
- Files can be **opened**, **shared**, and **deleted**

### 3.6 AI Chat
- Dedicated chat screen for educational Q&A
- Uses **Google Gemini API** (model: `gemini-2.5-flash`)
- **Streaming responses** — AI replies appear in real-time
- Chat maintains **conversation context** (session-based)
- **System prompt** shapes the assistant's educational tone
- User can **reset chat** to start fresh
- Handles API errors gracefully (rate limits, invalid key, etc.)

### 3.7 Settings
- **User Profile** — view and edit name, department, semester
- **Profile Photo** — pick from gallery or take photo, saved locally
- **Theme Selection** — System / Light / Dark mode (persisted)
- **Change Password** — secure password update flow
- **Sign Out** — logs out and returns to sign-in screen
- **Sync Now (Cloud Backup)** — triggers backup popup
- **Clear Cache** — clears all local files and cache
- **Premium Section** — upgrade/manage premium features
- **Help & Support** — contact and FAQ
- **Terms & Conditions** — legal terms screen
- **Privacy Policy** — privacy policy screen
- **About NoteNest** — app info and version

### 3.8 Cloud Backup (Google Drive)
**Biggest feature of the app.**
- **Backup to Google Drive** — compresses all data into a ZIP file and uploads to Google Drive's appDataFolder
- **Restore from Google Drive** — downloads latest backup ZIP and restores all data
- Backup includes:
  - `backup.json` — all subjects, lectures, and notes metadata
  - `note_attachments/` — all images and files from lectures
  - `files/` — all files from the Files screen
- Uses **Google Sign-In** with Drive appData scope
- **Retry logic** with exponential backoff for network failures
- Allows cross-device data recovery (backup on one phone, restore on another)
- Option to include/exclude videos from backup

### 3.9 Additional Features
- **Splash Screen** with animated loading
- **Onboarding Screen** for first-time users
- **Premium/Paywall** system
- **Shimmer loading** effects throughout the app
- **Responsive design** — adapts to tablets and phones
- **Lottie animations** for engaging UI

---

## 4. Technical Architecture

### 4.1 Architecture Pattern: MVVM
```
lib/
├── main.dart                    # App entry point, Firebase + Hive init
├── app.dart                     # App configuration
├── firebase_options.dart        # Auto-generated Firebase config
├── core/
│   ├── constants/               # App colors, strings
│   ├── router/                  # GoRouter navigation
│   ├── services/
│   │   ├── database/            # HiveRepo (local DB operations)
│   │   ├── storage/             # LocalStorageService, FirebaseStorageService
│   │   └── camera/              # CameraCaptureService
│   ├── theme/                   # AppTheme (light/dark), ThemeProvider
│   └── utils/                   # Result type, validators
├── models/                      # Data models (Subject, Lecture, NoteItem, NoteType)
├── repositories/                # FileRepository, UserRepository
├── widgets/                     # BottomNavScaffold, CustomBottomNav
└── features/
    ├── auth/                    # Login, SignUp, ForgotPassword, ChangePassword
    ├── home/                    # HomeScreen, SubjectDetail, LectureDetail
    ├── files/                   # FilesScreen, CameraCapture, ImageView, PdfView
    ├── ai/                      # AiChatScreen, AiService, SystemPrompt
    ├── backup/                  # BackupService, DriveService, BackupPopup
    ├── settings/                # SettingsScreen, SettingsViewModel
    ├── splash/                  # SplashScreen, OnboardingScreen
    ├── about/                   # AboutPopup
    ├── support/                 # SupportScreen
    ├── policy/                  # PrivacyPolicyPopup
    ├── terms/                   # TermsConditionsScreen
    ├── premium/                 # PremiumPaywallScreen, PremiumController
    └── profile_setup/           # ProfileSetupScreen
```

**Total Dart files: 83**

### 4.2 State Management: Riverpod
- `flutter_riverpod` for reactive state management
- Each feature has its own ViewModel (e.g., `HomeViewModel`, `LectureDetailViewModel`)
- ViewModels use `Notifier` pattern with Riverpod providers

### 4.3 Navigation: GoRouter
- Routes: `/splash`, `/onboarding`, `/auth`, `/` (home)
- Auth-based redirect logic (logged in → home, logged out → auth)
- Bottom navigation scaffold with 4 tabs: Home, Files, AI Chat, Settings

---

## 5. Data Models (Hive)

### Subject (TypeId: 4)
| Field       | Type     | Description            |
|-------------|----------|------------------------|
| id          | String   | Unique identifier      |
| name        | String   | Subject name           |
| department  | String?  | Department (optional)  |
| semester    | String?  | Semester (optional)    |
| createdAt   | DateTime | Creation timestamp     |

### Lecture (TypeId: 2)
| Field       | Type     | Description            |
|-------------|----------|------------------------|
| id          | String   | Unique identifier      |
| subjectId   | String   | Parent subject ID      |
| date        | DateTime | Lecture date           |
| title       | String   | Lecture title          |
| createdAt   | DateTime | Creation timestamp     |

### NoteItem (TypeId: 3)
| Field       | Type     | Description            |
|-------------|----------|------------------------|
| id          | String   | Unique identifier      |
| lectureId   | String   | Parent lecture ID      |
| type        | NoteType | text / image / file    |
| text        | String?  | Text content           |
| path        | String?  | File/image path        |
| order       | int      | Display sequence       |
| createdAt   | DateTime | Creation timestamp     |

### NoteType (TypeId: 1)
- `text` — Written note content
- `image` — Captured photo or uploaded image
- `file` — Any uploaded file (PDF, DOC, etc.)

---

## 6. Technology Stack & Packages

### Backend / Cloud Services
| Package              | Purpose                                      |
|----------------------|----------------------------------------------|
| `firebase_core`      | Firebase initialization                      |
| `firebase_auth`      | Email/password + Google authentication        |
| `cloud_firestore`    | Cloud Firestore (user profiles)              |
| `firebase_storage`   | Firebase Storage service                     |
| `google_sign_in`     | Google Sign-In for auth + Drive access       |
| `googleapis`         | Google Drive API for cloud backup             |

### Local Database
| Package              | Purpose                                      |
|----------------------|----------------------------------------------|
| `hive` / `hive_flutter` | Local NoSQL database (subjects, lectures, notes) |
| `hive_generator`     | Code generation for Hive type adapters       |
| `shared_preferences` | Key-value storage (theme, settings)          |

### AI Integration
| Package                | Purpose                                    |
|------------------------|----------------------------------------------|
| `google_generative_ai` | Google Gemini API for AI chat + note generation |

### File & Media Handling
| Package              | Purpose                                      |
|----------------------|----------------------------------------------|
| `file_picker`        | Pick files from phone storage                |
| `image_picker`       | Pick/capture images                          |
| `camera`             | High-quality camera capture                  |
| `photo_view`         | Full-screen image viewing with zoom          |
| `pdfx`               | PDF file viewing                             |
| `open_filex`         | Open files with system app                   |
| `image`              | Image processing                             |
| `archive`            | ZIP compression/decompression for backup     |
| `share_plus`         | Share files to other apps                    |

### UI & Design
| Package                        | Purpose                                |
|--------------------------------|----------------------------------------|
| `google_fonts`                 | Custom typography (Poppins)            |
| `animations`                   | OpenContainer transitions              |
| `shimmer`                      | Loading shimmer effects                |
| `flutter_staggered_animations` | Staggered list/grid animations         |
| `lottie`                       | Animated Lottie illustrations          |
| `flutter_speed_dial`           | Speed dial FAB button                  |
| `convex_bottom_bar`            | Custom bottom navigation               |

### Utility
| Package              | Purpose                                      |
|----------------------|----------------------------------------------|
| `intl`               | Date/time formatting                         |
| `uuid`               | Unique ID generation                         |
| `path_provider`      | Get app storage directories                  |
| `path`               | File path manipulation                       |
| `http`               | HTTP requests                                |
| `url_launcher`       | Open URLs in browser                         |
| `package_info_plus`  | Get app version info                         |
| `android_intent_plus`| Android-specific intents                     |
| `go_router`          | Declarative routing/navigation               |

### Dev Dependencies
| Package              | Purpose                                      |
|----------------------|----------------------------------------------|
| `flutter_test`       | Unit/widget testing framework                |
| `build_runner`       | Code generation runner                       |
| `flutter_lints`      | Lint rules for code quality                  |

---

## 7. Database Design

### 7.1 Local Database (Hive — NoSQL)
- **Per-user boxes**: `subjects_{uid}`, `lectures_{uid}`, `notes_{uid}`
- Data isolated by Firebase Auth user UID
- Key-value storage with type-safe adapters
- Relationships: Subject → Lectures → Notes (parent-child via IDs)

### 7.2 Cloud Database (Firebase Firestore)
- User profile data stored in Firestore
- Fields: name, email, department, semester, photoUrl

### 7.3 Cloud Storage (Google Drive appData)
- Backup ZIP file stored in user's Google Drive appDataFolder
- Contains: `backup.json`, `note_attachments/`, `files/`

---

## 8. Design & Theming

### Color Palette
| Token          | Light               | Dark               |
|----------------|----------------------|---------------------|
| Primary        | `#581B98` (Purple)   | `#581B98`           |
| Secondary      | `#DD0B8C` (Pink)     | `#DD0B8C`           |
| Background     | `#F5F5F7`            | `#121212`           |
| Surface        | White                | `#1E1E1E`           |
| Card           | White                | `#252525`           |
| Text Primary   | `#1A1A2E`            | `#F1F1F1`           |

- **Material 3** design system
- **Poppins** font family
- **Light + Dark** theme support
- Gradient accents using primary → secondary

---

## 9. Reference Thesis Structure (From Sample Theses)

Both reference theses (from University of Malakand, CS Department) follow this 8-chapter structure:

### Front Matter
1. Title Page
2. Approval Certificate
3. Dedication
4. Acknowledgment
5. Abstract
6. Table of Contents

### Chapters
| Chapter | Title                          | Pages (approx) |
|---------|--------------------------------|-----------------|
| 1       | Introduction                   | 5-6             |
| 2       | System Analysis                | 5-6             |
| 3       | Conceptual Database Design     | 5-6             |
| 4       | Physical Database Design       | 4-5             |
| 5       | Functional Modelling           | 5-6             |
| 6       | User Interface & System Features | 6-7           |
| 7       | System Testing                 | 3-4             |
| 8       | Conclusion & Future Work       | 2-3             |

### Back Matter
- References (numbered citation style: [1], [2], etc.)
- Appendices (code, additional diagrams)

### Formatting Conventions
- **Font:** Times New Roman, size 12 for body
- **Headers:** Bold, often ALL-CAPS
- **Spacing:** 1.5 line spacing
- **Margins:** Standard 1-inch
- **Figures/Tables:** Numbered by chapter (e.g., Figure 6.2)
- **Citations:** Numeric style [1], [2]
- **Total pages:** ~50-60 pages

### Content Patterns from Reference Theses
- **Chapter 1 (Introduction):** Background, problem statement, objectives, scope, technologies used, key features, motivation
- **Chapter 2 (System Analysis):** Current vs proposed system comparison, workflows for different user roles
- **Chapter 3 (Conceptual DB Design):** ER Diagrams, data dictionaries, entity-attribute descriptions
- **Chapter 4 (Physical DB Design):** Collection/table structures with data types and constraints
- **Chapter 5 (Functional Modelling):** DFD (Level-0, Level-1), Use Case Diagrams, process specs
- **Chapter 6 (UI & Features):** Screenshots with feature descriptions, screen-by-screen walkthrough
- **Chapter 7 (Testing):** Strategy, environment, detailed test cases with evidence
- **Chapter 8 (Conclusion):** Summary of findings, social impact, future development plans

---

## 10. Key Files Reference

| File | Purpose |
|------|---------|
| `lib/main.dart` | App entry, Firebase + Hive init, RootGate auth router |
| `lib/core/services/database/hive_repo.dart` | All local DB operations (CRUD for subjects, lectures, notes) |
| `lib/features/ai/services/ai_service.dart` | Gemini API integration (chat + streaming) |
| `lib/features/backup/services/backup_service.dart` | ZIP backup creation and restoration |
| `lib/features/backup/services/drive_service.dart` | Google Drive upload/download |
| `lib/core/theme/app_theme.dart` | Full light/dark theme definitions |
| `lib/models/subject.dart` | Subject data model |
| `lib/models/lecture.dart` | Lecture data model |
| `lib/models/note_item.dart` | NoteItem data model (text/image/file) |
| `pubspec.yaml` | All dependencies and package versions |

---

## 11. Development Tools

- **IDE:** VS Code / Android Studio
- **Platform:** Flutter (cross-platform: Android + iOS)
- **Version Control:** Git
- **Build System:** Gradle (Android), Xcode (iOS)
- **Code Generation:** `build_runner` + `hive_generator`

---

> **Status:** Ready for thesis writing. All project info captured above. User will provide template confirmation before we begin drafting.
