# Git & GitHub Learned form problem (Windows)

### How to upload existing folder to existing repo

1. cd C:\Projects\MyDjangoProject
2. git init
3. git remote add origin https://github.com/yourusername/your-django-repo.git
4. git add .
5. git commit -m "Initial commit with existing files"
6. git push -u origin main

##### Warn

If subfolder has `.git` folder, Git will show error.

Error:

```
warning: adding embedded git repository: django_basic
hint: You've added another git repository inside your current repository
```

To remove initialized subfolders in query list use: `git rm --cached git_tracked_dir_name ` [This will not be removed from filesystem (working tree)]

### How to remove git init

To remove the embedded Git repositories from the folder, you need to delete its `.git` directories.

##### Way 1 (better way)

Use: `rd /s /q path\to\your\folder` on windows cmd
Above command will permanently delete `.git` folder and all its contents.

##### Way 2

1. Go to directory where `.git` exist
2. And use: `rmdir .git`
   This will only delete its contents for permanent. (`.git` folder will not be deleted)

### Add submodule (repo inside a repo)

1. Go to your initialized repo directory
2. Use:  `git submodule add <repository-url from github> dir_name`
   This will clone repo from GitHub to dir_name

### Pull from other branches (in my case main)

1. Switch to branch that you want to track
   Use: `git switch main`
2. Set the upstream branch for main to origin/main
   Use: `git branch --set-upstream-to=origin/main main`
3. Pull from origin/main: `git pull origin main`
4. Push the changes to main: `git push origin main`

### Handling Non-Fast-Forward Error

If you are sure that you want to overwrite the remote changes with your local changes (this is generally not recommended unless you are sure about it),
you can force push: `git push origin main --force`
