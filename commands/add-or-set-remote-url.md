---
description: >-
  To add a remote repository to a existing git project or to update the existing
  rep
---

# Add or Set Remote URL

Note:- You can create a local git repo with "git init" command. Then you wont have the remote repository set. In that case you can add a remote repository with the following command.

```text
git remote add origin https://github.com/USERNAME/REPOSITORY.git
  -- or --
git remote add origin git@github.com:USERNAME/REPOSITORY.git
```

If you want to change the url of an existing remote repository:

```text
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
  -- or --
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

To find remote repo 

```text
git remote -v
```

[https://stackoverflow.com/questions/42830557/git-remote-add-origin-vs-remote-set-url-origin](https://stackoverflow.com/questions/42830557/git-remote-add-origin-vs-remote-set-url-origin)

