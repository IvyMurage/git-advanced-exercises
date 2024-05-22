## Stashing Changes:

```
~/ojemba/git-advanced-exercises (main*) » git stash push -m 'This are the new changes'                                   ivy@ivy-HP-ProBook-430-G7
Saved working directory and index state On main: This are the new changes
```

## Retrieving Stashed Changes:

```
~/ojemba/git-advanced-exercises (main) » git stash pop                                                                   ivy@ivy-HP-ProBook-430-G7
Removing README.md
On branch main
Your branch is ahead of 'origin/main' by 10 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test6.md

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    README.md

Dropped refs/stash@{0} (362214ac7de3a2f83a598feb5d8a75fc13f968e6)
```
