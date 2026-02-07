# 📝 Flask Note Taking Application (Bug Fix & Refactor)

A simple Flask-based note-taking web application that was **initially broken** and later **refactored and fixed** as part of a hands-on debugging task.

This project focuses on identifying bugs, understanding Flask fundamentals, and refactoring code to make the application fully functional.

---

## 🎯 Project Purpose

The goal of this task was to:

- Analyze a **non-working Flask application**
- Identify and document all bugs
- Refactor the code using Flask best practices
- Ensure the application works as expected
- Document the debugging approach clearly

This task was assigned during my learning journey at **Innomatics Research Labs**.

---

## 📌 Application Functionality

- Single **Home Route (`/`)**
- User can:
  - Enter a note using a text field
  - Click **Add Note**
- All notes are displayed as an **unordered list on the same page**
- Notes persist during runtime

---

## 🐞 Bugs Identified & Fixed

### 🔴 Bug 1: Route Accepted Only POST Requests
- **Issue:** Home page did not load on browser
- **Reason:** Browser sends a GET request, but route accepted only POST
- **Fix:** Added support for both GET and POST methods

---

### 🔴 Bug 2: Incorrect Request Object Used
- **Issue:** Notes were not captured from the form
- **Reason:** `request.args` was used instead of `request.form`
- **Fix:** Used `request.form.get()` for POST data

---

### 🔴 Bug 3: Missing Form Method in HTML
- **Issue:** Form submitted data using GET by default
- **Fix:** Explicitly added `method="POST"` in the form tag

---

### 🔴 Bug 4: Empty Notes Were Being Added
- **Issue:** Empty or null notes were stored
- **Fix:** Added validation to ensure only valid notes are saved

---

### 🔴 Bug 5: Notes Not Passed During Initial Page Load
- **Issue:** Template expected `notes` variable even on GET request
- **Fix:** Always passed the notes list to the template

---

## 🛠️ Refactored Code Overview

### `app.py`
- Supports both GET and POST methods
- Handles form submission safely
- Uses clean and readable logic
- Prevents invalid data insertion

### `home.html`
- Correct form submission method
- Displays notes dynamically
- Simple and user-friendly UI

---

## 📂 Project Structure
- Code for correction: Refer `note_taking_app.zip`
- Corrected code: Refer `home.html` and `app.py`
