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
