# Recover Git Branch

```sh
$ git reflog
```

With this command, you can see the git action history. Then find the commit that you want to recover and checkout new branch using **HEAD@{NUMBER}** next to the commit checksum.

```sh
$ git checkout -b [DELETED BRANCH] HEAD@{NUMBER}
```
