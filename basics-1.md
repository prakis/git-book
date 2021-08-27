---
description: Commands and their purpose for basic git operations
---

# Basics



### Git Clone

When you clone a remote git repository, that remote code is copied into your 'Local Repository' and also it is copied into your 'Working Directory' \(Staging area is empty for freshly cloned projects\).

### Git add

After you modify your local files, to add them to Staging area.

```text
git add file1.java file2.java
git add *
```

{% hint style="info" %}
You can add all files with \* ex:- git add \*
{% endhint %}

### Git Commit

To move the currently staged files into local repository. You can also label the current commit with a description.

```text
git commit -m 'image compression module'
```

### Git Push

To push your local repository changes to the remote git repository\(on remote git server\).

```text
git push origin master
```

### Git Pull

Git pull will fetch the remote git code \(from git server\) to the local git repository and also merges those files to your working directory. You will most frequently use 'Git Pull' over 'Git Fetch'.

Git Pull = Git Fetch + Git Merge

```text
git pull
```

### Git Fetch

To pull other developers code from the remote git repository to the local repository. Git fetch wont merge these freshly fetched files files into 'Working directory'. Check 'Git Pull'.

```text
git fetch origin
```

### Git Merge 

You want to merge the code which is in the local repository to your working direcotry

You may wonder why will your code in your local repository different to your working directory. This happens when you pull code from the remote repository, that will be moved from remote to local repository and then into your working directory.

```text
git merge
```

### 



