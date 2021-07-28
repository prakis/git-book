---
description: How to undo/remove file after  'git add'
---

# git undo add

Lets say you mistakenly added a file using the following command.

```text
git add abc.txt
```

To undo adding run the following. 

```bash
git reset HEAD abc.txt
```

**Dont do git reset, you will loose changes** 

```bash
git reset abc.txt    < ---- DONT DO THIS
```

[https://stackoverflow.com/questions/348170/how-do-i-undo-git-add-before-commit](https://stackoverflow.com/questions/348170/how-do-i-undo-git-add-before-commit)

