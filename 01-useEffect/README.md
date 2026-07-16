# 🧠 Concept 01: `useEffect` and "Side Effects"


💡 Follow my live updates and daily technical discussions on my [LinkedIn Post]
https://www.linkedin.com/posts/aniketh-r_reactjs-webdevelopment-frontend-ugcPost-7483444739208273920-pOVZ/?utm_source=share&utm_medium=member_desktop&rcm=ACoAADCqL3oB0wklBumIujuqb8_ayfphsDmfU7g

A breakdown of how React interacts with the outside world, written during my early days of mastering hooks.

## 🤔 What on earth is a "Side Effect"?
In React, a component's primary job is to take data and render UI onto the screen. It calculates the JSX. 

A **Side Effect** is *anything* that happens outside of that predictable rendering process. It’s when your component needs to reach out and interact with the "outside world."

Common examples:
* Fetching data from an API 🌐
* Setting up a timer or interval ⏳
* Manually changing the browser's DOM title 📄

## ⚙️ Enter `useEffect`: The Manager
`useEffect` tells React: *"Render the UI first so the user sees the page instantly. Once that is done, go ahead and handle the side effect in the background."*

## 💡 The 3 Modes of `useEffect`

1️⃣ **No Array at all:** Runs on *every single render*.
```javascript
useEffect(() => {
  console.log("I run every time the page updates!");
});

2️⃣ Empty Array []: Runs only once when the component first loads. Perfect for initial data fetching.

JavaScript
useEffect(() => {
  console.log("I run only ONCE when the component loads.");
}, []); 
3️⃣ Array with variables [count]: Runs once when the component loads, and then runs again only if the specific variable changes.

JavaScript
useEffect(() => {
  console.log("I run whenever 'count' changes!");
}, [count]);



