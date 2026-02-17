---
id: 005-flows
title: User Flows
description: Step-by-step descriptions of key user interactions and processes within the application.
type: doc
subtype: core
status: draft
sequence: 5
tags:
  - user-flow
  - ux
  - product
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

## 1. Introduction

This document outlines the critical user flows within the COCKMAXXING platform. These flows describe the step-by-step journey a user takes to accomplish key tasks. Understanding these processes is essential for designing an intuitive user experience and for engineering the underlying logic. Each flow references specific pages and features detailed in the **Pages & UI Structure** and **Core Features** documents.

## 2. New User Signup & Onboarding (`user-onboarding-signup`)

This flow covers the critical process of converting a visitor into an engaged community member.

*   **Trigger:** User clicks the 'Sign Up' button on the **Landing Page**.
*   **Steps:**
    1.  **Navigate to Auth Page:** The user is directed to the `/auth` page, with the 'Sign Up' tab active.
    2.  **Input Credentials:** The user enters a valid email, a secure password, and a desired anonymous `username`. The system performs real-time validation to check for email format and username availability (querying the `users` collection).
    3.  **Account Creation:** Upon submission, the system creates a new user account in Firebase Authentication. Simultaneously, a new document is created in the `users` collection with the user's UID, email, username, and default privacy/notification settings.
    4.  **First Login & Onboarding:** The user is automatically logged in and redirected to the `/dashboard`. The system initiates a brief, interactive onboarding tour. The tour highlights the main navigation items: Dashboard, Forums, and Progress Tracker.
    5.  **Initial Prompt:** As part of the tour, the user is prompted to set an optional avatar and review their initial privacy settings on the `/settings` page to build immediate trust.
    6.  **Flow Completion:** The user completes or dismisses the tour and can now freely explore the platform. A 'Welcome' forum thread might be highlighted on their dashboard to encourage their first interaction.

## 3. Logging Daily Progress (`log-daily-progress`)

This is a core, recurring flow for engaged users, central to the platform's value proposition.

*   **Trigger:** User clicks 'Add New Entry' or a similar CTA on the **Progress Tracker Page** (`/progress`).
*   **Steps:**
    1.  **Open Entry Form:** A modal or dedicated section of the page displays the form for a new progress entry.
    2.  **Input Data:** The user selects the date (defaults to today) and inputs their data into the form fields: `measurements` (length, girth), `routine_details`, and personal `notes`.
    3.  **Upload Photos (Optional):** The user can click an 'Upload Photos' button, which opens a file selector. They can select one or more images, which are then uploaded directly to a private, user-specific folder in Firebase Storage.
    4.  **Save Entry:** The user clicks 'Save Progress'.
    5.  **System Action:** The system creates a new document in the `progress_entries` collection, associating it with the `user_id`. The URLs of any uploaded photos are included in the `private_photo_urls` array.
    6.  **UI Update:** The form closes, and the charts and historical entry list on the `/progress` page are instantly updated with the new data, providing immediate visual feedback.

## 4. Participating in a Forum Discussion (`participate-forum-thread`)

This flow describes how users engage with the community, either by creating new topics or replying to existing ones.

*   **Trigger:** User clicks 'New Post' or the 'Reply' button on the **Community Forums Page** (`/forums`).
*   **Steps:**
    1.  **Navigate & Select:** The user browses the forum categories and clicks on a thread title that interests them, or clicks the 'New Post' button.
    2.  **Compose Content:**
        *   **For a New Post:** The user is taken to a new page where they input a `title`, select a `category`, and write the `content` of their post in a rich-text editor.
        *   **For a Reply:** The user scrolls to the bottom of the thread and uses the reply editor to compose their comment.
    3.  **Submit Post/Reply:** The user clicks 'Submit'.
    4.  **System Action:**
        *   **For a New Post:** A new document is created in the `posts` collection.
        *   **For a Reply:** A new document is created in the `comments` subcollection of the parent post. The `comment_count` on the parent `post` document is atomically incremented.
    5.  **UI Update & Notification:** The page refreshes to show the newly created post or comment. The system may trigger notifications for users subscribed to the thread.

## 5. Update Account & Privacy Settings (`update-account-privacy`)

This flow empowers users to maintain control over their personal information and experience.

*   **Trigger:** User navigates to the **Settings Page** (`/settings`).
*   **Steps:**
    1.  **Select Category:** The user selects a settings category, such as 'Profile Privacy'.
    2.  **Modify Settings:** The user interacts with the UI elements, for example, toggling the `measurements_visible_to_all` setting from `false` to `true`.
    3.  **Save Changes:** The user clicks the 'Save Changes' button for that section.
    4.  **System Action:** The system sends an update request to Firestore to modify the user's document in the `users` collection, specifically updating the `privacy_settings` object.
    5.  **Confirmation:** The UI displays a success toast or message (e.g., "Privacy settings updated.") confirming the change has been saved.