---
description: What is brancing?
---

# Git Branching

Imaging you released a web app project for production, where your customers are using it. And you started working on a next feature enhancement. Now lets say a user found a major bug in the production app, which needed to be urgently fixed. You have to keep aside the feature enhancement code and start immediately on the production bug.  This is called branching, git branching allows you to work in parallel on multiple features or branhes of the same project. 

The work-in-progress implemented feature code is a separate branch and the production code is a separate branch. You can quickly jump to production code fix that critical bug, push it to production branch and then jump back to the feature enhancment you were working on. When you started working on your feature enhancment code, you made few changes to the files, added new files etc. But the moment when you switch to production branch, all those modified files and newly added files in your **working directory** are kept aside and the working directory is replaced with the production code\( the newly created files for that feature are not any more visbile\). Your current code is the production branch code, the code you kept aside is feature-branch. Git allows you to work on multiple branches, you can name the branches as you like.

{% hint style="info" %}
If you create a branch in your computer, it wont be automatically pushed to the remote branch. You have to push that new branch to the remote git repository.
{% endhint %}

Its very easy to create a new branch with git.

```text
git branch new-branch-name


```

{% hint style="info" %}
Very important: When you create a new branch like above, your working-directory is not automatically switched to the new branch. For that you have to say

```
git checkout new-branch-name
```
{% endhint %}

Instead you can create a new branch with -b switch.

```text
git checkout -b new-branch-name
```



{% hint style="info" %}
Generally for each feature you will create a separate branch and start working on it.

And before you push your code to remote branch, you will pull the latest changes from the remote + merge changes\(if there are any changes by other devs\) and then push to remote.
{% endhint %}

#### Scenario-1 : Lets take a scenario of how you will work on a short feature \(mostly as a individul dev\).

Imagine this scenario, you are on main branch \( previously use to be called master branch\). You started working on a feature called 'password-check'.  This is how you will work.

Step-1: You will pull the latest main/master branch code from the remote repository.

```text
git pull 
```

Step-2: Create a new branch from the main/master, lets call this new branch password-check

```text
git checkout -b password-check
```

This above command will create a new branch called 'password-check' which is a copy of the current main/master branch.

Now you will open your IDE like Visual Studio Code and start working on the password checking feature on the password-check branch. **All your code changes are in the password-check branch.** 

You will add the modified files or newly added files \(git add\) and git commit those changes to the password-check branch.

Once you make all the changes required for passowrd-checking and commited them to the password-check branch. You will pull the latest main/master code from the remote repository \(this is required because other devs may have pushed some changes \).

```text
git checkout main
```

With the above command your working directory is switched to main branch. All your password-check branch code is saved \(assuming you commited that code\) and it is replaced with the main branch code. You wont see your password-check files in main branch, because they are in different branch, you have to merge the password-check branch changes to the main branch with the following command.

```text
git merge password-check
```

 Now main branch is also have the password-check branch code. At this point you will generally push your changes to remote git\(but you need to do a git pull before you push to get other devs code\). 

Once all these steps are done, you don't require the password-check branch, which you can delete with the command.

```text
git branch -d password-check
```

The above working style is typically used with individual developer. But when you working in a organization with a team of devs, you will typically create a pull requests \(please check the next chapter for Pull Requests\).

