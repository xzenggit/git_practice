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
### Work with branches

* Check current branch name
```bash
$ git branch
* master
```
Typically, we don't work directly in the master branch. Instead, we make our own branch and do coding there. Here we make a new branch `exp1`.

* Create a new branch
```bash
$ git checkout -b exp1
Switched to a new branch 'exp1'

$ git branch
* exp1
  master
```

After we make some changes under the new branch, we can push it to remote repo, or merge with master branch locally.

Make some changes and commit to `exp1`.

* Commit to new branch
```bash
$ git add .
$ git commit -m "new changes"
[exp1 2983e7d] new changes
 1 file changed, 28 insertions(+)
```
* Push the new branch to remote repo
```bash
$ git push origin exp1
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 950 bytes | 950.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote:
remote: Create a pull request for 'exp1' on GitHub by visiting:
remote:      https://github.com/xxx/git_practice/pull/new/exp1
remote:
To https://github.com/xxx/git_practice.git
 * [new branch]      exp1 -> exp1
```

* Check the git status
```bash
$ git status
On branch exp1
nothing to commit, working tree clean
```

Now, our `exp1` has the most updated version. We can further merge it with master and push the master branch to remote repo and make it our updated official package.

* Swith branches
```bash
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```
* Merge branches
```bash
$ git merge exp1
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```
After editing the conflicts, we can commit the new changes to master branch.

```bash
$ git add .
$ git commit -m "merge exp1"
$ git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 306 bytes | 306.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/xxx/git_practice.git
   535d021..69a5279  master -> master
```

If the master branch has latest code, we can always pull it to the `exp1` branches
```bash
$ git pull origin master
```

### Summary

```bash
# Clone remote repo to local
$ git clone https://github.com/xxx/git_practice.git
# Make your own work branch
$ git checkout -b exp1
# Check local branches
$ git branch
# Make some changes in exp1 and commit to remote repo
$ git add .
$ git commit -m "new changes"
$ git push origin exp1
# Change to master branch
$ git checkout master
# Make sure master branch have the latest code from remote repo
$ git pull origin master
# Merge exp1 with master
$ git merge exp1
# Push latest version to remote repo
$ git push origin master
```
