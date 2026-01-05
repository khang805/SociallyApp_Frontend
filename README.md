# Socially: Android Social Media UI Kit (Frontend Only)

| **Document Info**    | **Details**              |
| :------------------- | :----------------------- |
| **Document Version** | 1.0                      |
| **Type**             | UI/UX Prototype / UI Kit |
| **Platform**         | Android (Native)         |
| **Language**         | Kotlin & XML             |
| **Architecture**     | MVVM (UI-Centric)        |

---

## 1. Introduction

### 1.1 Project Overview

**Socially** is a high-fidelity social networking application prototype built natively for Android. This project is a **pure frontend implementation**, focusing exclusively on modern **Material Design** principles, complex **XML layouts**, and seamless user navigation.

It serves as a comprehensive **Android UI Kit**, featuring **20+ XML layout files** that represent fully designed screens including authentication, social feeds, user profiles, messaging, and video call interfaces.

The application operates entirely on **local mock data**, making it an excellent reference for building and showcasing complex UI architectures **without any backend dependencies** (No Firebase, No SQL, No REST APIs).

---

### 1.2 Purpose

This codebase is designed for Android developers and UI/UX designers to understand and practice:

* **Complex Layout Design** using `ConstraintLayout` for responsive UIs
* **RecyclerView Adapter Logic** with multiple view types (Stories, Posts, Chats)
* **Navigation Handling** via Activities, Fragments, and Intents
* **UI State Management** such as empty states, input validation, and toggle buttons

---

## 2. Technical Architecture

### 2.1 Design Pattern

The application follows a **UI-Centric MVVM (Model–View–ViewModel)** architecture to maintain clean separation of concerns.

* **View (XML)**
  Defines layout structure, styling, and Material components.

* **Activity / Fragment**
  Handles user interactions, binds data to UI elements, and manages navigation.

* **ViewModel**
  Maintains UI-related state (e.g., Like button toggle, selected tab state).

* **Model (Mock Data)**
  Kotlin data classes such as `User.kt`, `Post.kt`, and `Message.kt`, populated with static dummy data.

---

### 2.2 Technology Stack

| Category          | Technology                           | Usage                                          |
| :---------------- | :----------------------------------- | :--------------------------------------------- |
| **Language**      | Kotlin                               | UI logic, adapters, state handling             |
| **Layouts**       | XML                                  | ConstraintLayout, LinearLayout, RelativeLayout |
| **Design System** | Material Design 3                    | Cards, FABs, Bottom Navigation                 |
| **Lists**         | RecyclerView                         | Feeds, Stories, Chats                          |
| **Images**        | CircleImageView / ShapeableImageView | Circular avatars                               |
| **Navigation**    | Intents & Fragments                  | Screen transitions                             |

---

## 3. Features & Screen Overview

This UI Kit includes **20+ XML layout files** organized into the following modules:

### 3.1 Authentication Suite

* **Splash Screen** – Minimal branding entry point
* **Sign Up Screen** – Name, DOB, Email, Password fields
* **Login Flow**

  * Login Landing Screen
  * Username & Password Entry
  * Forgot Password / Account Recovery UI

---

### 3.2 Main Social Feed

* **Stories Bar** – Horizontal `RecyclerView` for user stories
* **Post Cards** featuring:

  * User avatar & username
  * Location tag (e.g., *Tokyo, Japan*)
  * Media container
  * Like, Comment, Share, Save actions
  * Likes counter & caption

---

### 3.3 Discovery & Search

* **Explore Grid** – Staggered grid layout
* **Category Filters** – Chip groups (Shop, Style, Sports, Auto, Music)
* **Search UI**

  * Recent search history
  * Tabbed results (Top, Accounts, Tags, Places)

---

### 3.4 Messaging & Communication

* **Chat List Screen** – Active conversations with timestamps
* **Direct Message Screen**

  * Incoming & outgoing message bubbles
  * Input bar with attachment & camera icons
* **Video Call UI**

  * Full-screen overlay
  * Controls: Mute, End Call, Flip Camera

---

### 3.5 User Profile

* **Profile Header**

  * Circular profile image
  * Stats: Posts, Followers, Following
  * Bio & website link

* **Content Tabs**

  * Grid view (Posts)
  * Tagged photos view

* **Edit Profile Screen**

  * Update picture, name, username, bio

---

### 3.6 Activity & Notifications

* **Activity Feed**

  * New followers notifications
  * Likes on photos

---

## 4. Project Structure

The project is organized to separate UI logic from reusable components:

```text
app/src/main/
├── java/com/example/socially/
│   ├── adapters/        # FeedAdapter, StoryAdapter, ChatAdapter
│   ├── models/          # User, Post, Message data classes
│   ├── utils/           # MockDataGenerator.kt
│   └── ui/              # Activities & Fragments
└── res/layout/
    ├── activity_login.xml
    ├── fragment_home.xml
    ├── item_post.xml
    ├── item_chat_message.xml
    ├── fragment_profile.xml
    └── activity_video_call.xml
```

---

## 5. Setup Guide

### 5.1 Prerequisites

* **Android Studio:** Iguana (2023.2.1) or newer
* **Android SDK:** API Level 24 (Android Nougat) or higher
* **Java:** JDK 17 (Recommended)

---

### 5.2 Installation Steps

1. **Clone the Repository**

```bash
git clone https://github.com/khang805/SociallyApp_Frontend
cd socially-ui-kit
```

2. **Open in Android Studio**

* Launch Android Studio
* Select **File → Open**
* Navigate to the cloned project directory

3. **Sync Gradle**

Allow Android Studio to download required UI dependencies.

> **Note:** No `google-services.json`, API keys, Firebase, or backend configuration is required.

4. **Run the Application**

* Select an emulator (Pixel 6 / Pixel 7 recommended)
* Press the **Run (▶)** button
* The app launches with pre-filled mock data

---

## 6. Conclusion

The **Socially (Frontend-Only)** project provides a strong foundation for building modern social media applications. By eliminating backend complexity, it allows developers to focus purely on **UI polish, interaction design, and layout mastery**.

This UI Kit demonstrates:

* Complex XML-based layouts
* Multi-view-type RecyclerView adapters
* Material Design navigation patterns

The project is **backend-ready** and can be easily integrated with REST APIs, GraphQL, or Firebase by replacing the `MockDataGenerator` with real data sources.
