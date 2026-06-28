# 📚 Full-Stack Development Vault

## ⚡ React + Vite Master Setup Workflow
> **⚠️ PREREQUISITE:** [Node.js](https://nodejs.org/) must be installed. Verify with `node -v`.

### Option 1: Interactive Menu (Global)
1. `npm create vite@latest`
2. Follow the prompts (Select React + TypeScript).
3. `cd <project-name>` && `npm install`

### Option 2: Direct Scaffold (Folder-Specific)
1. `npm create vite@latest YourProjectName -- --template react-ts`
2. `cd YourProjectName` && `npm install`

### 📦 Essential Add-ons
* **Component Generator (Global):** `npm install --global react-cli-snippets`
* **React Router (Local):** `npm install react-router-dom -D` 
* **React Router Types (Local):** `npm install @types/react-router-dom -D`
* **NorthWind Server (Global):** `npm install --global northwind-rest-api` (Run with: `northwind`)


---

## ⚠️ Troubleshooting "Gotchas"

* **The "Zombie Cache" Trap:** If GitHub shows files from other folders, your local cache is dirty. 
  * *Fix:* `git push origin --delete gh-pages` -> `rm -rf node_modules/.cache/gh-pages` -> `npm run deploy`.
* **Wrong Terminal Location:** Never `git add` or create a Vite app while inside an app subfolder. Always run Git/Scaffold commands from the **root** to keep the project structure flat.
* **The `.gitignore` Catch-22:** Git will block the deploy if it sees a `.gitignore`. Always rename it during the `npm run deploy` step, then rename it back immediately.

[[Deploying subfolders inside GH-Pages]]
[[GITHUB essential Commands!!]]
