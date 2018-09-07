# React Dev

## Creating a New Project

1. Create the project on github.com
2. Get a local copy of the project at this point
  ```bash
  git clone https://github.com/my_repo
  mv my_repo changeme_my_repo
  ```
3. Get the demo app from npx
  ```bash
  npx create-react-app my_repo
  cd my_repo
  npm start
  ```
4. Getting the configuration back
  ```bash
  git init
  cp -Ra ../changme_my_repo/* ./
  git status
  ```

Here you should have a working directory with a working react app inside.

5. Cleaning work
  ```bash
  git add .gitignore
  git commit -m "add gitignore for react"
  git add .
  git commit -m "demo react app"
  git push
  ```