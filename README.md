---
description: A simple tutorial for understanding Git basics.
---

# A Simple Git Help

## So, What is Git? 

Git is a Source Control \(sometimes it is also called Version Control\). Source control is the process/practice of tracking and managing changes to software code. Source control is specifically for source code, whereas Version control is for versioning all types of data, not just for source code, ex:- versioning images, documents, binary data etc. For better understanding check this [BitBucket tutorial](https://www.atlassian.com/git/tutorials/what-is-version-control).

Another explanation from[ AWS](https://aws.amazon.com/devops/source-control/git/) "Git is an open-source distributed source code management system. Git allows you to create a copy of your repository known as a branch. Using this branch, you can then work on your code independently from the stable version of your codebase. Once you are ready with your changes, you can store them as a set of differences, known as a commit. You can pull in commits from other contributors to your repository, push your commits to others, and merge your commits back into the main version of the repository".

The whole concept of version control is to let multiple developers work on a single project. So there is a git central system \(git remote repository ex:- github, gitlab, etc\) where the project source is stored. And each developer will move their code from their local computer to the remote git repository \(git server\) and also pull code pushed by other developers from remote repository to their computers.

{% hint style="info" %}
 To connect from your computer to this remote repository you will  need[ git client](https://github.com/git-guides/install-git) on your computer. There are few GUI clients as well, but we will only cover the command line CLI here. You can install [git client from here](https://github.com/git-guides/install-git).
{% endhint %}

## Git System Architecture

**This is the most important step in understanding git.**

Most of the other version controls before Git worked as follows.

As a developer you will write code using code editors like Notepad, Eclipse, etc., save those files \(.js .py .java .html etc., files\) in your local computer and then move those to the remote source server. This is true for git as well but there are a couple more steps with git.

‌Unlike other version control systems Git structures data into 4 areas, the first 3 of these are on your local computer and the last "Remote Repository" resides in the remote server.  


Working Directory ---&gt;  Staging\(or Index\) ---&gt; Local Repository  =============&gt; Remote Repository

{% hint style="info" %}
Working directory is the file system where you edit files using Visual Studio Code/Notepad or other IDE's.
{% endhint %}

![](.gitbook/assets/main-architecture4.png)



To visualize, you can think of these as 3 different folders. Working Directory is the only thing which is accessible to edit with your editors like Visual Studio Code or notepad etc. Staging \(also called Index\) is another folder and 'Local Repository' is yet another folder \(Staging and 'Local Repository' are hidden\). 

Now lets say you implemented a new feature called 'image compress' and for this new feature you created/modified two files, lets say these files are ImageComp.java, Util.java. To send your code to remote git reposity you need to do the following. 

#### Step -1:  You will select these two files and add it to staging area. 

{% hint style="info" %}
**Staging is like a basket \(Imagine you are going to a shopping mall where you pick different items and put them into your shopping cart\).** 
{% endhint %}

```
# And this is how you to add ImageComp.java, Util.java files to 'Staging Area'

git add ImageComp.java Util.java
```

#### Step-2:  Then you move your code from **Staging Area** to the **Local Repository** \(Remember you are moving your code to the to the local repository not to the remote repository\).

And while you are moving your code to the local repository you can write a note about the changes. For example for the above commit you can say "code for image compression". Later when you are looking at git history and try to understand what these commits are for, this commit label helps you and other devs to quickly understand these changes. It's a good practice to give a brief and high level description for each commit.

```text
# This is how you move your code from 'Staging Area' to your own 'Local Repository'
# Note:- This command not moving your code to remote git repository.

git commit -m "code for image compression"
```

> With this commit action both of these files are grouped together and given a label called 'code for image compression'.

**Step-3: Once you label your code changes and add it to the Local Repository now is the step to move that commit to the Remote Git Repository.**

```text
# This is how you push your local code (commit) to the remote git repository

git push origin master
```

{% hint style="info" %}
I will repeat the above steps again, because you need to understand these steps well. Your local repository is not the same as your working directory. So when you write code and save, it will be saved in your working directory. Then from that working directory, you will add selected files into the 'Staging' area. From the staging area you will move your code to your 'Local Repository'. Remember at this step all these changes happen only inside your computer. Code is not moved to the remote git repository. Only when you do push action, your code is moved from your local repo to remote repo.
{% endhint %}

