---
id: 006-design
title: Design System & Vibe
description: Outlines the visual style, color palette, typography, and overall user experience principles for the platform.
type: doc
subtype: core
status: draft
sequence: 6
tags:
  - design
  - ui
  - ux
createdAt: "2023-10-27T10:00:00Z"
updatedAt: "2023-10-27T10:00:00Z"
---

## 1. Core Principles & Vibe

The design of COCKMAXXING must embody our core values: **Trustworthy, Supportive, and Empowering**. The user interface should feel like a secure, modern tool, not a sleazy or sensationalist forum. It must be clean, data-forward, and easy to navigate, inspiring confidence and encouraging consistent use. We are creating a private sanctuary for personal growth, and the design must reflect that at every touchpoint.

*   **Trustworthy:** The UI will be clean, professional, and transparent. Clear privacy indicators, intuitive settings, and an absence of dark patterns are paramount. The design should feel stable and reliable.
*   **Supportive:** The color palette and typography will be calm and encouraging. Community interactions will be framed positively. The overall feel should be welcoming and non-judgmental.
*   **Empowering:** Data visualizations will be clear and insightful. Users should feel in control of their data and their journey. The design should make complex information easy to understand and act upon.

## 2. Color Palette

The color scheme is chosen to be modern, calming, and focused. It avoids aggressive or overly masculine colors, opting for a more mature and tech-oriented feel.

*   **Primary Color (`primaryColor`):** `#8b5cf6` (Violet). This color is modern, unique, and conveys a sense of purpose and creativity. It will be used for primary buttons, active navigation links, and key interactive elements.
*   **Accent Color (`accentColor`):** `#06b6d4` (Cyan). A vibrant yet cool accent used for secondary CTAs, highlights, notification badges, and positive data trends in charts.
*   **Neutral Dark (`neutralDark`):** `#1a202c`. A deep, slightly blue-tinted charcoal for primary text, backgrounds in dark mode, and creating strong contrast.
*   **Neutral Light (`neutralLight`):** `#f8fafc`. A clean, slightly cool off-white for page backgrounds in light mode, ensuring content is highly readable.
*   **Supporting Colors:**
    *   **Success:** `#22c55e` (Green) for success messages and positive indicators.
    *   **Warning:** `#f59e0b` (Amber) for warnings or non-critical alerts.
    *   **Danger:** `#ef4444` (Red) for error messages, delete confirmations, and critical alerts.

## 3. Typography

Typography will be clean, legible, and modern, prioritizing readability for both short-form UI text and long-form content in forums and the resource library.

*   **Font Family (`fontFamily`):** **Inter**. This sans-serif typeface is highly legible at all sizes and has excellent screen rendering. Its neutral yet friendly character is a perfect fit for the platform's vibe.
*   **Headings (H1, H2, H3):** Will use a heavier weight (e.g., `font-bold` or `font-semibold`) to create a clear visual hierarchy.
*   **Body Text:** Will use a regular weight (`font-normal`) with a comfortable line height (e.g., `leading-relaxed`) to ensure long-form content is easy to read.

## 4. Layout & Navigation

Consistency in layout is key to creating an intuitive user experience.

*   **Navigation Pattern:** A persistent **sidebar** will be used for the main navigation in the authenticated app. This provides quick, consistent access to all core pages: Dashboard, Forums, Progress Tracker, Resources, and Settings. The sidebar will be collapsible on larger screens and will transform into a slide-out menu on mobile devices.
*   **Layout Grid:** A standard 12-column grid system will be used for consistency. Content will be constrained to a maximum width to ensure readability on large monitors.
*   **Spacing & White Space:** Generous use of white space will be employed to reduce cognitive load, improve focus, and give the interface a clean, uncluttered feel. A consistent spacing scale (e.g., based on multiples of 4px or 8px) will be used for all margins and padding.

## 5. Key Components

*   **Buttons:** Primary buttons will use the `primaryColor` with white text. Secondary buttons will be outlined or use a more subdued color. States (hover, focus, disabled) will be clearly defined.
*   **Forms:** Inputs will be clean and simple, with clear labels and validation messages. Focus states will be prominent to improve accessibility.
*   **Charts:** Data visualizations on the **Progress Tracker Page** will be clean and easy to read, using the `primaryColor` and `accentColor` for data lines against a neutral background. Tooltips will provide detailed information on hover.