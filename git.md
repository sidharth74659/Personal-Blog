# Table of contents

- [Logging into Github from Terminal using Personal Access Tokens](#logging-into-github-from-terminal-using-personal-access-tokens)
- [Change git repository name locally](#change-git-repository-name-locally)

#### Logging into Github from Terminal using Personal Access Tokens

- [Login to github in command-line using personal-access-token](https://stackoverflow.com/questions/66231282/how-to-add-github-personal-access-token-to-visual-studio-code)

  Personal Access Tokens : Go to profile > Settings > Developer Settings > Personal Access Tokens > Generate New Token > Enable required Permissisons > copy code/token (which is availaible only once)

  ```
  git remote set-url origin https://<username>:<personal-access-token>@github.com/<username>/<repository-name>.git
  ```

  ```
  git remote add origin https://[USERNAME]:[NEW TOKEN]@github.com/[USERNAME]/[REPO].git
  ```


#### Change git repository name locally
- [change git repository name locally](https://www.codepoc.io/blog/git/5617/change-git-repository-name-locally)

  ```
  cd projectFolder
  git remote -v (it will show previous git url)
  git remote set-url origin https://username@bitbucket.org/username/newName.git
  git remote -v (double check, it will show new git url)
  git push (do whatever you want.)
  ```