# Recover Git Branch

```sh
$ git reflog
4576185 (HEAD -> master, origin/master) HEAD@{0}: commit: Fix ...
740a1a3 HEAD@{1}: commit: Add ...
e5cc93f HEAD@{2}: commit: README.md
d626c90 HEAD@{3}: commit (initial): Init commit
```

With this command, you can see the git action history. Then find the commit that you want to recover and checkout new branch using **HEAD@{NUMBER}** next to the commit checksum.

```sh
$ git checkout -b [DELETED BRANCH] HEAD@{NUMBER}
```
