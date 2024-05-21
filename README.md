# Advanced-Git

### Initialize Your Environment

```
ouch test{1..4}.md
bash: ouch: command not found

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git add test1.md && git commit -m "chore: Create initial file"
fatal: pathspec 'test1.md' did not match any files

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git add test2.md && git commit -m "chore: Create another file"
fatal: pathspec 'test2.md' did not match any files

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git add test3.md && git commit -m "chore: Create third and fourth files"^C

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ touch test{1..4}.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git add test1.md && git commit -m "chore: Create initial file"
[main 1c69ee9] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git add test2.md && git commit -m "chore: Create another file"
[main 7f864c1] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main b193351] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

```

## Refining git history

### Missing files

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git log
commit b193351b24f69e39b5434eaaada750b4dd3a2473 (HEAD -> main)
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Mon May 20 19:42:41 2024 +0200

    chore: Create third and fourth files

commit 7f864c12043b80ab3d18a7c87188c9035d1a6609
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Mon May 20 19:42:08 2024 +0200

    chore: Create another file

commit 1c69ee9a5e9c8f28cd6fb5ce3ba317e49c20ed8c
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Mon May 20 19:42:07 2024 +0200

    chore: Create initial file

commit b295bded34791990476b539e634b3fd451e2ddce (origin/main, origin/HEAD)
Author: Chartine02 <141454615+Chartine02@users.noreply.github.com>
Date:   Mon May 20 17:08:37 2024 +0100

    Initial commit

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git commit --amend -m "created the fourth file"
[main ba0b696] created the fourth file
 Date: Mon May 20 19:42:41 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
```

### Edit commit history
