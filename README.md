# git-add-commit-push-all-in-one-config
Git command to add, commit, and push the code with a single command

Most of the times, I end up doing a small change to my code, and to push it to the GIT repository, I have first to do a Git add, then a commit, and finally a push. I find it annoying sometimes, but some other time, I type it out as it is in my muscle memory. I don't even realise that I had to give three different commands to push the code. 

## So, what next?
A quick solution would be, write a bash or batch script that can do the job. Great, now I have another problem. I need to keep that script it in all the Projects folders so I can invoke them.

## OK, then, what next?
In that case, write a bash or batch script and configure the path as your global environment variable. Sounds nice, but Git should have some option that can make it simpler than what I do. Well, they do. How about using the Git Global configuration.

## How to use Git Global configuration
```
git config --global alias.cmp "!f() { git add -A && git commit -m "$@" && git push; }; f"
```
The above script creates an alias for "add", "commit", and "push" as a single command "cmp"

## How to use it?
```
git cmp "test commit"
```

## Sample Output will look like this
```
C:\Users\gp\Projects\test-project>git cmp "commit"
[master 966b73d] commit
 1 file changed, 3 insertions(+), 3 deletions(-)
Enter passphrase for key '/c/Users/gp/.ssh/id_rsa':
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads.
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 497 bytes | 497.00 KiB/s, done.
Total 6 (delta 4), reused 0 (delta 0)
To gp.git.com:test-project
   ac9d70f..966b73d  master -> master
```
