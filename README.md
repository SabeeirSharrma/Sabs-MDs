<![CDATA[# Sab's MDs

A sleek, client-side Markdown dashboard for writing, previewing, and sharing Markdown documents — all from a single static HTML file.

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)

---

## ✨ Features

- **Live Preview** — See your rendered Markdown in real-time as you type.
- **Publish & Persist** — Posts are saved to `localStorage`, so they survive page reloads.
- **Token Lock** — Optionally protect any post behind a secret token. Readers must enter the token before the content is revealed.
- **Shareable Links** — Generate a self-contained share URL that encodes the entire post (title, body, date, and token) into the URL hash. No server required.
- **Dark Glassmorphism UI** — A premium dark theme with glass cards, gradient accents, and micro-animations.
- **Zero Dependencies (server-side)** — Everything runs in the browser. No build step, no backend.

## 🛠 Tech Stack

| Layer     | Technology                                                                 |
| --------- | -------------------------------------------------------------------------- |
| Structure | HTML5                                                                      |
| Styling   | [Tailwind CSS](https://tailwindcss.com/) (CDN) + custom CSS               |
| Logic     | Vanilla JavaScript                                                         |
| Markdown  | [marked.js](https://marked.js.org/)                                        |
| Sanitizer | [DOMPurify](https://github.com/cure53/DOMPurify)                           |
| Fonts     | [Inter](https://fonts.google.com/specimen/Inter) & [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) |

## 🚀 Getting Started

No installation needed. Just open the file:

```bash
# Clone the repo
git clone https://github.com/SabeeirSharrma/Sabs-MDs.git
cd Sabs-MDs

# Open in your browser
start index.html        # Windows
open index.html         # macOS
xdg-open index.html     # Linux
```

Or serve it with any static server:

```bash
npx -y serve .
```

## 📖 Usage

### Writing a Post

1. Enter a **title** in the title field.
2. Paste or type your **Markdown** in the editor — the preview updates live.
3. *(Optional)* Toggle **Lock behind token** and set a secret token.
4. Click **Publish**.

### Sharing a Post

- Click the **share icon** on any post card, or the **Share** button inside the post viewer.
- A self-contained URL is copied to your clipboard.
- Anyone with the link can view the post — no account or server needed.
- If the post is token-locked, the recipient will be prompted to enter the token before viewing.

### Deleting a Post

- Click the **trash icon** on a post card and confirm the deletion.

## 🔒 How Token Lock Works

When you enable the token toggle and set a secret:

1. The token is stored alongside the post data in `localStorage`.
2. When opening a locked post (or following a share link to one), a modal prompts for the token.
3. The content is only rendered after the correct token is entered.

> **Note:** This is client-side obfuscation, not encryption. The token and content are stored in plain text in `localStorage` and encoded (not encrypted) in share URLs. Do not use this for sensitive or confidential data.

## 🔗 How Sharing Works

Posts are encoded into the URL hash using **Base64URL** encoding:

1. The post's title, body, date, and token are serialized to JSON.
2. The JSON is Base64URL-encoded (URL-safe characters, no padding).
3. The encoded string is appended as `#share=<payload>` in the URL.
4. On page load, the app checks for a `#share=` hash and decodes the post.

Since everything lives in the URL fragment, no data ever hits a server.

## 📁 Project Structure

```
Sabs-MDs/
├── index.html    # The entire application (HTML + CSS + JS)
└── README.md     # This file
```

## 📄 License

This project is open source. Feel free to fork and modify.
]]>
