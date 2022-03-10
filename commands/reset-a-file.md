---
description: To reset a file to the original file
---

# Reset a file or full

To reset a file to its orginal file (remove your changes to the file abc.txt)

```
# With Git 2.23
git restore abc.txt  

# With older version of git
git checkout -- abc.txt
```

To do full reset a file (reset the file back to original remote format)

```
git checkout @ -- abc.txt

git checkout HEAD -- abc.txt
```

{% embed url="https://stackoverflow.com/questions/7147270/hard-reset-of-a-single-file" %}

### **To reset a local branch exactly to the remote**&#x20;

```
git fetch origin
git reset --hard origin/master
```
