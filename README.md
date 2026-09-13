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

## 💡 React Concepts

A few questions about the ideas behind this project, answered in my own words.

### 1. What is JSX, and why is it used in React?

JSX stands for JavaScript XML. It allows us to write HTML-like syntax inside JavaScript or TypeScript. React uses JSX to describe what the UI should look like. It makes components easier to read and understand because the UI structure and logic can be written together.

### 2. What is the difference between props and state?

Props are used to pass data from a parent component to a child component. Props are read-only and should not be changed by the child.

State is data that belongs to a component and can change over time. When state changes, React re-renders the component and updates the UI.

In this project, I use props to pass technologies and state-related functions between components, while `selectedTechnologies` is stored as state.

### 3. What does the `useState` hook do, and where did you use it in this project?

The `useState` hook allows a functional component to store and update data that can change over time.

I used `useState` in `TechnologySection.tsx` to store the selected technologies. When a technology is added or removed, the state is updated and React re-renders the UI.

For example:

const [selectedTechnologies, setSelectedTechnologies] =
  useState<ITechnology[]>([]);

Here, `selectedTechnologies` stores the currently selected technologies, while `setSelectedTechnologies` is used to update the state.

**4. What does the `useEffect` hook do, and why did you need it to load the JSON data?**
The useEffect hook is used to perform side effects in a React component, such as fetching data from an API, updating the document title, or interacting with external systems.

For example, useEffect can be used to fetch JSON data when a component loads.

In this project, I did not use useEffect for loading the JSON data. Instead, I used React's use() hook together with Suspense to read the promise returned by the fetch function.
**5. Why does every item in a `.map()` list need a unique `key` prop?**
React uses the key prop to identify individual items in a list. It helps React determine which items were added, removed, or changed when the list is updated.

In this project, I use the technology ID as the key:

{technologies.map((technology) => (
  <TechnologyCard
    key={technology.id}
    technology={technology}
  />
))}

The ID is unique for each technology, so it is a suitable key.
**6. What is conditional rendering? Show one place you used it.**
Conditional rendering means displaying different UI depending on a condition.

I used conditional rendering in the YourStack component. When no technologies are selected, an empty-state message is displayed. Otherwise, the selected technologies are shown.

For example:

{count === 0 ? (
  <div>
    Your stack is empty.
  </div>
) : (
  <div>
    {technologies.map((tech) => (
      // selected technologies
    ))}
  </div>
)}
**7. How do you pass data from a parent component to a child component, and how does a child send something back to the parent?**
A parent component can pass data to a child component using props.

A child component can communicate back to the parent by receiving a function through props and calling that function.

In this project, TechnologySection stores the selectedTechnologies state and passes it to TechnologyCard and YourStack.

It also passes setSelectedTechnologies to the child components. When a technology is added or removed, the child calls this function to update the parent's state.
