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
