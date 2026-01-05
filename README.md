# Socially: Android Social Media UI Kit (Frontend Only)

---

## 1. Introduction

### 1.1. Project Overview
**"Socially"** is a high-fidelity social networking application prototype built natively for Android. This project is a **pure frontend implementation**, focusing exclusively on modern **Material Design** principles, complex **XML layouts**, and seamless user navigation.

It serves as a comprehensive **UI Kit** for developers, featuring a robust set of screens including authentication, social feeds, user profiles, and chat interfaces. It operates using **local mock data**, making it an excellent reference for building complex UI architectures without the overhead of backend dependencies (No Firebase, No SQL, No APIs).

### 1.2. Purpose
This codebase is designed for Android developers and UI/UX designers to understand:
* **Complex Layouts:** Implementing `ConstraintLayout` for responsive designs.
* **Adapter Logic:** Managing multiple view types in `RecyclerView` (e.g., Stories vs. Posts).
* **Navigation:** Handling fragment transactions and Intent-based navigation.
* **UI States:** Managing visual states for empty lists, input validation, and toggle buttons.

---

## 2. Technical Architecture

### 2.1. Design Pattern
The application follows a **UI-Centric MVVM** (Model-View-ViewModel) pattern. This separation of concerns ensures that the UI code remains clean and the data logic is testable.



* **View (XML):** Handles the layout structure and styling.
* **Activity/Fragment:** Binds data to views and handles user interactions (Clicks, Scrolls).
* **ViewModel:** Manages UI state (e.g., toggling "Like" icons) and fetches data from the Mock Repository.
* **Model (Mock Data):** Kotlin data classes (`User.kt`, `Post.kt`) populated with static dummy data to simulate a populated application.

### 2.2. Technology Stack

| Category | Technology | Usage |
| :--- | :--- | :--- |
| **Language** | Kotlin | UI Logic & Adapter bindings. |
| **Layouts** | XML | UI definition (ConstraintLayout, RelativeLayout). |
| **Components** | Material Design 3 | Cards, Floating Action Buttons, Bottom Navigation. |
| **Lists** | RecyclerView | Efficient scrolling lists for Feeds and Chats. |
| **Images** | CircleImageView | Circular avatars for profiles and stories. |
| **Navigation** | Intents | Moving between Activities. |

---

## 3. Features & Screen Overview

This UI Kit includes over 15+ distinct screens organized into the following modules:

### 3.1. Authentication Suite
* **Splash Screen:** Minimalist branding entry point.
* **Sign Up:** Comprehensive form fields (Name, DOB, Email) with polished input layouts.
* **Login Flow:**
    * Main Login Landing (Switch accounts, Sign up option).
    * Credential Entry (Username/Password).
    * Forgot Password / Account Recovery UI.

### 3.2. Main Social Feed
* **Stories Bar:** Horizontal scrollable list (RecyclerView style) for user statuses/stories at the top.
* **Post Cards:** Detailed layout including:
    * User Avatar & Username.
    * Location tags (e.g., "Tokyo, Japan").
    * Post Image/Media container.
    * Action Buttons: Like, Comment, Share, Save.
    * Likes Count & Caption text.

### 3.3. Discovery & Search
* **Explore Grid:** Staggered grid layout for discovering new content.
* **Category Tabs:** Chip groups for filtering (Shop, Style, Sports, Auto, Music).
* **Search Interface:**
    * Recent search history list.
    * Tabbed results: Top, Accounts, Tags, Places.

### 3.4. Messaging & Communication
* **Chat List:** Vertical list of active conversations with last message previews and timestamps.
* **Direct Message (DM) Screen:**
    * Incoming/Outgoing message bubbles.
    * Input bar with attachment and camera icons.
* **Video Call UI:** Full-screen video interface overlay with controls (Mute, End Call, Flip Camera).

### 3.5. User Profile
* **Profile Header:**
    * Circular Profile Image.
    * Stats: Posts, Followers, Following.
    * Bio text and website link.
* **Content Tabs:** Grid view vs. Tagged photos view.
* **Edit Profile:** Form to update display picture, name, username, and bio.

### 3.6. Activity & Notifications
* **Activity Feed:** List styling for "New Followers" and "Likes" on photos.

---

## 4. Project Structure

The project is organized to separate screens logic from reusable components:

```text
app/src/main/
├── java/com/example/socially/
│   ├── adapters/       # Recycler Adapters (FeedAdapter, StoryAdapter, ChatAdapter)
│   ├── models/         # Data Classes (Post, User, Message)
│   ├── utils/          # MockDataGenerator.kt (Static data source)
│   └── ui/             # Activities & Fragments
└── res/layout/
    ├── activity_login.xml         # Auth Screens
    ├── fragment_home.xml          # Main Feed
    ├── item_post.xml              # Single Post Card Design
    ├── item_chat_message.xml      # Chat Bubbles
    ├── fragment_profile.xml       # Profile Layout
    └── activity_video_call.xml    # Video Call Overlay

## 5. Setup Guide
5.1. Prerequisites
Android Studio: Version Iguana (2023.2.1) or newer.

Android SDK: API Level 24 (Nougat) or higher.

Java: JDK 17 (Recommended).

5.2. Installation Steps
1. Clone the Repository

Bash

git clone [https://github.com/your-username/socially-ui-kit.git](https://github.com/your-username/socially-ui-kit.git)
cd socially-ui-kit
2. Open in Android Studio

Launch Android Studio.

Select File > Open and navigate to the cloned directory.

3. Sync Gradle

Allow Android Studio to download the necessary UI dependencies (Material Components, ConstraintLayout, etc.).

Note: No google-services.json, API keys, or backend server setup is required.

4. Run the Application

Select an Emulator (Pixel 6 or 7 recommended for best density visualization).

Press the Run (▶) button.

The app will launch with pre-filled mock data.

## 6. Conclusion
The "Socially" (Frontend) project stands as a robust foundation for any modern social media application. By stripping away backend complexities, it allows developers to focus purely on perfecting the visual experience and user interactions.

This kit provides a pixel-perfect implementation of:

Complex XML Layouts

Multiple ViewType Adapters

Material Design Navigation

It is ready to be connected to any backend solution (REST API, GraphQL, or Firebase) by simply replacing the MockDataGenerator with actual network calls.
