Weight Tracker App - CS-360 Portfolio Artifact
App Summary

Weight Tracker is an Android app that helps users log their daily weight, set a goal weight, and receive an SMS notification when they hit it. It supports secure account creation and login, with all data stored privately on-device using SQLite - no internet connection required.
UI and User-Centered Design

The app uses three screens: a login/registration screen, an SMS permission screen, and a dashboard where users can add, edit, and delete weight entries. Each screen was kept minimal to reduce friction. The dashboard renders a scrollable grid of entries with inline Edit and Delete buttons, and gracefully handles the empty state with a prompt to add the first entry.
Coding Approach

Database logic was separated into a dedicated DatabaseHelper class managing two tables - users and weight_entries-keeping Activities focused on UI behavior. Input was validated before any database operation, and runtime permission handling for SEND_SMS was designed to degrade gracefully: if the user declines, the app continues fully without notifications.
Testing

The app was tested on the Android Emulator across phone and tablet screen sizes. Testing validated login edge cases (empty fields, wrong credentials, duplicate usernames), CRUD operations on weight entries, goal detection logic, and SMS permission grant/deny flows.
Innovation and Challenges

The goal detection logic required comparing each new or updated entry against the stored goal and conditionally triggering an SMS or a toast depending on permission state - all without blocking the UI or crashing on emulators where SMS is unavailable.
Strongest Component

The DatabaseHelper class best demonstrates technical skill - implementing a relational SQLite schema with user authentication and scoped weight entry CRUD, cleanly abstracted from the rest of the app.
