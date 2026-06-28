# 1. Initialize Git in your project folder
git init

# 2. Add all your files to the staging area
git add .

# 3. Commit your files with a descriptive message
git commit -m "Initial commit: setting up project structure"

# 4. Rename your local branch to 'main' (if it isn't already)
git branch -M main

# 5. Add your remote GitHub repository address
# (Replace the link below with your actual repo URL)
git remote add origin https://github.com/your-username/your-repo-name.git

# 6. Push your code to GitHub
git push -u origin main