# Ritma — Telegram Cycle Tracking Bot

**Ritma** is a production-ready Telegram bot designed for menstrual cycle tracking, analytics, and partner notifications.
The bot helps users better understand cycle phases, record events, review history, and gently involve their partner in a supportive way.

👉 **Live bot:** [https://t.me/RitmaOn_bot](https://t.me/RitmaOn_bot)

---

## ✨ Key Features

- **Menstrual cycle tracking and history:** Keep a precise log of your cycle.
- **Cycle analytics:** Automatic calculation of cycle length and prediction of the next period.
- **Inline Calendar UI:** Intuitive interface for browsing and adding past records.
- **Symptoms & Intimacy Logging:** Track health details and intimacy.
- **Partner Notifications:** Unique, empathetic notifications tailored to the cycle phase.
- **Privacy First:** Data is securely stored in MongoDB.
- **Production Ready:** Background scheduled checks and reliable architecture.

---

## 🧠 Thoughtful Partner Notifications

One of the core ideas behind Ritma is **empathetic communication**.
Notifications are tailored separately for the user and their partner depending on the current cycle phase.

*Example logic from the project:*

```python
# === Notification messages by cycle phase ===
PHASE_MESSAGES = {
    "menstruation": {
        "user": (
            "Menstruation has started. Slow down and take care of yourself — "
            "rest and avoid overload. (3–5 days)"
        ),
        "partner": (
            "Her period has started. Be especially gentle and supportive. "
            "Help and care matter most right now. (3–5 days)"
        )
    },
    "pre_menstrual": {
        "user": (
            "Premenstrual phase. Mood may fluctuate — be kind to yourself "
            "and try to reduce stress. (≈3 days)"
        ),
        "partner": (
            "Premenstrual phase is approaching — emotional sensitivity may increase. "
            "Avoid starting difficult conversations and offer extra support. (≈3 days)"
        )
    },
    "ovulation": {
        "user": (
            "Ovulation. Possible boost of energy, sensitivity and mood. "
            "Listen to your body. (±2 days)"
        ),
        "partner": (
            "Ovulation period. Increased sensitivity and attraction. "
            "More attention, romance and closeness can be especially meaningful. (±2 days)"
        )
    },
    "follicular": {
        "user": (
            "Follicular phase. Energy and motivation rise — a great time "
            "for planning and social activity. (≈7 days)"
        ),
        "partner": (
            "She may feel more energetic and optimistic. "
            "A good moment for shared plans and activities. (≈7 days)"
        )
    },
    "luteal": {
        "user": (
            "Luteal phase. Estrogen and stress tolerance decrease, "
            "progesterone and anxiety increase. Peaks before menstruation. (≈13 days)"
        ),
        "partner": (
            "Luteal phase. Stress tolerance may decrease and emotions fluctuate. "
            "Offer support and avoid taking mood changes personally. (≈13 days)"
        )
    }
}
```
💡 *This logic helps transform raw health data into meaningful, human-centered interaction.*

---

## 🖼 Screenshots

### Main Menu
Simple and accessible actions.
![Main Menu](screenshots/buttons.jpg)

### Interactive Calendar
Adding records using an inline calendar interface.
![Calendar UI](screenshots/data.jpg)

### Commands
List of supported commands.
![Commands](screenshots/command.jpg)

---

## 🎥 Demo Video

📺 **Video walkthrough**
*(Coming soon — YouTube link will be added here)*

---

## 🧩 Project Architecture

The project is built for reliability and ease of maintenance.

- **Language:** Python 3.11
- **Framework:** `python-telegram-bot`
- **Database:** MongoDB (Persistent storage for users, events, and notifications)
- **Scheduling:** `JobQueue` (Daily background checks for phase changes)
- **Deployment:** Systemd service / Docker support

### High-level structure
```text
bot_calendar_full.py        # Main application logic
requirements-prod.txt       # Production dependencies
.env.example                # Environment variables template
ritma_bot.service.example   # systemd service example
screenshots/                # Images for README
```

The bot runs as a long-lived background service handling:
1. **Real-time interactions:** Callbacks, text inputs, and command handling.
2. **Scheduled tasks:** Daily checks for period predictions and notifications.
3. **State management:** MongoDB for persistent user states.

---

## 🔐 Source Code Availability

**⚠️ Important Note**

This repository is a **public showcase** of a commercial project.
The full production source code is kept private to protect business logic and user data.

This repository contains:
- Documentation
- Screenshots & Demos
- Architectural Overview
- Selected Code Snippets

*Full source code reviews are available upon request for verification purposes.*

---

## 🚀 Try It Yourself

You can interact with the live bot directly in Telegram:

👉 **[Start Ritma Bot](https://t.me/RitmaOn_bot)**

---

## 📌 Status

- ✅ **Active in Production**
- 📈 **Ongoing Feature Expansion**
