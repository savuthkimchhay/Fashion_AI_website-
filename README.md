# Maison Vell — Runway Depth Lookbook

An editorial, full-viewport fashion lookbook where six looks stand in a receding perspective line into a blurred distance. Dragging, scrolling, or pressing the arrow keys moves the line forward in real time with synchronized product catalog rails and rolling counters.

---

## Getting Started in VS Code

### 1. Prerequisites
- [Node.js](https://nodejs.org/) (version 18 or higher recommended)
- [npm](https://www.npmjs.com/) (bundled with Node.js)
- [Visual Studio Code](https://code.visualstudio.com/)

### 2. Quick Setup

1. **Open the repository in VS Code**:
   ```bash
   git clone <YOUR_GITHUB_REPO_URL>
   cd maison-vell
   code .
   ```

2. **Open the Integrated Terminal in VS Code**:
   - Press `Ctrl + ~` (Windows/Linux) or `Cmd + ~` (macOS).

3. **Install dependencies**:
   ```bash
   npm install
   ```

4. **Start the local development server**:
   ```bash
   npm run dev
   ```

5. **View in browser**:
   - Open [http://localhost:3000](http://localhost:3000) (or click the terminal link).

---

## Project Structure

```
├── index.html         # Main application markup, responsive styling, and vanilla physics script
├── vite.config.ts     # Vite configuration (port 3000 dev server, Tailwind)
├── package.json       # Project dependencies and script commands
├── metadata.json      # AI Studio metadata and permissions
├── src/               # React / TypeScript support entry points
└── tsconfig.json      # TypeScript compiler configuration
```

---

## Available Scripts

- `npm run dev`: Starts the local development server on `http://localhost:3000`.
- `npm run build`: Compiles and bundles the application for production into `dist/`.
- `npm run preview`: Locally previews the production build.
- `npm run lint`: Validates TypeScript types across the codebase.

---

## Core Features & Controls

- **Drag / Swipe**: Click and drag horizontally across the stage to pull looks forward or push them back.
- **Scroll Wheel**: Smooth wheel scrubbing with automatic look snapping.
- **Keyboard Navigation**: Use `ArrowRight` / `ArrowDown` to advance to the next look, or `ArrowLeft` / `ArrowUp` to return to the previous look.
- **Click to Focus**: Click on any model standing in the line to jump directly to that look.
- **Product Rail Interaction**: Wishlist heart toggling and add-to-cart counter integration.
