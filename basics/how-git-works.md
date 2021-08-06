---
description: From developers point of view
---

# How Git Works

## Git Architecture

The whole concept of version control is to let multiple developers work on a single project. So there is a git central system \(git remote repository. Few such git servers are github, gitlab,etc\) where project source resides. And each developer will push their code changes from their computer to the git remote repository and also pull other developer code \(code pushed by other developers\) from remote repository to their  computers.

{% hint style="info" %}
 To connect from your computer to this remote repository you need [git client](https://github.com/git-guides/install-git) on your computer. There are few GUI clients aswell, but we will only cover the command line CLI here. You can install [git client from here](https://github.com/git-guides/install-git).
{% endhint %}

## Git Local System Architecture

**This is the most important step in understanding git.**

Most of the other version controls before Git worked as follows.

As a developer you will write code using code editors like Visual Studio Code, Eclipse.. save those files\(.js .java .html etc files\)  in your local computer and then push those to the remote repository. This is true for git also but there are couple more steps with git.

Unlike other version control systems Git divides the code in your computer into 3 layers. 

Working Directory    ---&gt;    Staging   ---&gt;   Local Repository

You can think of these as 3 different folders. Working Directory is the only thing which is accisible to edit with your editors like Visual Studio Code or notepad etc. You can think of 'Staging' and 'Local Repository' are hidden folders which will reside in .git folder at the project root. 

When you clone a remote git repository, that remote code is copied into your 'Local Repository' and also it is copied into your 'Working Directory' \(Staging is empty for freshly cloned projects\).

Note that your your local repository is not the same as your working directory. So when you write code and save, it will be saved in your working directory. Then from that working directory you will move these files into 'Staging' layer. From staging layer you will move to 'Local Repository'. Remember all these changes happen only inside your computer, code is not moved to remote git repository.

#### Why do we need this multiple layers ?

Git maintains history of all your code push. All files you changed for a particular bug fix or a new feature will stay in the git history as packages. Each of the package will have 



There are few advantages of having them in layers. Imagine while you are working on a new feature you found a minor bug. After implementing the new feature and fixing the bug, its better to have two commits in the git history.

 When you are putting all these features in the git history how do you want to see them? you can push all feature changes and bug as one package. This way you can see all that day changes as one package in git history \(denoted by a name\). Or you can package all new feature changes as one and all bug fix related things as another package. With this approach you will see git history having two boxes, one with new features and other with bug fixes.

----- Diagram ----



You want to put all the features 

So you can push the feature changes as one package and bug fix as another package of files and push it to git history.

```
$ git add *
```



