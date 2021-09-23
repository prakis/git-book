---
description: To reset a file to the original file
---

# Reset a file

To reset a file to its orginal file \(remove your changes to the file abc.txt\)

```text
# With Git 2.23
git restore abc.txt  

# With older version of git
git checkout -- abc.txt
```

To do full reset a file \(reset the file back to original remote format\)

```text
git checkout @ -- abc.txt

git checkout HEAD -- abc.txt
```

[https://stackoverflow.com/questions/7147270/hard-reset-of-a-single-file](https://stackoverflow.com/questions/7147270/hard-reset-of-a-single-file)

