# Class Exit Poll

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/Platform-GitHub%20Pages-000000?style=for-the-badge&logo=github" alt="GitHub Pages">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-classroom%20ready-brightgreen?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/focus-pupil%20engagement-blueviolet?style=flat-square" alt="Focus">
  <img src="https://img.shields.io/badge/device-Chromebook%20%7C%20Laptop-lightgrey?style=flat-square" alt="Devices">
</p>

---

A simple, **kid-friendly exit poll web app** for measuring lesson engagement at the end of a class.

Designed to run in a browser (Chromebooks, teacher laptops, etc.), with a **clean full-screen interface** and **four large colour-coded circles** pupils can tap as they leave the room.

---

## 👀 Quick preview

> Teacher view – setup  

```text
+----------------------------------------------+
| Class Exit Poll                              |
|                                              |
| Class / Group: [ 7X/CS1               ]      |
| Send results to: [ teacher@school.co.uk ]    |
|                                              |
|                  [ Start poll ]              |
+----------------------------------------------+
```

> Pupil view – low-distraction poll  

<p align="center">
  <img alt="Four coloured poll circles" src="https://img.shields.io/badge/All-22c55e?style=for-the-badge">
  <img alt="Most circle" src="https://img.shields.io/badge/Most-eab308?style=for-the-badge">
  <img alt="Some circle" src="https://img.shields.io/badge/Some-f97316?style=for-the-badge">
  <img alt="None circle" src="https://img.shields.io/badge/None-ef4444?style=for-the-badge">
</p>

Each tap shows a **“Thank you! 🌟”** bubble for one second, then the circles reappear for the next pupil.

---

## ✨ Features

- **Four big choices (traffic-light style):**
  - 🟢 **All** – I finished everything  
  - 🟡 **Most** – Nearly all done  
  - 🟠 **Some** – I did a bit  
  - 🔴 **None** – I didn’t start  

- **Teacher setup screen**
  - Enter **class / group name**  
  - Enter **email address** to receive results  
  - Email address is remembered on that device for next time (`localStorage`)

- **Pupil poll screen**
  - Only the four circles + a small **“Teacher: End poll”** button  
  - Single tap → response stored → **“Thank you! 🌟”** overlay for 1 second  
  - Big, touch-friendly layout designed for Chromebooks / tablets

- **Teacher summary screen**
  - Shows **class name** and **total responses**
  - Calculates an **engagement score**
  - Lists **counts and percentages** for each option
  - **Email results** button:
    - Opens a Gmail compose window
    - To: the email address entered on the setup screen
    - Subject: `Exit poll results – <Class>`
    - Body: a readable plain-text summary

- **Local storage**
  - All responses are saved to the browser’s `localStorage` on that device
  - Multiple classes can be recorded over time on the same machine

---

## 🧮 Engagement score

The engagement score is a simple weighted average:

| Choice | Weight |
|--------|--------|
| All    | 1.0    |
| Most   | 0.75   |
| Some   | 0.5    |
| None   | 0      |

For each lesson:

1. Convert each response into its weight  
2. Take the average  
3. Multiply by 100 → **overall engagement %**

Example:

> 10 × All, 8 × Most, 4 × Some, 3 × None  
> Overall engagement might be: **78.3%**

---

## 🧑‍🏫 Teacher workflow

1. Open the app in **Chrome** (or any modern browser).
2. On the **setup screen**:
   - Type the **Class / Group name** – e.g. `7X/CS1`
   - Type the **email address** you want results sent to.
3. Click **Start poll**.
4. As pupils leave:
   - Hand them the device or place it by the door.
   - Each pupil taps one circle that best matches how much work they completed.
   - A **“Thank you! 🌟”** bubble appears for 1 second, then the buttons reappear.
5. When the class is finished, tap **Teacher: End poll**.
6. On the **summary screen**, click **Email results**:
   - A Gmail compose window opens with:
     - To: the email you entered
     - Subject: `Exit poll results – <Class>`
     - Body: total responses, engagement %, and a breakdown.
7. Click **New class / poll** to reset for the next lesson.

---

## 🛠 Tech stack

- **HTML5** – single-page app
- **CSS3** – responsive layout, child-friendly style
- **Vanilla JavaScript** – state handling, `localStorage`, summary & email integration
- **Git & GitHub** – version control
- **GitHub Pages** – free hosting (static deployment)

No frameworks, build tools, or backend required.

---

## 🚀 Running locally

1. Clone the repository:

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

2. Open `index.html` in a browser:
   - Double-click the file  
   - or use **Live Server** in VS Code (optional)

---

## 🌍 Deployment (GitHub Pages)

1. Go to **Settings → Pages** in your GitHub repo  
2. Under **Source**:
   - **Deploy from a branch**
   - Branch: `main`
   - Folder: `/ (root)`
3. Save  
4. GitHub will provide a public URL such as:

```
https://<your-username>.github.io/<your-repo-name>/
```

---

## 🔮 Future improvements

- 🔐 Login + cloud storage (Firebase or Supabase)  
- 📊 Per-class charts and historical tracking  
- 📥 CSV exports  
- 📱 PWA and mobile app wrappers  
- 🎨 Custom themes for different age groups  
