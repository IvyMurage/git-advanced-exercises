## Stashing Changes:

```
~/ojemba/git-advanced-exercises (main*) » git stash push -m 'This are the new changes'
Saved working directory and index state On main: This are the new changes
```

## Retrieving Stashed Changes:

```
~/ojemba/git-advanced-exercises (main) » git stash pop
Removing README.md
On branch main
Your branch is ahead of 'origin/main' by 10 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)



Dropped refs/stash@{0} (362214ac7de3a2f83a598feb5d8a75fc13f968e6)
```

## Branch Merging Conflicts (Continued):

```
~/ojemba/git-advanced-exercises (main) » git pull origin ft/test-6-feature
From github.com:IvyMurage/git-advanced-exercises
 * branch            ft/test-6-feature -> FETCH_HEAD
Auto-merging feature.txt
CONFLICT (content): Merge conflict in feature.txt
Automatic merge failed; fix conflicts and then commit the result.


```

## Resolving Merge Conflicts with a Merge Tool:

```
~/ojemba/git-advanced-exercises (main*) » git status                                                                 1 ↵
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
 (use "git push" to publish your local commits)


All conflicts fixed but you are still merging.
 (use "git commit" to conclude merge)


Changes to be committed:
       modified:   feature.txt

```

## Understanding Detached HEAD State:

```
~/ojemba/git-advanced-exercises (ft/test-6-feature) » git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
~/ojemba/git-advanced-exercises (main) » git switch ft/test-6-feature
Switched to branch 'ft/test-6-feature'
Your branch is up to date with 'origin/ft/test-6-feature'.
~/ojemba/git-advanced-exercises (ft/test-6-feature) » git log --oneline
~/ojemba/git-advanced-exercises (ft/test-6-feature) » git checkout fbfc70a
Note: switching to 'fbfc70a'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at fbfc70a chore: Create third and fourth file
~/ojemba/git-advanced-exercises (fbfc70a) » git checkout -b ft/test-3-4-feature
Switched to a new branch 'ft/test-3-4-feature'
~/ojemba/git-advanced-exercises (ft/test-3-4-feature*) » git branch
~/ojemba/git-advanced-exercises (ft/test-3-4-feature*) » git status
On branch ft/test-3-4-feature
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test3.md
        modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")
~/ojemba/git-advanced-exercises (ft/test-3-4-feature*) » git add .
~/ojemba/git-advanced-exercises (ft/test-3-4-feature*) » git commit -m 'Add new test cases'
[ft/test-3-4-feature 776a54c] Add new test cases
 2 files changed, 2 insertions(+)
~/ojemba/git-advanced-exercises (ft/test-3-4-feature) » git push -u origin ft/test-3-4-feature
Enumerating objects: 7, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 381 bytes | 381.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'ft/test-3-4-feature' on GitHub by visiting:
remote:      https://github.com/IvyMurage/git-advanced-exercises/pull/new/ft/test-3-4-feature
remote:
To github.com:IvyMurage/git-advanced-exercises.git
 * [new branch]      ft/test-3-4-feature -> ft/test-3-4-feature
Branch 'ft/test-3-4-feature' set up to track remote branch 'ft/test-3-4-feature' from 'origin'.
```

## Ignoring Files/Directories:

```
~/ojemba/git-advanced-exercises (ft/test-6-feature) » git rm readme.txt --cached
rm 'readme.txt'
~/ojemba/git-advanced-exercises (ft/test-6-feature*) » git status
On branch ft/test-6-feature
Your branch is up to date with 'origin/ft/test-6-feature'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    readme.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

~/ojemba/git-advanced-exercises (ft/test-6-feature*) » git add .
~/ojemba/git-advanced-exercises (ft/test-6-feature*) » git commit -m 'git igrnore readme.txt'
[ft/test-6-feature dae7c05] git igrnore readme.txt
 2 files changed, 1 insertion(+), 1 deletion(-)
 create mode 100644 .gitignore
 delete mode 100644 readme.txt
~/ojemba/git-advanced-exercises (ft/test-6-feature) » git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 295 bytes | 295.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:IvyMurage/git-advanced-exercises.git
   99d4a45..dae7c05  ft/test-6-feature -> ft/test-6-feature
------------
```
