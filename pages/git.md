# Git

## Introduction

[Git](https://en.wikipedia.org/wiki/Git) is a version control system that allows you to track changes in software over time. The workflow usually uses several branches, which each contain their own changes, and these then have to be merged at some point. The branches allow teams to work together effectively. See the Workflow section below for more information.

## Installation

First, connect to your jail and install Git:

```
sudo pkg install git
```

Then we set the user email and user name:

```
# replace $EMAIL with the email address you used to register at GitHub
git config --global user.email "$EMAIL"
# replace $NAME with your name
git config --global user.name "$NAME"
```

## Configuration

The next steps assume you already have a GitHub account and have created a repository, you can follow [these steps](github) to do so. Afterward, you will have to create an SSH key and add it to your GitHub account. This is how to create the key:

```
# replace $EMAIL with your point park email
ssh-keygen -t ed25519 -C "$EMAIL"
Enter a file in which to save the key (/home/username/.ssh/id_ed25519): [Press enter]
Enter passphrase (empty for no passphrase): [Press enter]
Enter same passphrase again: [Press enter]
```

This generated the key. Now we need to output the key so we can copy it to GitHub:

```
cat ~/.ssh/id_ed25519.pub
```

Copy the text that is displayed after that command and enter it as an SSH key into GitHub. This can be done under Settings (available in the top right dropdown menu in the black bar) and click on SSH and GPG keys. Then create a new SSH key and paste the earlier copied text in the Key area.

## Cloning a Repository

Now we are ready to retrieve the repository from GitHub. The easiest way to do so is to go to the repository page, click on the green button that says Code, make sure you select **SSH**, and then copy the link that is displayed. Go back to your jail, make sure you are in the right directory, and run:

```
git clone $PASTE_LINK_HERE
```

where you need to replace `$PASTE_LINK_HERE` with the actual link.

## Committing Changes

After cloning a repository, we can make changes and commit them. To do so, make sure you are within the repository (e.g., you may need to do `cd repo`). The best way to make sure you are in the repo is to run the following command:

```
git status
```

which should print something like the following if no changes have been made:

```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

You can then either edit some files directly, or use FileZilla to transfer files. After that is completed, run `git status` again to make sure the files were actually changed. After confirming, you can run the following command to add files to the commit:

```
git add $FILENAME
```

where you need to replace `$FILENAME` with an actual filename that changes (e.g., see the `git status` output). After adding the files, you will need to commit them:

```
git commit -m "some message"
```

Finally, you need to push the changes for them to show up on GitHub:

```
git push
```

Note that changes are committed to the main branch by default. You can (and should) change this behavior, see the next section for details.

## Workflow

Normally when working in a team, you would not commit changes directly to the main branch but work on your own branch first, and then create a pull request to merge those changes into main. So first, we create a new branch to develop a new feature. Make sure you are somewhere inside the directory under git control, there should be no uncommitted changes, and you are on the main branch, then run:

```
git checkout -b new_feature_branch
```

This creates the new branch with as base the main branch but now you can make your changes without affecting main. Make sure to use a more descriptive name than `new_feature_branch`, as that's just an example. Follow the steps in the previous section to commit changes to `new_feature_branch`. After you are done, make sure to push the changes to GitHub.

### Creating a Pull Request

The final step is to create a pull request to merge the changes that were made in `new_feature_branch` back to main. In GitHub on the main page of the repository, select `new_feature_branch` from the drop down. Then click on the New pull request button right next to it, and on the next page click on New pull request once again (the green button).

At this point, the pull request is usually reviewed by the appropriate people. Note that under Files changed you can see the differences in a very nice way. Once everyone is onboard, you can click on Merge pull request to do the actual merge.

### Pulling in Changes from Master

One of the issues with the described workflow is while you are working on your branch, the main branch could updated by someone else. Therefore, you should pull the changes from main occasionally by running:

```
git pull origin main
```

Occasionally, there may be conflicts that you have to resolve. If that happens, you should open the files that have conflicts and look for these sections:

```
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
section a
=============================
section b
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
```

The part under section a comes from one branch, and section b comes from the other branch. You have to decide what to keep and what to remove, which is usually clear from the context. At the end, no >>>>, =====, or <<<< should be left in the file. Then do:

```
git add $CONFLICT_FILE
```

where you need to replace `$CONFLICT_FILE` with the actual filename. Then do a git commit and git push. That should do the trick. Note that this strategy also works when a pull request cannot be merged because of conflicts.
