# Chapter 2 – Project Planning & UX Design

## Defense Dictionary & Terminology Guide

This document contains the most important technical, UX, UI, design, planning, and healthcare-related terms used in Chapter 2 of the Najda project.

---

# Requirements & Planning

## Ideation

**Meaning:** The process of generating and refining project ideas.

**In Najda:** The stage where we identified healthcare problems in Algeria and imagined an AI-powered Darija triage solution.

---

## Requirement

**Meaning:** Something the system must do or must respect.

**In Najda:** Features such as appointment booking, emergency alerts, and AI triage.

---

## Functional Requirement (FR)

**Meaning:** Describes what the system does.

**In Najda:** Book appointments, analyze symptoms, send emergency alerts.

---

## Non-Functional Requirement (NFR)

**Meaning:** Describes how well the system performs.

**In Najda:** Security, speed, scalability, usability, and reliability.

---

## Traceability

**Meaning:** The ability to connect a feature back to its original requirement.

**In Najda:** Every screen and API can be linked to one or more project requirements.

---

## Constraint

**Meaning:** A limitation or rule imposed on the system.

**In Najda:** Triage responses must be generated within a few seconds.

---

## Scalability

**Meaning:** The ability of a system to handle growth.

**In Najda:** Supporting more hospitals, doctors, and users without redesigning the platform.

---

## Reliability

**Meaning:** The ability of a system to operate consistently and correctly.

**In Najda:** The platform remains available even during peak usage periods.

---

## Maintainability

**Meaning:** How easy it is to update and maintain the system.

**In Najda:** Modular architecture and clean code make future updates easier.

---

## Extensibility

**Meaning:** The ability to add new features later.

**In Najda:** Supporting additional medical specialties or languages.

---

## Role-Based Access Control (RBAC)

**Meaning:** A security model where permissions depend on the user's role.

**In Najda:** Patients, doctors, receptionists, and administrators have different permissions.

---

# UX & User Research

## UX (User Experience)

**Meaning:** The overall experience users have while using a product.

**In Najda:** Making healthcare access simple, fast, and understandable.

---

## UI (User Interface)

**Meaning:** The visual elements users interact with.

**In Najda:** Forms, buttons, dashboards, cards, and navigation components.

---

## Persona

**Meaning:** A fictional representation of a target user.

**In Najda:** Patient, doctor, and receptionist personas were created to guide design decisions.

---

## Pain Point

**Meaning:** A problem or frustration experienced by users.

**In Najda:** Long waiting times and difficulty accessing healthcare information.

---

## User Flow

**Meaning:** The path users follow to complete a task.

**In Najda:** Patient → Describe symptoms → AI analysis → Appointment recommendation.

---

## Information Architecture (IA)

**Meaning:** The organization and structure of information within a system.

**In Najda:** Structuring screens and navigation for all user roles.

---

## User Journey

**Meaning:** The complete experience of a user from beginning to end.

**In Najda:** From reporting symptoms to receiving healthcare assistance.

---

## Workflow

**Meaning:** A sequence of tasks required to achieve a goal.

**In Najda:** Doctor consultation workflow or emergency alert workflow.

---

## Onboarding

**Meaning:** Introducing new users to the product.

**In Najda:** Helping users understand how to use triage and appointment features.

---

## Mobile-First Design

**Meaning:** Designing for mobile devices before desktop devices.

**In Najda:** Most users access the platform through smartphones.

---

## Darija-First Design

**Meaning:** Designing primarily for Algerian Darija speakers.

**In Najda:** The platform is built around local language usage rather than translating later.

---

# UI Design Terms

## Wireframe

**Meaning:** A low-detail blueprint of a screen.

**In Najda:** Early screen layouts before applying colors and visual styling.

---

## Low-Fidelity Design

**Meaning:** A rough and simple design used during planning.

**In Najda:** Initial wireframes and layout sketches.

---

## High-Fidelity Design

**Meaning:** A polished and detailed design close to the final product.

**In Najda:** The final prototype shown before development.

---

## Prototype

**Meaning:** An interactive representation of the future application.

**In Najda:** Used to test navigation and usability before coding.

---

## Information Hierarchy

**Meaning:** Organizing content according to importance.

**In Najda:** Emergency information is displayed more prominently.

---

## Layout

**Meaning:** The arrangement of visual elements on a page.

---

## CTA (Call To Action)

**Meaning:** A button or element encouraging users to take action.

**In Najda:** "Trigger Emergency Alert" or "Book Appointment".

---

## Dashboard

**Meaning:** A central screen displaying key information.

**In Najda:** Doctor dashboard, receptionist dashboard, and admin dashboard.

---

# Design System

## Design System

**Meaning:** A collection of reusable design rules and components.

**In Najda:** Ensures consistency across all applications and platforms.

---

## Single Source of Truth

**Meaning:** One official place where design values are stored.

**In Najda:** Figma variables and design tokens.

---

## Design Token

**Meaning:** Reusable design values such as colors and spacing.

**Examples:** Colors, font sizes, border radius, spacing.

---

## Primitive Component

**Meaning:** A basic reusable UI element.

**Examples:** Button, Input, Checkbox.

---

## Composite Component

**Meaning:** A component built from multiple primitive components.

**Example:** Form field with label and validation.

---

## Component Library

**Meaning:** A collection of reusable components.

**In Najda:** Shared between web and mobile interfaces.

---

## Domain Component

**Meaning:** A component specific to business logic.

**In Najda:** Appointment cards, triage result cards, emergency cards.

---

## Variant

**Meaning:** Different versions of the same component.

**Examples:** Primary button, secondary button, danger button.

---

## Hover State

**Meaning:** The appearance of a component when the mouse pointer is over it.

---

## Focus State

**Meaning:** The appearance of a component when selected via keyboard navigation.

---

## Disabled State

**Meaning:** A component that cannot currently be interacted with.

---

## Loading State

**Meaning:** Temporary visual feedback while data is being loaded.

---

# Branding & Visual Identity

## Visual Identity

**Meaning:** The visual representation of a brand.

**In Najda:** Logo, typography, colors, icons, and marketing materials.

---

## Typography

**Meaning:** The style and organization of text.

**In Najda:** Font families, sizes, weights, and hierarchy.

---

## Type Scale

**Meaning:** A structured system of font sizes.

**In Najda:** Creates consistency throughout the application.

---

## Color Palette

**Meaning:** The set of approved brand colors.

**In Najda:** Primary Blue, Consultation Orange, and Urgent Red.

---

## Iconography

**Meaning:** The collection of icons used within a system.

**In Najda:** Medical and navigation icons.

---

## Wordmark

**Meaning:** A logo made primarily from text.

**In Najda:** The "Najda" text logo.

---

## Brand Mark

**Meaning:** The symbol part of a logo.

**In Najda:** The soundwave-inspired "N" symbol.

---

## Logo Lockup

**Meaning:** The combination of the logo symbol and text.

**In Najda:** Soundwave icon + Najda wordmark.

---

## Graphic Charter

**Meaning:** Official branding guidelines.

**In Najda:** Rules governing logo use, colors, typography, and marketing assets.

---

## Collateral

**Meaning:** Marketing and communication materials.

**In Najda:** Posters, flyers, banners, and social media graphics.

---

## Tagline

**Meaning:** A short phrase representing the brand.

**In Najda:** "From your voice to full recovery."

---

# Accessibility

## Accessibility (A11Y)

**Meaning:** Designing products usable by everyone, including people with disabilities.

---

## RTL (Right-To-Left)

**Meaning:** Interface support for languages written from right to left.

**In Najda:** Arabic language support.

---

## Keyboard Navigation

**Meaning:** Using the application without a mouse.

---

## Focus Ring

**Meaning:** A visual indicator showing the currently selected element.

---

# Healthcare & Platform Concepts

## Triage

**Meaning:** Determining the urgency and priority of a medical case.

**In Najda:** AI classifies symptoms into consultation or urgent care categories.

---

## Speech-to-Text (STT)

**Meaning:** Converting spoken language into text.

**In Najda:** Converts spoken Darija symptoms into text for analysis.

---

## Geolocation

**Meaning:** Determining the user's physical location.

**In Najda:** Used during emergency alert situations.

---

## Analytics Dashboard

**Meaning:** A screen displaying statistics and metrics.

**In Najda:** Used by administrators to monitor system activity.

---

## GPS Coordinates

**Meaning:** Latitude and longitude values representing a location.

**In Najda:** Sent with emergency alerts.

---

## Real-Time

**Meaning:** Data is updated instantly with minimal delay.

**In Najda:** Emergency notifications are delivered immediately.

---

# Important Defense Tip

When answering jury questions:

* Start with the general definition.
* Explain the concept in simple English.
* Connect it back to the Najda project.
* Give a concrete example whenever possible.

Example:

**Q: What is a Design System?**

**Answer:**
"A Design System is a collection of reusable design rules and components that ensure consistency across an application. In Najda, we created a design system containing colors, typography, buttons, forms, and cards so that both the web and mobile interfaces share the same visual identity and user experience."

