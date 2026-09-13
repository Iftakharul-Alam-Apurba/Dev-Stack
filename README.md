# 🧱 Dev Stack Builder

Build your ideal development stack — explore frontend, backend, database, and tooling technologies side by side, then add the ones you want to your own personal "Your Stack" collection.

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-B73BFE?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38BDF8?logo=tailwindcss&logoColor=white)
![DaisyUI](https://img.shields.io/badge/DaisyUI-5A0EF8?logo=daisyui&logoColor=white)

## 📖 About the Project

**Dev Stack Builder** is a single-page React app for browsing a curated catalog of development technologies — frontend libraries, backend runtimes, databases, styling tools, and more. Each card shows its category, difficulty level, rating, and a short description, all loaded live from a local JSON dataset. Pick the technologies that fit your next project and build out a personalized stack, with instant feedback at every step.

## 🛠️ Built With

| Layer | Technology |
|---|---|
| Framework | React 19 + TypeScript |
| Build tool | Vite |
| Styling | Tailwind CSS v4 + DaisyUI |
| Notifications | React-Toastify |
| Data | Local JSON |

## ✨ Features

- **🗂️ JSON-driven technology catalog** — every technology (name, category, description, icon, rating, difficulty, badge) is loaded from a local JSON file at runtime instead of being hardcoded, so growing the catalog never means touching component code.
- **➕ Interactive Stack Builder** — add any technology to "Your Stack" with a click, watch the selected count update live, remove items one at a time or clear the whole stack, and get a toast notification for every action.
- **📱 Fully responsive, on-brand design** — a sticky navbar with its own mobile layout, a responsive 1/2/3-column technology grid, and a single shared orange → pink → violet gradient reused across the brand, hero heading, and primary buttons.

## 🚀 Getting Started

```bash
# install dependencies
npm install

# start the dev server
npm run dev

# build for production
npm run build
```

## 📸 Screenshots

_Add a few screenshots here — the homepage, the technology grid, and "Your Stack" with items selected all work well._

## 💡 React Concepts

A few questions about the ideas behind this project, answered in my own words.

**1. What is JSX, and why is it used in React?**
> _Write your answer here._

**2. What is the difference between props and state?**
> _Write your answer here._

**3. What does the `useState` hook do, and where did you use it in this project?**
> _Write your answer here._

**4. What does the `useEffect` hook do, and why did you need it to load the JSON data?**
> _Write your answer here. (Note: this project currently loads data with `use()` + Suspense rather than `useEffect` — see the chat for how to reconcile that before answering.)_

**5. Why does every item in a `.map()` list need a unique `key` prop?**
> _Write your answer here._

**6. What is conditional rendering? Show one place you used it.**
> _Write your answer here._

**7. How do you pass data from a parent component to a child component, and how does a child send something back to the parent?**
> _Write your answer here._
