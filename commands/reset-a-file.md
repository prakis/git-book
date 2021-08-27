---
description: To reset a file to the original file
---

# Reset a file

To reset a file to Index with latest version Git 2.23

```text
git restore abc.txt
```

With older version of git, following will work

```text
git checkout -- abc.txt
```

To do full reset a file \(reset the file back to original remote format\)

```text
git checkout @ -- abc.txt

git checkout HEAD -- abc.txt
```

[https://stackoverflow.com/questions/7147270/hard-reset-of-a-single-file](https://stackoverflow.com/questions/7147270/hard-reset-of-a-single-file)

