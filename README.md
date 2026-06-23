# FocusFrame × NeuroLearn

> A gentle, explainable planning and learning suite for turning overwhelming work into manageable next steps.

Created by **Yashashwini Awate**.

## The idea

Most productivity apps are static lists, rigid streaks, or generic AI chatboxes. FocusFrame and NeuroLearn work together as a calmer, more adaptive system:

- **FocusFrame** is the planning space: brain-dump tasks, schedule them naturally, see them in a calendar, and receive gentle reminders.
- **NeuroLearn** is the study space: turn notes and learning material into small study sessions, then send those sessions directly into FocusFrame.

The product supports planning, focus, and reflection. It does **not** diagnose, treat, or provide medical advice about ADHD, anxiety, stress, or any other health condition.

## What makes it different

### Explainable next steps

FocusFrame does not simply present a list. It gives the user one realistic next action and explains why it was chosen: for example, because it is time-boxed, already scheduled, or better suited to the user’s current energy.

### Natural-language calendar capture

Miso, the in-app cat companion, accepts human wording rather than form fields. For example:

```text
Meeting at 4 pm with Het
```

is converted into a calendar task at `16:00` on the selected day. The parser currently supports clock times, `am`/`pm`, and `tomorrow`; it is designed to become an LLM-backed calendar agent later.

### Two products, one gentle loop

NeuroLearn makes study notes smaller and more actionable. FocusFrame schedules those actions. This gives users a bridge from “I need to understand this” to “I know exactly what I can do next.”

### A living, non-punitive interface

The daylight theme uses birds, trees, cloud movement, and fireflies. The nighttime theme becomes a quiet galaxy. Miso opens the calendar, while visual motion stays subtle and respects the user’s actual work rather than demanding attention.

## Current features

- Mobile-first responsive interface
- Day/nature and night/galaxy themes
- FocusFrame daily planning and weekly calendar
- Local browser storage: tasks stay on the device in this prototype
- Natural-language chat task capture through Miso
- Task completion and flexible calendar movement
- Browser notification permission and in-session reminder scheduling
- `.ics` calendar export for Google Calendar, Apple Calendar, or Outlook
- NeuroLearn note-to-study-session hand-off
- Animated environment and distinct NeuroLearn visual identity

## Reminder behaviour

Browser reminders work when the app is open and the user grants notification permission. A static GitHub Pages site cannot independently send scheduled email. Email reminders will require a small secure backend or an automation provider such as GitHub Actions plus an email service; no email address or secret should be stored in the browser bundle.

## Planned AI layer

1. **Docling** for local PDF and study-note extraction.
2. Retrieval-backed study summaries, flashcards, and source-aware explanations.
3. An LLM calendar agent that understands richer instructions such as dates, recurring events, priorities, and rescheduling requests.
4. Explainable planning recommendations with user feedback controls.
5. Optional secure email reminders through server-side environment variables.

## Run locally

```powershell
npm.cmd install
npm.cmd run dev
```

If PowerShell blocks `npm`, use `npm.cmd` as shown above.

## Build for deployment

```powershell
npm.cmd run build
```

The Vite base path is configured for static hosting, including GitHub Pages. The generated site is placed in `dist/`.

## Tech stack

- React + TypeScript + Vite
- CSS animation and responsive design
- Browser Local Storage, Notifications API, and Calendar (`.ics`) export
- Planned: Python/FastAPI, Docling, LangChain, and a secure LLM adapter

## Privacy and safety principles

- Keep user planning data local by default.
- Never put API keys, email credentials, or private documents into the public GitHub repository.
- Let users edit, reject, and delete plans.
- Describe recommendations as support, never as medical assessment.
