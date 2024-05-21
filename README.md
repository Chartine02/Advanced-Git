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

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git  rebase -i --root
Stopped at 7f864c1...  chore: Create another file
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main|REBASE 3/5)
$ git commit --amend
[detached HEAD f6ae3bc] chore: Create second file
 Date: Mon May 20 19:42:08 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main|REBASE 3/5)
$ git rebase --continue
You must edit all merge conflicts and then
mark them as resolved using git add

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main|REBASE 3/5)
$ git add .

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main|REBASE 3/5)
$ git commit -m 'updated readme'
[detached HEAD 2eaaa04] updated readme
 1 file changed, 1 insertion(+), 1 deletion(-)

```

### Keeping History Tidy - Squashing Commits

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git rebase -i --root
[detached HEAD 586ba7e] Creating initial files
 Date: Mon May 20 19:42:07 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git log
commit 85362b6b7e23ec54651848bac2041ea526869e4b (HEAD -> main)
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 07:54:22 2024 +0200

    Updated readme

commit e944609d6e86f950577fb71eee6686b74b8c85da
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Mon May 20 19:42:41 2024 +0200

    created the fourth file

commit 204e37ac695a583fb533a01411df6e87d0eccf21
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 08:11:26 2024 +0200

    updated readme

commit 586ba7e4eeb11e6963b1832164ce801c978f3b29
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Mon May 20 19:42:07 2024 +0200

    Creating initial files

```

### Splitting commit

```
git reflog
git rebase -i b193351
git reset HEAD~
git rebase --continue
```
