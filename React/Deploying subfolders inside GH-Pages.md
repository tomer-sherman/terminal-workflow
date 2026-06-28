
# 🚀 React Homework Deployment Workflow

This repository holds multiple React/Vite assignments. Since they are all stored in one master repository, follow this exact Standard Operating Procedure (SOP) to add new projects and deploy them safely to GitHub Pages.

---

## 🛠️ The Master Workflow

### Phase 1: Scaffold the App (From the Root)
Always create the new app from the very top of the mega-repo.
1. Open a terminal at the root folder.
2. `Simply create a new File, manually like a normal human.`
3. `Inside it all the necery commands too start a React project`


### Phase 2: Wire the Configurations (Inside the App Folder)
**1. Update `vite.config.ts`**
Add the `base` path pointing to the repo and the exact new folder name:
`base: '/john-bryce-fullstack-course/FolderName/',`

**2. Update `package.json`**
Add the exact deploy script:
`"predeploy": "npm run build",`
`"deploy": "gh-pages -d dist --dest FolderName"`

### Phase 3: Save Source Code to Main Repo (From the Root)
Once the app works locally, back it up to the master branch.
1. Ensure your terminal is at the **root mega-repo folder**.
2. `git add .`
3. `git commit -m "Completed FolderName assignment"`
4. `git push`

### Phase 4: Deploy the Live Link (Inside the App Folder)
Push the compiled app to the live server. 
1. `cd FolderName`
2. Rename `.gitignore` to `temp.gitignore`.
3. `npm run deploy`
4. Rename `temp.gitignore` right back to `.gitignore`.

Give GitHub about 60 seconds, and the app will be live at:
`https://tomer-sherman.github.io/john-bryce-fullstack-course/FolderName/`

---

## ⚠️ Troubleshooting & Traps to Avoid

### 1. The "Zombie Cache" (Uploading the entire mega-repo)
**The Trap:** The `gh-pages` tool has a hidden cache deep inside `node_modules`. Sometimes it takes a bad snapshot of your entire mega-repo and uploads all your course folders to the live branch instead of just the compiled app.
**The Fix:** 
If your live branch gets cluttered with raw files, run these commands inside the specific app folder:
1. Delete the dirty branch: `git push origin --delete gh-pages`
2. Obliterate the hidden local cache: `rm -rf node_modules/.cache/gh-pages`
3. Deploy fresh: `npm run deploy`

### 2. The `.gitignore` Catch-22 (ProcessError)
**The Trap:** Git blocks the deploy tool because it is programmed to ignore the `node_modules` folder where the tool operates.
**The Fix:** You must lower the shield. Always rename `.gitignore` to `temp.gitignore` right before running `npm run deploy`, and rename it back immediately after. 

### 3. Wrong Terminal Location
**The Trap:** Running `git add .` or creating a Vite app while inside a subfolder. This creates nested `.git` repositories and destroys the single-repo structure.
**The Fix:** Always run standard Git commands (`add`, `commit`, `push`) and scaffold new apps from the **absolute root** of the directory. Only go into the specific app folder when you need to run `npm run deploy`.