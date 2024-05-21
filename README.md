# Advanced-Git

### Initialize Your Environment

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ touch test{1..4}.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add test1.md && git commit -m "chore: Create initial file"
[main (root-commit) 8b3c8fb] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add test2.md && git commit -m "chore: Create another file"
[main 97204f1] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
chore: Create third and fourth files
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main 9cc368d] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git status
On branch main
edit 97204f1 chore: Create another file
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git log
chore: Create second file
commit 9cc368dd07bb10ef6cb474d7bb2ff026de77b715 (HEAD -> main)
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 11:54:13 2024 +0200

    chore: Create third and fourth files

commit 97204f189761b133c3b92bc198826bd215ff3010
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 11:54:12 2024 +0200

    chore: Create another file

commit 8b3c8fbd024f95ca43b2dc241e7fb822ad6501e1
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 11:54:11 2024 +0200

    chore: Create initial file

```

## Refining git history

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add .

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git commit --amend
pick 8b3c8fb chore: Create initial file
# This is a combination of 2 commits.
[main 9ceed82] chore: Create third and fourth files
 Date: Tue May 21 11:54:13 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
```

### 1.Missing files

```
$ git rebase -i HEAD~2
Stopped at 97204f1...  chore: Create another file
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main|REBASE 1/2)
$ git commit --amend
[detached HEAD 38d44fd] chore: Create second file
 Date: Tue May 21 11:54:12 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

 TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main|REBASE 1/2)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

```

### 2.Edit commit history

```

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git reset HEAD~

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add test3.md && git commit -m 'Add third file'
[main e945194] Add third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add test4.md && git commit -m 'Add fourth file'
[main c43b75e] Add fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md


```

### 3.Keeping History Tidy - Squashing Commits

```

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git (main)
$ git rebase -i --root
[detached HEAD 586ba7e] Creating initial files
Date: Mon May 20 19:42:07 2024 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test1.md
create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

```

### 4.Splitting commit

```

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git reset HEAD~

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add test3.md && git commit -m 'Add third file'
[main e945194] Add third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add test4.md && git commit -m 'Add fourth file'
[main c43b75e] Add fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

```

### 5.Advanced Squashing

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git rebase -i --root
[detached HEAD e321886] Create third and fourth files
 Date: Tue May 21 12:15:04 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

### 6.Dropping a Commit

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add unwanted.txt

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git commit -m 'Unwanted commit'
[main 9e27263] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt


TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git rebase -i --root
Stopped at 9e27263...  Unwanted commit
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main|REBASE 3/3)
$ git reset --hard HEAD~1
HEAD is now at e321886 Create third and fourth files
```

### 7.Reordering Commits

```
git rebase -i --root
```

### 8.Cherry-Picking Commits

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git checkout -b ft-branch
Switched to a new branch 'ft-branch'

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft-branch)
$ touch test5.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft-branch)
$ git add .

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft-branch)
$ git commit -m 'Implemented test 5'
[ft-branch ea5afb0] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft-branch)
$ git log
commit ea5afb0ef11c769a76666d65723cfde2f7f71532 (HEAD -> ft-branch)
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 14:31:00 2024 +0200

    Implemented test 5

commit 7feaa8420a5cb347b6faee067f8240437cf56d3f (main)
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 11:54:11 2024 +0200

    Create initial files

    chore: Create initial file

    chore: Create second file

commit 51d7a039903183e11576fa4df4f196570d063198
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 12:15:04 2024 +0200

    Create third and fourth files

    Add third file

    Add fourth file

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft-branch)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git cherry-pick ea5afb0ef11c769a76666d65723cfde2f7f71532
[main fc3d1af] Implemented test 5
 Date: Tue May 21 14:31:00 2024 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git log
commit fc3d1afce1ab6be4ce44fad98f1f57f865f30ad7 (HEAD -> main)
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 14:31:00 2024 +0200

    Implemented test 5

commit 7feaa8420a5cb347b6faee067f8240437cf56d3f
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 11:54:11 2024 +0200

    Create initial files

    chore: Create initial file

    chore: Create second file

commit 51d7a039903183e11576fa4df4f196570d063198
Author: Chartine02 <noellachartine125@gmail.com>
Date:   Tue May 21 12:15:04 2024 +0200

    Create third and fourth files

    Add third file

    Add fourth file
```
