## Fixing Origin

### Remove directory from remote repository after adding them to .gitignore
Q:  I committed and pushed some directory to github. After that, I altered the .gitignore file adding a directory that should be ignored. Everything works fine, but the (now ignored) directory stays on github.  How do I delete that directory from github and the repository history?

A: The rules in your .gitignore file only apply to untracked files. Since the files under that directory were already committed in your repository, you have to unstage them, create a commit, and push that to GitHub:

```
$ git rm -r --cached some-directory
$ git commit -m 'Remove the now ignored directory "some-directory"'
$ git push origin master
```



### ___