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

### Part 1: Refining git history

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

### 9.Visualizing Commit History (Bonus)

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git log --graph
* commit fc3d1afce1ab6be4ce44fad98f1f57f865f30ad7 (HEAD -> main)
| Author: Chartine02 <noellachartine125@gmail.com>
| Date:   Tue May 21 14:31:00 2024 +0200
|
|     Implemented test 5
|
* commit 7feaa8420a5cb347b6faee067f8240437cf56d3f
| Author: Chartine02 <noellachartine125@gmail.com>
| Date:   Tue May 21 11:54:11 2024 +0200
|
|     Create initial files
|
|     chore: Create initial file
|
|     chore: Create second file
|
* commit 51d7a039903183e11576fa4df4f196570d063198
  Author: Chartine02 <noellachartine125@gmail.com>
  Date:   Tue May 21 12:15:04 2024 +0200

      Create third and fourth files

      Add third file

      Add fourth file

```

### 10.Understanding Reflogs (Bonus)

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git reflog
fc3d1af (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
7feaa84 HEAD@{1}: checkout: moving from ft-branch to main
ea5afb0 (ft-branch) HEAD@{2}: commit: Implemented test 5
7feaa84 HEAD@{3}: checkout: moving from main to ft-branch
7feaa84 HEAD@{4}: rebase (finish): returning to refs/heads/main
7feaa84 HEAD@{5}: rebase (pick): Create initial files
51d7a03 HEAD@{6}: rebase (pick): Create third and fourth files
3fed002 HEAD@{7}: rebase (start): checkout 3fed00258523525b86d35e3d8e28135e54be7b1e
e321886 HEAD@{8}: rebase (finish): returning to refs/heads/main
e321886 HEAD@{9}: rebase (start): checkout HEAD~1
e321886 HEAD@{10}: rebase (finish): returning to refs/heads/main
e321886 HEAD@{11}: rebase (start): checkout HEAD~1
e321886 HEAD@{12}: rebase (finish): returning to refs/heads/main
e321886 HEAD@{13}: rebase: fast-forward
29598c3 HEAD@{14}: rebase: fast-forward
2d384f3 HEAD@{15}: rebase (start): checkout 2d384f33418bd27296c717307906122b0e1adc81
e321886 HEAD@{16}: rebase (finish): returning to refs/heads/main
e321886 HEAD@{17}: reset: moving to HEAD~1
9e27263 HEAD@{18}: rebase: fast-forward
e321886 HEAD@{19}: rebase: fast-forward
29598c3 HEAD@{20}: rebase: fast-forward
810f405 HEAD@{21}: rebase (start): checkout 810f4057cfe8e75d7d965a70382ae15662518c5d
9e27263 HEAD@{22}: commit: Unwanted commit
e321886 HEAD@{23}: rebase (finish): returning to refs/heads/main
e321886 HEAD@{24}: rebase (squash): Create third and fourth files
e945194 HEAD@{25}: rebase: fast-forward
29598c3 HEAD@{26}: rebase: fast-forward
ab78a40 HEAD@{27}: rebase (start): checkout ab78a40af02ce71550de7ceecbce2ffd0b676b64
c43b75e HEAD@{28}: commit: Add fourth file
e945194 HEAD@{29}: commit: Add third file
29598c3 HEAD@{30}: reset: moving to HEAD~
ed4f5bb HEAD@{31}: rebase (finish): returning to refs/heads/main
ed4f5bb HEAD@{32}: rebase: fast-forward
29598c3 HEAD@{33}: rebase: fast-forward
c3254ca HEAD@{34}: rebase (start): checkout c3254cabedc3dd20afb85fe5867de85120468e66
ed4f5bb HEAD@{35}: rebase (finish): returning to refs/heads/main
ed4f5bb HEAD@{36}: rebase (pick): chore: Create third and fourth files
29598c3 HEAD@{37}: rebase (squash): Create initial files
8b3c8fb HEAD@{38}: rebase: fast-forward
3742603 HEAD@{39}: rebase (start): checkout 37426030ff1fa2f8e43d973dd79fac1a64210129
be54904 HEAD@{40}: rebase (finish): returning to refs/heads/main
be54904 HEAD@{41}: rebase (pick): chore: Create third and fourth files
```

## Part 2 : Branching Basics (10 Challenges)

### Feature Branch Creation

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft/new-feature)
$ git add .

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft/new-feature)
$ git commit -m 'Implemented core functionality for new feature.'
[ft/new-feature 5e5d9e2] Implemented core functionality for new feature.
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

#### Switching Back and Making More Changes

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ touch readme.txt

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git add readme.txt

TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git commit -m 'Updated project readme'
[main 5446465] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

### Local vs. Remote Branches

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git pull
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 897 bytes | 42.00 KiB/s, done.
From https://github.com/Chartine02/Advanced-Git-Exercises
   5446465..fc28666  main       -> origin/main
Updating 5446465..fc28666
Fast-forward
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

```

### Branch Deletion

```
TheGym@DESKTOP-9QFHBAI MINGW64 ~/Desktop/Gym/Advanced-Git-Exercises (main)
$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was 5e5d9e2).
```
