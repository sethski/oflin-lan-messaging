# oflin – LAN Messaging App

A simple offline-first LAN chat app built with Electron and React. It lets people on the same local network host or join a server and exchange messages in real time, without any external internet or cloud services.

## For beginners (Windows)

You just need to download and run the installer.

1. Go to the project page:
	- https://github.com/sethski/oflin-lan-messaging
2. On that page, click **Releases** (on the right or near the bottom).
3. Under the latest release, download the file named something like:
	- `oflin Setup 1.0.0.exe`
4. After it finishes downloading, double‑click the `.exe` file.
5. If Windows shows a SmartScreen warning, click **More info → Run anyway**.
6. When the installer is done, start the app by either:
	- Double‑clicking the **oflin** shortcut on your Desktop, or
	- Opening the Start menu and searching for **oflin**.

You do **not** need to install Node.js, npm, or any developer tools to use the app this way.

---

## For developers (run from source)

### 1. Requirements
- Node.js 18+ and npm
- Git

### 2. Clone the repo
```bash
git clone https://github.com/sethski/oflin-lan-messaging.git
cd oflin-lan-messaging
```

### 3. Install dependencies
```bash
npm install
```

### 4. Run in development
```bash
npm run dev
```
This starts Vite and Electron together:
- Vite dev server on `http://localhost:5180`
- Electron window pointing at that URL

### 5. Build Windows installer
```bash
npm run build:electron
```
This creates the installer at:
- `dist-electron/oflin Setup 1.0.0.exe`

You can upload that `.exe` to the GitHub **Releases** page so non‑technical users can download and install oflin easily.

---

## Project structure (simplified)
- `App.jsx` – top‑level React app
- `LandingPage.jsx` – host/join screen
- `Dashboard.jsx` – main chat layout
- `Sidebar.jsx`, `ChatFeed.jsx`, `MessageInput.jsx` – chat UI components
- `useChatStore.js` – Zustand store for chat state
- `socket.js` – Socket.IO client singleton
- `main.js` – Electron main process (window, IPC, server control)
- `preload.js` – safe bridge between Electron and React
- `server.js` – Socket.IO server for LAN messaging

---

## License

Add a `LICENSE` file here when you pick a license (MIT is a common choice).