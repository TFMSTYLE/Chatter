# Chatter

![chatter-thumb](https://github.com/user-attachments/assets/ed67fac0-3a8a-464f-bbb0-e252ed493c04)

**Author:** The French Monkey (TFMSTYLE)  
**Version:** 1.0.0  

---

## Overview

Chatter is a **communication and feedback system** integrated directly into Blender’s sidebar.  
It allows users to view the latest **changelog**, report **issues**, and submit **feature requests** for TFMSTYLE add-ons — all from within the Blender interface.  

Messages are synced through a lightweight Firebase backend, and changelogs are automatically fetched from the GitHub repository.  
Chatter provides a centralized hub for user feedback, updates, and community-driven development.

---

## Features

- **Changelog Feed:** Displays the latest updates pulled from GitHub.  
- **Issue Reporting:** Send anonymous bug reports tied to specific add-ons.  
- **Feature Requests:** Suggest new ideas or improvements.  
- **Text Wrapping System:** Dynamically adjusts message display width based on the Blender region size.  
- **Cached Storage:** Uses local caching for quick startup and offline reading.  
- **Live Room Switching:** Instantly toggles between logs, issues, and requests.  

---

## Parameters

### Room
Selects the active chat category.  

Available options:
- **Changelog:** Read-only feed of updates.  
- **Issues:** View and submit bug reports.  
- **Request:** View and submit feature suggestions.

---

### Message
The text field for submitting a new issue or request.  
Messages are capped at **250 characters** and support automatic line wrapping.

---

### Addon
Specifies which TFMSTYLE add-on the issue or request relates to.  
Includes all major tools such as **City Generator**, **Shell Generator**, **Spline Generator**, **Stair Generator**, and others.  
Default value is **General** when no specific add-on applies.

---

## Operators

### Send Message
Submits the typed message to the selected room (**Issues** or **Request**).  
Automatically timestamps the message and posts it anonymously to Firebase.  
Unavailable in **Changelog** mode (read-only).

---

### Refresh
Manually updates the current room’s feed.  
Fetches the latest messages or changelog data from the server and rebuilds the local display list.

---

## Internal Behavior

- Chatter automatically loads cached changelog data at startup.  
- Messages are wrapped and formatted according to the region width for optimal readability.  
- Each category (Log, Issue, Request) is stored in separate Blender collection properties.  
- Message submission and retrieval use HTTPS requests with short timeouts for responsiveness.  
- Interface updates are triggered via Blender’s redraw system for instant feedback.

---

## Usage Notes

- The **Changelog** is refreshed directly from the GitHub repository and cannot be edited.  
- Issues and requests are submitted anonymously — no user login or personal data is stored.  
- Use **Refresh** after sending a message to see it appear in the list.  
- Ideal for reporting bugs, proposing features, or staying informed about new add-on releases.  
- Integrates seamlessly into Blender’s sidebar under **View3D > Sidebar > Chatter**.
