# Connect Maison Vell Project to VS Code via GitHub

A step-by-step guide to exporting your project from Google AI Studio to GitHub, cloning the repository into Visual Studio Code, and running the local development environment.

### User Review & Critical Decisions

> [!IMPORTANT]
> You confirmed that your GitHub account is already connected and authenticated within VS Code. This makes cloning and working with the repository straightforward.

- **Confirmed Decision**: Export codebase to a GitHub repository and clone into VS Code.
- **Environment Strategy**: Use Node.js (v20+ recommended) and `npm` locally to install dependencies and run Vite on `localhost:3000`.

---

### 1. Overview & Core Concept

- **What It Does**: Establishes a synchronized local development workflow between your Google AI Studio project and your local VS Code workspace through a GitHub remote repository.
- **Target Audience**: Developers who prefer editing code, running debuggers, and managing version control inside the desktop VS Code editor.
- **Key Value**: Full access to your local extensions, linting, keyboard shortcuts, and offline editing while maintaining synchronization with GitHub.

---

### 2. Step-by-Step Workflow Walkthrough

```
┌─────────────────────────┐       ┌────────────────────────┐       ┌─────────────────────────┐
│   Google AI Studio      │       │     GitHub Remote      │       │      Local VS Code      │
│  (Maison Vell Project)  ├──────►│ (github.com/user/repo) ├──────►│   (Desktop Editor)      │
│                         │ Push  │                        │ Clone │                         │
└─────────────────────────┘       └────────────────────────┘       └────────────┬────────────┘
                                                                                │
                                                                       npm install && npm run dev
                                                                                │
                                                                                ▼
                                                                     http://localhost:3000
```

#### Step 1: Export Project to GitHub from AI Studio
1. In the upper-right toolbar of Google AI Studio, locate the **Export** or **GitHub** button (or project settings menu).
2. Click **Export to GitHub** (or **Create GitHub Repository**).
3. Select your GitHub account/organization, specify a repository name (e.g. `maison-vell-lookbook`), choose public or private visibility, and confirm the export.
4. Copy the repository URL (e.g., `https://github.com/your-username/maison-vell-lookbook.git`).

#### Step 2: Clone the Repository in VS Code
1. Open **Visual Studio Code** on your computer.
2. Open the Command Palette using `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS).
3. Type and select `Git: Clone`.
4. Paste your GitHub repository URL and press **Enter**.
5. Select a local directory on your drive where you want to store the project folder.
6. When prompted by VS Code, click **Open** (or **Open in New Window**).

#### Step 3: Configure Local Dependencies & Environment
1. In VS Code, open the integrated terminal (`Ctrl+` `~` or via menu `Terminal` > `New Terminal`).
2. Verify you have Node.js installed by running:
   ```bash
   node -v
   npm -v
   ```
3. Install the project dependencies:
   ```bash
   npm install
   ```
4. Prepare your environment file if using API endpoints:
   ```bash
   cp .env.example .env
   ```

#### Step 4: Run the Development Server
1. Start the Vite local dev server:
   ```bash
   npm run dev
   ```
2. Click the link in your terminal or open your browser to `http://localhost:3000`.
3. You should see the exact runway depth lookbook running locally with full hot reload.

#### Step 5: Committing & Pushing Changes
- Whenever you make changes in VS Code, use the Source Control tab (`Ctrl+Shift+G` / `Cmd+Shift+G`) to stage changes, enter a commit message, and click **Commit & Push**.

---

### 3. Key Product Decisions & Trade-Offs

- **Approach: GitHub as the Remote Bridge**:
  - *Chosen Approach*: Export via GitHub rather than raw zip downloads.
  - *Why*: Allows version history tracking, continuous synchronization, and standard pull/push workflow directly integrated into VS Code's Source Control panel.
- **Alternative Considered**: Direct zip download.
  - *Why Passed Over*: Zip downloads do not preserve git commit history and require manual re-downloading whenever modifications are made in the cloud.

---

### 4. Technical Architecture & Local Verification

- **Workspace Structure**:
  - `index.html`: Entry point containing the complete Maison Vell lookbook markup, responsive CSS, and canvas math loop.
  - `package.json`: Vite configuration and build scripts (`npm run dev`, `npm run build`, `npm run lint`).
  - `vite.config.ts`: Vite bundling and dev server port bindings.
- **Local Verification Checklist**:
  1. `npm install` succeeds without dependency conflicts.
  2. `npm run build` generates production bundle in `dist/`.
  3. `npm run dev` spins up local server at `http://localhost:3000` with responsive models, drag physics, soundless wheel scrubbing, and product rail sync.
