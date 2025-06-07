# 🧠 MindTrack – Learn, Reflect, Remember  
## Product Requirements Document (PRD)  
### Version: 1.0  
**Author:** Aryan Shrivastava
**Date:** June 8th, 2025  

---

## 🎯 Overview

MindTrack is a personal growth and learning tool that helps users build better habits through structured daily tasks, reflection, and spaced repetition revision tracking. It combines todo lists, journaling, and smart revision scheduling to help users remember what they’ve learned and improve long-term retention.

The goal of this product is to create a **personalized learning engine** that not only tracks what you plan to learn but also ensures you retain it over time using science-backed methods.

---

## 🧩 Problem Statement

Many learners forget most of what they study within days. Even when they write down todos or reflect at the end of the day, there’s no system to ensure long-term memory retention. There’s a gap between planning to learn and actually retaining knowledge.

MindTrack solves this by:
- Letting users track daily plans
- Encouraging end-of-day reflection
- Automatically scheduling revisions based on spaced repetition
- Providing reminders to review important items

---

## 🎯 Target Audience

- **Students**: Wanting to retain academic content long-term
- **Self-learners**: Learning new skills like coding, languages, or music
- **Professionals**: Looking to document and internalize work-related knowledge
- **Journalers / Reflective thinkers**: Who want to grow from their experiences

---

## 💡 Core Vision

A todo list that remembers what you’ve learned — and makes sure you never forget.

---

## 🔍 Key Features

| Feature | Description |
|--------|-------------|
| **Add Todo** | A form where users can enter what they plan to do/learn today |
| **End-of-Day Review** | A screen where users describe what they actually did/learned |
| **Auto Schedule Revisions** | Based on the date of the entry, schedule two revisions (default: +4d, +10d) |
| **User-Controlled Revision Spacing** *(Future)* | Allow users to choose custom intervals for revision |
| **Revision List** | Show all items due today at the top of the todo list |
| **Mark as Reviewed** | Mark each item as reviewed when done |
| **View All Revisions** | See past and upcoming revision dates in a list |
| **Daily Journal Entry** | Optional space to write reflections on how things went |
| **Progress Dashboard** *(Future)* | Visual stats about completed todos vs reviewed items |
| **Calendar View** *(Future)* | Visual calendar showing scheduled revisions |
| **Tags & Categories** *(Future)* | Categorize entries by subject, mood, topic |
| **Dark Mode & Themes** *(Future)* | For comfort and style |
| **Export Journal Entries** *(Future)* | Export as PDF or Markdown |
| **Markdown Support in Journal** *(Future)* | Rich formatting |
| **Email Reminders** *(Future)* | Get a morning summary or evening reminder |
| **Mobile PWA Support** *(Future)* | Installable on phone |
| **Sync with Supabase/Firebase** *(Future)* | Save data online, sync across devices |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Vite + React TS** | Fast, modern frontend setup |
| **Zustand** | Lightweight state management |
| **TailwindCSS** | Rapid UI development |
| **React Router v6** | Navigation between pages |
| **Framer Motion** | Smooth animations |
| **React Hook Form** | Powerful form handling |
| **Day.js / Luxon** | Date calculations |
| **LocalStorage / IndexedDB** | Store data offline (initially) |
| **Optional Supabase** | Cloud storage later |
| **Optional Nodemailer / Resend** | Email reminders later |
| **Optional OpenAI API** | AI insights into journal entries |

---

## 📦 MVP Scope (Minimum Viable Product)

The first version will focus on core functionality that validates the idea and user behavior:

### ✅ Must-Have MVP Features

| Feature | Description |
|--------|-------------|
| **Add Todo Form** | Input fields for title, planned activity |
| **End-of-Day Review Form** | Input field for what was actually done |
| **Schedule Revisions** | Two auto-generated revision dates (+4d and +10d) |
| **Show Revision Items** | Display items due today at the top |
| **Mark as Reviewed** | Toggle button or action to mark as reviewed |
| **Basic UI** | Clean layout using TailwindCSS |
| **Local Storage** | Save all data in browser for now |

### ❌ Out of MVP Scope (For Later)

- Syncing with backend
- Calendar view
- Tags/categories
- Dark mode
- Email notifications
- Export features
- AI insights

---

## 📁 Folder Structure (Suggested)
src/
├── components/
│ ├── TodoForm.tsx
│ ├── EndOfDayReviewForm.tsx
│ ├── RevisionList.tsx
│ ├── RevisionCard.tsx
│ └── Layout.tsx
├── store/
│ └── useStore.ts
├── pages/
│ ├── Home.tsx
│ ├── AddTodo.tsx
│ ├── ReviewToday.tsx
│ └── Revisions.tsx
├── App.tsx
└── main.tsx

---

## 🗃️ Data Model (TypeScript Interfaces)

```ts
interface TodoItem {
  id: string;
  title: string; // Title of the task
  planned: string; // What was planned to be done
  actual?: string; // What was actually done
  date: string; // ISO date string when added
  revisions: {
    first: string; // ISO date string
    second: string; // ISO date string
  };
  status: 'pending' | 'reviewed'; // Whether reviewed or not
}

```
---

## 🧭 Development Roadmap

### 📆 Phase 1: MVP (Month 1)
- Build Zustand store logic  
- Create basic forms: Todo, End-of-day review  
- Implement revision scheduling logic  
- Show revision list  
- Basic UI styling  

### 📆 Phase 2: UX & Extra Features (Month 2)
- Add calendar view  
- Add tagging  
- Improve UI (dark mode, animations)  
- Add stats dashboard  
- Allow custom revision spacing  

### 📆 Phase 3: Advanced Features (Month 3)
- Add markdown journal support  
- Add AI analysis of journal entries  
- Add email reminders  
- Sync with Supabase or Firebase  
- Make it installable as PWA  
