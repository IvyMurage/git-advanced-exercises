## Feature Branch Creation:

```
~/ojemba/git-advanced-exercises (main) » git branch
~/ojemba/git-advanced-exercises (main) » git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
~/ojemba/git-advanced-exercises (ft/new-feature) » git switch ft/new-feature
Already on 'ft/new-feature'
```

## Working on the Feature Branch:

```
~/ojemba/git-advanced-exercises (ft/new-feature) » git status
On branch ft/new-feature
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        feature.txt
nothing added to commit but untracked files present (use "git add" to track)
~/ojemba/git-advanced-exercises (ft/new-feature*) » git add .
~/ojemba/git-advanced-exercises (ft/new-feature*) » git commit -m "Implemented core functionality for new feature"
[ft/new-feature 7e3cfce] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

## Switching Back and Making More Changes:

```
~/ojemba/git-advanced-exercises (ft/new-feature) » git switch main                                                 128 ↵
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

~/ojemba/git-advanced-exercises (main) » git add .

~/ojemba/git-advanced-exercises (main*) » git commit -m 'Updated project readme'
[main 5d184de] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

## Local vs. Remote Branches:

```
~/ojemba/git-advanced-exercises (main) » git pull origin ft/new-feature
From github.com:IvyMurage/git-advanced-exercises
 * branch            ft/new-feature -> FETCH_HEAD
Merge made by the 'ort' strategy.
 README.md   | 25 +++++++++++++++++++++++++
 feature.txt |  1 +
 2 files changed, 26 insertions(+)
 create mode 100644 README.md
 create mode 100644 feature.txt

```

## Branch Deletion:

```
~/ojemba/git-advanced-exercises (main) » git branch -d ft/new-feature                                                    ivy@ivy-HP-ProBook-430-G7
Deleted branch ft/new-feature (was 7426c91).

```

## Creating a Branch from a Commit:

```
~/ojemba/git-advanced-exercises (main) » git checkout -b ft/feature-102 5d184de ivy@ivy-HP-ProBook-430-G7
Switched to a new branch 'ft/feature-102'
~/ojemba/git-advanced-exercises (ft/feature-102) » git log --oneline ivy@ivy-HP-ProBook-430-G7
5d184de (HEAD -> ft/feature-102) Updated project readme
9206daa (origin/main) chore:Implemented test 5
7b95a3c chore: Create initial files
fbfc70a chore: Create third and fourth file

```

## Branch Merging:

```
~/ojemba/git-advanced-exercises (main) » git pull origin ft/feature-102                                                  ivy@ivy-HP-ProBook-430-G7
From github.com:IvyMurage/git-advanced-exercises
 * branch            ft/feature-102 -> FETCH_HEAD
Auto-merging README.md
CONFLICT (add/add): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
--------------------------------------------------------------------
```

## Branch Rebasing:

```
~/ojemba/git-advanced-exercises (ft/feature-102) » git rebase -i main                                                    ivy@ivy-HP-ProBook-430-G7
Successfully rebased and updated refs/heads/ft/feature-102.

```

## Renaming Branches:

```
~/ojemba/git-advanced-exercises (main) » git switch ft/feature-102                                                       ivy@ivy-HP-ProBook-430-G7
Switched to branch 'ft/feature-102'
Your branch and 'origin/ft/feature-102' have diverged,
and have 3 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
~/ojemba/git-advanced-exercises (ft/feature-102) » git branch -m ft/feature-102 ft/feature-branch
```

## Checking Out Detached HEAD:

```
~/ojemba/git-advanced-exercises (ft/feature-branch) » git checkout 7b95a3c                                               ivy@ivy-HP-ProBook-430-G7
Note: switching to '7b95a3c'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 7b95a3c chore: Create initial files
---------------------------------------------------------------------------------------------------------------------------------------------------
~/ojemba/git-advanced-exercises (7b95a3c) » git checkout -b  ft/test-branch                                              ivy@ivy-HP-ProBook-430-G7
Switched to a new branch 'ft/test-branch'
```
