# GIT

## Origin

- In Git, origin is the default name given to the remote repository from which you cloned your local repository
- `origin` refers to the URL of the repository hosted on a remote server (like GitHub, GitLab, Bitbucket, etc.). It contains all the branches and commits of the project.

- `git fetch origin` - Fetches updates from the remote repository 'origin'
- `git pull origin master` - Fetches and merges changes from the 'master' branch of 'origin' into the current branch
- `git push origin master` - Pushes the local 'master' branch to the 'master' branch in the remote 'origin'
- `git branch -r` - Lists remote tracking branches, like 'origin/master
- `git remote -v` - This will display the URLs of the remote repositories linked to your local repository
- ```shell
    origin  https://github.com/user/repo.git (fetch)
    origin  https://github.com/user/repo.git (push)
    ```
- Adding a new remote - `git remote add new-remote https://github.com/user/another-repo.git`
- Updating remote - `git remote set-url origin https://github.com/user/new-repo.git`

































### Refs

- https://subscription.packtpub.com/book/programming/9781785287909/pref08
- https://subscription.packtpub.com/book/web-development/9781801075732/pref