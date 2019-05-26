# git_practice
A demo of how to use git in real life


### Download code repo
```bash
$ git clone https://github.com/xxx/git_practice.git
Cloning into 'git_practice'...
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (5/5), done.
```
### Check current branch name
```bash
$ git branch
* master
```
Typically, we don't work directly in the master branch. Instead, we make our own branch and do coding there. Here we make a new branch `exp1`.
```bash
$ git checkout -b exp1
Switched to a new branch 'exp1'

$ git branch
* exp1
  master
```

After we make some changes under the new branch, we can push it to remote repo, or merge with master branch locally.
