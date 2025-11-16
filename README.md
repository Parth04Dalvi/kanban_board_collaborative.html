# kanban board collaborative

<img width="588" height="519" alt="image" src="https://github.com/user-attachments/assets/93cf76aa-afa4-4d50-9c7f-873b449a5076" />


Real-Time Collaborative Kanban Board

🚀 Project Overview

This project is a single-file, serverless implementation of a Real-Time Collaborative Kanban Board, designed to showcase proficiency in modern front-end development, reactive state management, and cloud-native persistent storage using Google Firebase Firestore.

It simulates a live project management environment where multiple users can view, create, edit, and move tasks simultaneously, demonstrating critical skills in building responsive, multi-user applications.

✨ Key Technical Features

This application highlights several high-value skills sought by recruiters:

Real-Time Data Synchronization (Firestore): Utilizes onSnapshot listeners to instantly reflect data changes across all active user sessions, ensuring a seamless collaborative experience.

Decoupled State Management: All application state (tasks, column status, task details) is managed by Firebase Firestore, minimizing client-side state logic.

User Authentication & Security Model: Employs Firebase Authentication (signInWithCustomToken / signInAnonymously) to establish a unique userId for data tracking and to enforce task ownership logic (e.g., only the creator can attempt to delete a task).

Advanced UX/Interaction: Implements native Drag-and-Drop (DnD) functionality to update task status in the database with smooth, immediate feedback.

Complex Data Modeling: Tasks feature multiple fields including status, priority (High/Medium/Low with visual cues), title, description, and audit fields (userId, createdAt).

Reusable UI Modals: Uses a single modal component for both creating new tasks and editing existing task details (title, description, priority).

Data Visualization & Analytics: Integrates Chart.js to display dynamic Task Priority Distribution (Pie Chart), demonstrating the ability to turn raw data into actionable insights.

🛠️ Technology Stack

Category

Technology

Purpose

Frontend

HTML5, JavaScript (ESM)

Core structure and logic.

Styling

Tailwind CSS

Utility-first framework for responsive, modern UI.

Database

Google Firebase Firestore

Real-time, NoSQL cloud database for persistent storage.

Authentication

Firebase Auth

Securely establishes a unique user session (userId).

Visualization

Chart.js

Rendering dynamic task analytics.

☁️ Data & Firestore Structure

The application connects to a Public Collection within Firestore, allowing for global collaboration:

Collection Path: /artifacts/{appId}/public/data/kanbanTasks

Data Model (task document):

title (string)

description (string)

status (string: todo, in_progress, done) - Updated via Drag-and-Drop

priority (string: low, medium, high) - Updated via Edit Modal

userId (string) - Creator's ID, used for permission checks.

deleted (boolean, Soft Delete) - Ensures data integrity and quick reversibility.

💡 How to Run and Test

Open the File: This is a single, self-contained HTML file. Open kanban_board_collaborative.html in any modern web browser.

Collaborate: Open the same URL in a second browser window or a different device.

Real-Time Test: Create a task in one window and observe it appear instantly in the other. Drag a task from 'To Do' to 'In Progress' and see the chart and the other window update immediately.

Edit/View: Click any task card to open the editing modal.

(Note: The userId is displayed in the top right. You can observe the permission changes when you click on a task you created versus one created by the "other" user.)
