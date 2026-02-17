---
id: 003-pages
title: Pages & UI Structure
description: An overview of the application's key pages, their routes, purpose, and the core components they contain.
type: doc
subtype: core
status: draft
sequence: 3
tags:
  - ui
  - pages
  - frontend
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

## 1. Introduction

This document defines the primary pages (or views) that constitute the COCKMAXXING application. Each page serves a distinct purpose in the user journey, from initial discovery to daily engagement. The structure is designed to be intuitive, with a clear separation between public-facing marketing content and the private, authenticated user experience. All authenticated pages will be accessible via a persistent sidebar navigation pattern, as specified in the **Design System** document.

## 2. Public Pages (Unauthenticated)

These pages are accessible to all visitors and are focused on education, trust-building, and user acquisition.

### 2.1. Landing Page (`/`)
*   **Route:** `home`
*   **Purpose:** To introduce COCKMAXXING, articulate its value proposition, and convert visitors into registered members.
*   **Key Sections & Components:**
    *   **Hero Section:** A compelling headline, the tagline ("A community-driven platform for safe, informed, and empowering penis enlargement journeys."), and a primary call-to-action (CTA) button: "Join the Community".
    *   **Problem/Solution:** A concise explanation of the challenges in this space and how our platform provides a trustworthy solution.
    *   **Features Showcase:** A visually engaging overview of the three core pillars: Community Forums, Progress Tracking, and the Resource Library.
    *   **Testimonials:** Placeholder for future member testimonials to build social proof.
    *   **FAQ:** Answers to common questions regarding privacy, safety, and cost.

### 2.2. Login/Signup Page (`/auth`)
*   **Route:** `auth`
*   **Purpose:** To provide a secure and simple interface for new user registration and existing user login.
*   **Key Sections & Components:**
    *   **Tabbed Interface:** Toggles between 'Login' and 'Sign Up' forms.
    *   **Signup Form:** Fields for `email`, `password`, and anonymous `username`.
    *   **Login Form:** Fields for `email` and `password`.
    *   **Social Login:** A prominent "Continue with Google" button for streamlined authentication, powered by Firebase Authentication.
    *   **Forgot Password Link:** A modal flow to initiate the password reset process.

## 3. Authenticated Pages

These pages form the core application experience and are only accessible after a user has logged in.

### 3.1. Dashboard (`/dashboard`)
*   **Route:** `dashboard`
*   **Purpose:** The user's personalized home base, providing a high-level overview of their journey and recent community activity.
*   **Key Sections & Components:**
    *   **Welcome Message:** Personalized greeting (e.g., "Welcome back, [username]!").
    *   **Progress Snapshot:** A compact chart showing the user's most recent measurement trend (e.g., last 30 days).
    *   **Recent Forum Activity:** A feed of the latest or most popular threads from the **Community Forums**.
    *   **Quick Access:** Buttons to "Log Today's Progress" or "Create New Post".

### 3.2. Community Forums (`/forums`)
*   **Route:** `forums`
*   **Purpose:** The central hub for all community discussions.
*   **Key Sections & Components:**
    *   **Category List:** A clear listing of all forum categories.
    *   **Thread List:** Displays threads within a selected category, showing title, author, reply count, and last activity.
    *   **Search & Filter Bar:** Allows users to search for content and filter by tags.
    *   **New Post Button:** A floating action button or prominent button to initiate the **Participate in a Forum Discussion** flow.

### 3.3. Progress Tracker (`/progress`)
*   **Route:** `progress`
*   **Purpose:** The dedicated interface for the **Progress Tracking & Journaling** feature.
*   **Key Sections & Components:**
    *   **Measurement Charts:** Large, interactive charts visualizing length and girth data over selectable time ranges.
    *   **Log Input Form:** The primary interface for the **Logging Daily Progress** flow, allowing users to add new entries.
    *   **Historical Entries:** A reverse chronological list of all past logs, allowing for edits or deletions.
    *   **Private Photo Gallery:** A secure, grid-based view of uploaded progress photos.

### 3.4. Resource Library (`/resources`)
*   **Route:** `resources`
*   **Purpose:** A browsable and searchable collection of all curated content.
*   **Key Sections & Components:**
    *   **Search & Filter:** Allows users to find resources by keyword, category, or tag.
    *   **Resource List:** Displays content in a card-based layout, showing title, type, and a brief summary.

### 3.5. Settings (`/settings`)
*   **Route:** `settings`
*   **Purpose:** A centralized location for all user account and preference management.
*   **Key Sections & Components:**
    *   **Tabbed Navigation:** Sections for 'Account', 'Profile Privacy', and 'Notifications'.
    *   **Account Settings:** Forms to change email and password.
    *   **Privacy Settings:** Toggles to control profile visibility.
    *   **Data Management:** Buttons to trigger data export and account deletion.