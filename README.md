# MusicalGym App: MVP Plan

## 1. Overview

MusicalGym is designed to help musicians record their practice times for various instruments and activities, providing insightful reports to monitor progress and maintain motivation. The MVP focuses on:

1. Creating basic user profiles.  
2. Tracking practice sessions (manual or timer-based).  
3. Providing basic insights through bar and pie (pizza) charts.  
4. Supporting two initial languages (English, Brazilian Portuguese), with an architecture designed for easy expansion to additional locales.  
5. Enabling manual data import/export for backup or device migration.

---

## 2. MVP Definition

### 2.1. Minimal User Profiles

Since no online features are included at launch, user profiles will remain local only. Even so, we gather essential data to facilitate future expansions:

- **Full Name**  
- **Username** (for potential future login or sharing features)  
- **Email** (for user identification and future communication)  
- **Registration Date** (automatically read from the device calendar)  
- **Default Session Duration** (defaults to 60 minutes, can be adjusted)  
- **Instrument(s)** (one or more; at least one mandatory instrument upon setup)  
- **Profile Picture** (optional; sourced from camera or photo library)

> **Note:**  
> - Phone number is omitted for the MVP, but could be integrated later if needed for notifications or user verification.  

---

### 2.2. Tracking Practice Sessions

Central to MusicalGym is the ability to log and review practice sessions:

1. **Manual Entry**  
   - Users can manually add a completed practice session (date, duration, instrument, activity, notes).  

2. **Timer-Based Sessions**  
   - **Fixed-Time Session**: User sets a target duration. The app counts down, and upon reaching zero, a pop-up message and sound alert notify the user.  
   - **Open-Ended Session**: The timer counts upward until manually stopped by the user.

3. **Pausing and Resuming**  
   - Any active session can be paused. A secondary timer displays the pause duration. Once resumed, the session timer picks up where it left off.

4. **Abandoned Session Prompt**  
   - To prevent infinite sessions if a user forgets to stop an open-ended session, after a user-configurable number of minutes (default 60), the app prompts: “Are you still practicing?”  
   - If unanswered within a short window, the session automatically stops and logs the time until that prompt triggered.

5. **Session Data Fields**  
   - **Instrument**
   - **Activity**
   - **Date**
   - **Duration**
   - **Notes**

6. **Activity Colors**  
   - Each activity can have an associated color. This color will be used in visual diagrams (pie/bar charts) for easy differentiation.

---

### 2.3. Insights & Reporting

Users can access insights on how they’re practicing:

- **Visualizations**  
  - **Pie (“Pizza”) Charts**: Offers a breakdown of total practice time by activity for a selected period.  
  - **Bar Charts**: Enables time-based comparisons (e.g., practice per activity by day/week/month).  

- **Report Scope**  
  - The user can choose to view data by day, week, month, or lifetime.  
  - Activities can be toggled on/off in charts to compare only specific groups.  

---

### 2.4. Internationalization

Two languages will be supported initially:

- **English (EN-US)**  
- **Brazilian Portuguese (PT-BR)**  

However, **the internationalization architecture is designed for easy expansion** to other languages (German, French, Italian, Spanish, etc.).

---

### 2.5. Data Sharing / Transfer

- **Manual JSON Export/Import**  
  - Users can export all session data (including user profile information) as a JSON file and later import it on another device.  
  - This approach serves as a first step in enabling data backup, basic migration, or sharing without requiring a backend.

---

### 2.6. Tech Stack

1. **Framework**: **React Native with Expo**  
   - Cross-platform support for both iOS and Android.  
   - Rapid development and hot-reloading for quick testing.

2. **Local Database**: **SQLite**  
   - Lightweight, performant, and well-supported on mobile devices.  
   - Data model can adapt for future cloud sync.
  
3. **Development Environment and Source Control:** **GitHub**
   - Allows insights on the state of development to all project members

---

## 3. Outlook & Future Enhancements

Beyond the MVP, several expansions are planned:

1. **Gamification & Achievements**  
   - Reward users with badges for milestones (e.g., total practice hours, consecutive practice days).  
   - Achievements would be stored locally for dynamic updates, eventually synced to a web dashboard.

2. **Metronome**  
   - Provide a built-in metronome tool that can function inside or outside a practice session.

3. **Tuner**  
   - A tuner utility featuring a needle display for pitch accuracy (without reference tones).

4. **Cloud Backend & Web Dashboard**  
   - Enable real-time syncing across devices and a browser-based dashboard.  
   - Allow multi-user scenarios, data sharing with friends, advanced analytics, and automated achievements updates.

5. **Full Internationalization**  
   - Extending language support to German, French, Italian, Spanish, or any others as needed.

6. **Advanced Data Analysis**  
   - More sophisticated insights and filtering options (e.g., tagging sessions by “exam pieces,” “classical,” “jazz,” etc.).  
   - PDF exports, collaborative sharing, and user commenting.
