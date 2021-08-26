---
description: A simple tutorial for understanding Git basics. Work in progress...
---

# How Git Works

## So, What is Git? 

Git is a Source Control \(sometimes it is also called Version Control\). Source control is the process/practice of tracking and managing changes to software code. Source control is specifically for source code, Version control is versioning all types of data not only for source code, ex:-  versioning images, documents, binary data etc. For deeper understanding check this [BitBucket tutorial](https://www.atlassian.com/git/tutorials/what-is-version-control).

Another explaination from [AWS](https://aws.amazon.com/devops/source-control/git/)  "Git is an open-source distributed source code management system. Git allows you to create a copy of your repository known as a branch. Using this branch, you can then work on your code independently from the stable version of your codebase. Once you are ready with your changes, you can store them as a set of differences, known as a commit. You can pull in commits from other contributors to your repository, push your commits to others, and merge your commits back into the main version of the repository".

## Git Architecture

The whole concept of version control is to let multiple developers work on a single project. So there is a git central system \(git remote repository\(repo\) github, gitlab,etc\) where project source saved. And each developer will push their code changes from their computer to the git remote repository and also pull other developer code \(code pushed by other developers\) from remote repository to their  computers.

{% hint style="info" %}
 To connect from your computer to this remote repository you need [git client](https://github.com/git-guides/install-git) on your computer. There are few GUI clients aswell, but we will only cover the command line CLI here. You can install [git client from here](https://github.com/git-guides/install-git).
{% endhint %}

## Git Local System Architecture

**This is the most important step in understanding git.**

Most of the other version controls before Git worked as follows.

As a developer you will write code using code editors like Visual Studio Code, Eclipse.. save those files\(.js .py .java .html etc files\)  in your local computer and then push those to the remote repository. This is true for git also but there are couple more steps with git.

Unlike other version control systems Git structures local data/files into 3 layers. 

Working Directory  ---&gt;    Staging\(or Index\)   ---&gt;   Local Repository  =====&gt; Remote Repository

{% hint style="info" %}
Your 'Local Repository' is a full git repository\(just like your server git repository\) and this is only for your machine. With git you will first commit your code to your local repository and then push these changes from your local repository to the remote repository.
{% endhint %}

{% hint style="info" %}
Working directory is the file system where you edit files using Visual Studio Code/Notepad or other IDE's.
{% endhint %}

![](.gitbook/assets/main-architecture4.png)



For visualization you can think of these as 3 different folders. Working Directory is the only thing which is accisible to edit with your editors like Visual Studio Code or notepad etc. Staging \(also called index\) is another folder and 'Local Repository' is yet another folder\(Staging and 'Local Repository' are hidden\).  

Now lets say you implemented a new feature called 'image compress' and for that you modified two files for this lets say ImageComp.java, Util.java. To send your code to remote git reposity you need to do the following. 

#### Step -1:  You will select these two files and add it to staging area. 

{% hint style="info" %}
**Staging is like a basket \(Imagine you are going to shopping mall where you pick different items and put all of them into your shopping cart\).** 
{% endhint %}

```
# And this is how you to add ImageComp.java, Util.java files to 'Staging Area'

$ git add ImageComp.java Util.java
```

#### Step-2:  Then you move your code from **Staging Area** to the **Local Repository** \(Remember you are moving your code to the to the local repository not to the remote repository\).

And while you are moving your code to local repository you can write a note about what these changes are for. For example for the above commit you can say "code for image compression". Later when you are looking at git history and try to understand what these commits are for, this commit label helps you and other devs to quickly understand these changes. Its a good practice to give a breif and highlevel description for each commit.

```text
# This is how you move your code from 'Staging Area' to your own 'Local Repository'
# Note:- This command not moving your code to remote git repository.

$ git commit -m "code for image compression"
```

> With this commit action both of these files are grouped together and given a label called 'code for image compression'.

Step-3: Once you label your code changes and added to the Local Repository now is the step to move that commit to the **Remote Git Repository**.

```text
# This is how you push your local code (commit) to the remote git repository

$ git push origin master
```

When you clone a remote git repository, that remote code is copied into your 'Local Repository' and also it is copied into your 'Working Directory' \(Staging is empty for freshly cloned projects\).

Note that your your local repository is not the same as your working directory. So when you write code and save, it will be saved in your working directory. Then from that working directory you will move these files into 'Staging' layer. From staging layer you will move to 'Local Repository'. Remember all these changes happen only inside your computer, code is not moved to remote git repository.

#### Why do we need this multiple layers ?

Git maintains history of code pushed. You can imagine all files you changed for a particular bug fix or a new feature will stay in the git history as package. Each of the package will have a \(commit id\), you can also name them as a TAG.

There are few advantages of having them in layers. Imagine while you are working on a new feature you found a minor bug. After implementing the new feature and fixing the bug, its better to have two commits in the git history.

 When you are putting all these features in the git history how do you want to see them? you can push all feature changes and bug as one package. This way you can see all that day changes as one package in git history \(denoted by a name\). Or you can package all new feature changes as one and all bug fix related things as another package. With this approach you will see git history having two boxes, one with new features and other with bug fixes.

----- Diagram ----







