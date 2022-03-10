# Commit changes to other branch

You can commit changes in different types.

#### Type 1:

```
git stash
git checkout otherBranch
git stash pop
```

#### Type 2:

```
git branch otherBranch
git checkout -b otherBranch
```

#### Type 3:

```
git checkout otherBranch
git add *
git commit -m
```

``

``[`https://stackoverflow.com/questions/2944469/how-to-commit-my-current-changes-to-a-different-branch-in-git`](https://stackoverflow.com/questions/2944469/how-to-commit-my-current-changes-to-a-different-branch-in-git)``
