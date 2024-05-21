## Missing File Fix:

```
~/ojemba/git-advanced-exercises (main) » touch test{1..4}.md                 ivy@ivy-HP-ProBook-430-G7
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main (root-commit) 064d9fd] chore: Create initial file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test1.md
[main 751f428] chore: Create another file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test2.md
[main fc90fcc] chore: Create third and fourth files
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
-------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git add test4.md && git commit --amend --no-edit
[main 389b997] chore: Create third and fourth files
Date: Tue May 21 10:29:19 2024 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
create mode 100644 test4.md
```

## Editing Commit History:

```
-------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git rebase -i HEAD~2                ivy@ivy-HP-ProBook-430-G7
Successfully rebased and updated refs/heads/main.
-------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git rebase -i --root                ivy@ivy-HP-ProBook-430-G7
Successfully rebased and updated refs/heads/main.
-------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git rebase -i HEAD~2                ivy@ivy-HP-ProBook-430-G7
Stopped at 751f428...  chore: Create another file
You can amend the commit now, with


 git commit --amend


Once you are satisfied with your changes, run


 git rebase --continue
-------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (751f428) » git commit --amend               ivy@ivy-HP-ProBook-430-G7
[detached HEAD dcd1c93] chore: Create second file
Date: Tue May 21 10:29:19 2024 +0200
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test2.md
-------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (dcd1c93) » git rebase --continue            ivy@ivy-HP-ProBook-430-G7
Successfully rebased and updated refs/heads/main.
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) »
~/ojemba/git-advanced-exercises (main) » git log --oneline


677b133 (HEAD -> main) chore: Create third and fourth files
dcd1c93 chore: Create second file
064d9fd chore: Create initial file
~
~
```

## Keeping History Tidy - Squashing Commits:

```
pick 064d9fd chore: Create initial file
squash dcd1c93 chore: Create second file
pick 677b133 chore: Create third and fourth files


# Rebase 677b133 onto 5e1a7aa (3 commands)


# This is a combination of 2 commits.
chore: Create inital files
# This is the 1st commit message:


chore: Create initial file


# This is the commit message #2:


chore: Create second file


~/ojemba/git-advanced-exercises (main) » git rebase -i --root                 ivy@ivy-HP-ProBook-430-G7
[detached HEAD c159b2a] chore: Create inital files
Date: Tue May 21 10:29:19 2024 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test1.md
create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.


~/ojemba/git-advanced-exercises (main*) » git log --oneline


ce65d78 (HEAD -> main) chore: Create third and fourth files
c159b2a chore: Create inital files
```

## Splitting a Commit:

```
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git reset HEAD~                      ivy@ivy-HP-ProBook-430-G7
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git add test3.md                    ivy@ivy-HP-ProBook-430-G7
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git commit -m 'chore: Create third file'
[main 0f96202] chore: Create third file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git status                          ivy@ivy-HP-ProBook-430-G7
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
 (use "git branch --unset-upstream" to fixup)


Untracked files:
 (use "git add <file>..." to include in what will be committed)
       test4.md


nothing added to commit but untracked files present (use "git add" to track)
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git add test4.md                    ivy@ivy-HP-ProBook-430-G7
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git commit -m 'chore: Create fourth file'
[main b59d885] chore: Create fourth file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test4.md
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git log --oneline

b59d885 (HEAD -> main) chore: Create fourth file
0f96202 chore: Create third file
c159b2a chore: Create inital files
```

## Advanced Squashing:

```
pick c159b2a chore: Create inital files
pick 6dea37d chore: Create third and fourth file


~/ojemba/git-advanced-exercises (main) » git rebase -i --root                 ivy@ivy-HP-ProBook-430-G7
[detached HEAD 6dea37d] chore: Create third and fourth file
Date: Tue May 21 10:50:40 2024 +0200
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test3.md
create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git rebase -i --root                 ivy@ivy-HP-ProBook-430-G7
Successfully rebased and updated refs/heads/main.


~/ojemba/git-advanced-exercises (main) » git log --oneline
6dea37d (HEAD -> main) chore: Create third and fourth file
c159b2a chore: Create inital files
```

## Dropping a Commit:

```
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git add .                            ivy@ivy-HP-ProBook-430-G7
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git commit -m 'chore:unwanted commit'
[main aa1c57b] chore:unwanted commit
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 unwanted.txt
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git log --oneline                    ivy@ivy-HP-ProBook-430-G7
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git log --oneline                    ivy@ivy-HP-ProBook-430-G7
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git reset --hard 70779ab             ivy@ivy-HP-ProBook-430-G7
HEAD is now at 70779ab chore: Create third and fourth file
```

## Reordering Commits:

```
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git rebase -i HEAD~2                 ivy@ivy-HP-ProBook-430-G7
fatal: invalid upstream 'HEAD~2'
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git rebase -i --root           128 ↵ ivy@ivy-HP-ProBook-430-G7
Successfully rebased and updated refs/heads/main.
------------------------------------------------------


pick 70779ab chore: Create third and fourth file
pick 41de8e2 chore: Create initial files


# Rebase 70779ab onto 8e25478 (2 commands)


--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main*) » git log                             ivy@ivy-HP-ProBook-430-G7
---------------------------------------------------
commit a565378b94165d4365f7067c1f499bbb50090565 (HEAD -> main)
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Tue May 21 10:29:19 2024 +0200


   chore: Create initial files


   chore: Create initial file


   chore: Create second file


commit 3af9ebbc41d40e807757c984fe3492475b93cf8c
Author: Murage-Ivy <ivymurage2000@gmail.com>
Date:   Tue May 21 11:05:37 2024 +0200


   chore: Create third and fourth file
```

## Git cherry pick

```
~/ojemba/git-advanced-exercises (ft/branch) » git log --oneline


b0ffe4d (HEAD -> ft/branch) chore:Implemented test 5
a565378 (main) chore: Create initial files
3af9ebb chore: Create third and fourth file




~/ojemba/git-advanced-exercises (ft/branch) » git switch main                 ivy@ivy-HP-ProBook-430-G7
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
 (use "git branch --unset-upstream" to fixup)
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git cherry-pick b0ffe4d              ivy@ivy-HP-ProBook-430-G7
[main 96a4850] chore:Implemented test 5
Date: Tue May 21 11:53:44 2024 +0200
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 test5.md
--------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (main) » git log --oneline

```

## Visualizing Commit History (Bonus):

```
~/ojemba/git-advanced-exercises (main) » git log --graph
* commit 9206daaaa0d1e7668f7854b75870ba4f915682b1 (HEAD -> main)
| Author: Murage-Ivy <ivymurage2000@gmail.com>
| Date:   Tue May 21 11:53:44 2024 +0200
|
|     chore:Implemented test 5
|
* commit 7b95a3c9de48134b1117e55871d9f003507b769e
| Author: Murage-Ivy <ivymurage2000@gmail.com>
| Date:   Tue May 21 10:29:19 2024 +0200
|
|     chore: Create initial files
|
|     chore: Create initial file
|
|     chore: Create second file
|
* commit fbfc70a12173bb89fd89e45d37eddf107d449f0e
 Author: Murage-Ivy <ivymurage2000@gmail.com>
 Date:   Tue May 21 10:50:40 2024 +0200
      chore: Create third and fourth file

     chore: Create third file

     chore: Create fourth file
(END)
```

## Understanding Reflogs (Bonus):

```
9206daa (HEAD -> main) HEAD@{0}: cherry-pick: chore:Implemented test 5
7b95a3c HEAD@{1}: checkout: moving from ft/branch to main
b0ffe4d (ft/branch) HEAD@{2}: checkout: moving from main to ft/branch
7b95a3c HEAD@{3}: rebase (finish): returning to refs/heads/main
7b95a3c HEAD@{4}: rebase (pick): chore: Create initial files
fbfc70a HEAD@{5}: rebase (pick): chore: Create third and fourth file
2a24d7b HEAD@{6}: rebase (start): checkout 2a24d7b98a2ec77efa7a0efa47e01f002a52fdf4
fe62014 HEAD@{7}: rebase (finish): returning to refs/heads/main
fe62014 HEAD@{8}: rebase: fast-forward
41de8e2 HEAD@{9}: rebase: fast-forward
f8ccfa5 HEAD@{10}: rebase (start): checkout f8ccfa52bfbe1f7403aa0228a1f6b1befc06ad39
fe62014 HEAD@{11}: reset: moving to fe62014
5d7e99b HEAD@{12}: reset: moving to 5d7e99b
96a4850 HEAD@{13}: cherry-pick: chore:Implemented test 5
a565378 HEAD@{14}: checkout: moving from ft/branch to main
b0ffe4d (ft/branch) HEAD@{15}: checkout: moving from main to ft/branch
a565378 HEAD@{16}: checkout: moving from ft/branch to main
b0ffe4d (ft/branch) HEAD@{17}: commit: chore:Implemented test 5
a565378 HEAD@{18}: checkout: moving from main to ft/branch
a565378 HEAD@{19}: rebase (finish): returning to refs/heads/main
a565378 HEAD@{20}: rebase (pick): chore: Create initial files
3af9ebb HEAD@{21}: rebase: fast-forward
3f2f89b HEAD@{22}: rebase (start): checkout 3f2f89bd188390031bda8a5ca5b1c629a847aca7
0d0643e HEAD@{23}: rebase (finish): returning to refs/heads/main
0d0643e HEAD@{24}: rebase (pick): chore: Create third and fourth file
95418c6 HEAD@{25}: rebase (pick): chore: Create initial files
c6cf672 HEAD@{26}: rebase (start): checkout c6cf6723a81b1efeae61bc841fe5bf76c4054755
f05ba71 HEAD@{27}: rebase (finish): returning to refs/heads/main
f05ba71 HEAD@{28}: rebase: fast-forward
3af9ebb HEAD@{29}: rebase: fast-forward
c8c51a5 HEAD@{30}: rebase (start): checkout c8c51a56a74771be366d9afb94851af0af23ea8a
f05ba71 HEAD@{31}: rebase (finish): returning to refs/heads/main
f05ba71 HEAD@{32}: rebase (pick): chore: Create initial files
3af9ebb HEAD@{33}: rebase (pick): chore: Create third and fourth file
8e25478 HEAD@{34}: rebase (start): checkout 8e2547849b854f047cf644234e08060b1cd7ab13
70779ab HEAD@{35}: reset: moving to 70779ab
aa1c57b HEAD@{36}: commit: chore:unwanted commit
```
