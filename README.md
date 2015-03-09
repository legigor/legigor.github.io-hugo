# Personal blog sources

Built with hugo_0.13_windows_amd64 and configured using this doc http://gohugo.io/tutorials/github-pages-blog/

1. Create a working Hugo website, setup a theme, create a first post, makre sure `$ hugo` creates the output HTML in the `./public` folder. Remove the `./public` folder before proceeding to the next steps.
2. `git init` - create a new repo and commit **something** to the `master` branch: `git add README.md & git commit -m "Init"`. This branch will be used to commit the html output from the hugo build.
3. Create an orphan branch to store the website source files: `git checkout --orphan hugo`, then commit the entire folder content to this branch `git add . & git commit -m "Add website sources"`
4. Create a remote repository and then add it as origin to our local repo and then push **all** branches there `git push --all origin` 
5. Now its time to link the **master** branch to the **./public** folder: `git subtree add --prefix=public git@github.com:legigor/legigor.github.io.git master --squash` and pull the master's content `git subtree pull --prefix=public git@github.com:legigor/legigor.github.io.git master --squash`
6. Build the website from the sources: `hugo`. Make sure build output stored in the `./public` folder
7. Commit all changes: `git add . & git commit -m "Build website"`
8. Optional step: push all changes to github `git push --all`
9. Push the './public' folder to the **master** branch: `git subtree push --prefix=public git@github.com:legigor/legigor.github.io.git master`
10. Check the url http://legigor.github.io and make sure everything works as expected

## TODO

* Create some build scripts for publishing 
* Add hugo.exe to the sources to make it portable
