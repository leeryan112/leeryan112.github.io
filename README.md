[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/UWYuTm85)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=20773481&assignment_repo_type=AssignmentRepo)

# 🧠 Neuro Research Finder

## 🚀 Overview
This project implements an interactive **AJAX-based frontend** for the Neurosynth-like API hosted at  
[`https://mil.psy.ntu.edu.tw:5000`](https://mil.psy.ntu.edu.tw:5000).

The web interface allows users to browse brain-related terms, find co-occurring concepts, and query related studies.  
Built with **HTML, JavaScript, and Tailwind CSS**, it dynamically communicates with the backend using asynchronous `fetch()` requests, requiring no page reloads.

---

## 🧩 API Endpoints

| Endpoint | Description | Example |
|-----------|-------------|----------|
| `/terms` | Retrieve all available terms | [https://mil.psy.ntu.edu.tw:5000/terms](https://mil.psy.ntu.edu.tw:5000/terms) |
| `/terms/<term>` | Retrieve terms associated with a given term | [https://mil.psy.ntu.edu.tw:5000/terms/amygdala](https://mil.psy.ntu.edu.tw:5000/terms/amygdala) |
| `/query/<query_string>/studies` | Logical search for studies by query string | [https://mil.psy.ntu.edu.tw:5000/query/amygdala%20not%20emotion/studies](https://mil.psy.ntu.edu.tw:5000/query/amygdala%20not%20emotion/studies) |

---

## 🧠 Features

- **Three search modes**
  - Display all available terms
  - Find related terms for a specific keyword
  - Search studies using logical expressions (e.g., `amygdala not emotion`)
- **Asynchronous AJAX search**
  - Automatically sends requests while typing (no need to press Enter)
  - Debounced and abort-safe (cancels previous requests)
- **Dynamic rendering**
  - `/terms` → keyword tag wall  
  - `/terms/<term>` → table of related terms (`相關詞 / 出現次數 / 關聯程度`)  
  - `/query/<query>/studies` → table of studies (`序號 / Study ID / 作者 / 標題 / 年份`)
- **Built-in sanity checks**
  - Prevents empty or repetitive queries
  - Skips too-short input
  - Validates keyword format
  - Gracefully handles server or network errors

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, JavaScript (ES6), Tailwind CSS  
- **AJAX:** Native `fetch()` API + `AbortController`  
- **Deployment:** GitHub Pages  
- **Backend:** [Neurosynth API (Tren’s Server)](https://mil.psy.ntu.edu.tw:5000)

---

