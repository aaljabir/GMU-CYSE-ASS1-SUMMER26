# Assignment 1 (CYSE 411): Secure Status Portal

## Learning Goals
You will practice JavaScript fundamentals and browser web programming concepts:
- Functions, variables, conditionals, and basic data structures
- DOM selection and safe DOM updates
- Event-driven programming (addEventListener)
- JSON parsing and validation
- Async execution: Promises + async/await
- Basic `fetch()` usage
- Browser-side state: localStorage, sessionStorage, cookie concepts

You will also apply a key security lesson:
> The browser is not trusted. Frontend logic can be modified by the user.

---

## Operation Glass Wall

### 🏢 The Setting

You are a junior Cyber Security Engineer at OmniCorp, a massive tech conglomerate. OmniCorp just launched their brand new Internal Status Portal, a dashboard where high-ranking executives and system administrators view system alerts, update their security profiles, and access restricted server rooms.

The senior developers built it quickly using pure JavaScript. They think it’s secure because "the code is hidden in the browser." Your Job: You’ve been tasked to audit and fix the prototype (src/app.js) before a notorious hacktivist group known as "The Null Pointer" exploits it. You know the golden rule of application security: Never trust the frontend.

### 🖥️ Act-by-Act Mission Briefing

As you solve each TODO in src/app.js, you aren't just writing code—you are actively stopping an attack vector.

### Act I: The Gateway (The Inputs)

#### 🚀 Mission 1: sanitizeUsername(input)

> ⚠️ **The Threat:** > Hackers are trying to inject malicious scripts into their usernames to hijack the sessions of HR managers.

- Objective: Neutralize incoming string data to prevent Cross-Site Scripting (XSS).

- Constraint: Implement sanitization using REGEX (https://www.w3schools.com/JS/js_regexp.asp).


#### 🚀 Mission 2: renderNotifications(listEl, notifications)

> ⚠️ **The Threat** > A clever attacker managed to slip a Cross-Site Scripting (XSS) payload into a system notification. If you use innerHTML, the moment an executive opens their dashboard, the hacker steals their admin cookie.

- Your Goal: Defuse the XSS bomb. Use safe DOM updates to render the notifications like an armored glass window—visible, but impenetrable.

### 🖥️ Act II: The Data Vault (The Parser & Fetcher)

#### 🚀 Mission 3: parseProfileJson(jsonText)

> ⚠️ **The Threat** > Attackers are sending malformed, corrupted, or "JSON-bomb" profiles to crash the portal, causing a Denial of Service (DoS) on the client side.

- Your Goal: Build a secure airlock. Implement robust try/catch validation that inspects the JSON payload safely without swallowing critical system exceptions blindly.


#### 🚀 Mission 4: fetchUserProfile(url)


> ⚠️ **The Threat** > The portal needs to fetch profile data from an internal API. If the connection fails or gets intercepted (Man-in-the-Middle), the application might break or leak information.

- Your Goal: Establish a secure, asynchronous data pipeline using Promises and async/await to handle data streams cleanly.

