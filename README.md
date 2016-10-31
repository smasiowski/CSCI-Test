# GithubTutorial
==================================================

Git and Github have many features, but the intent of this tutorial exercise is to show you how to add repositories (think projects) to your account and add to/edit those repositories from your computers. This tutorial will also show you how to create a repository in Github from an exisiting project on your local filesystem.


## Downloading Git
1. Follow this link and choose your OS https://git-scm.com/downloads
2. After download completes, go through the install 
   * Windows users wanting to use command line should install GitBash (it should be automatically selected) and read the rest of the install instructions carefully; it really comes down to how you want your environment set up; if you would like help understanding this portion find a git guy with a windows set up


## Creating Repositories in Github
1. Navigate to your Github profile page
2. Click on the `Repositories` tab 
3. In this page near the top is a green button labeled `New`. Click on that button to create a new repo
4. Name your new repo `CSCI-Test`. 
   * Add a description for the repo if you would like; this is just to help you know the purpose of the repo
   * Choose `Public` for the repo type; `Private` repos you have to pay for
   * Do not check the box for adding a README file
   * Optionally you can create a .gitignore file and a license file, for our purposes we will not be needing these
5. Your new repo is created

## Adding to Our New Repository
We are going to cheat a bit here. There are so many possiblities with forking, git cloning, git init, etc. We will begin with baby steps. This process will be most akin to downloading or cloning somebody else's repo and uploading it into your own without touching the command line.

1. In the new repo that we have created you should see a button near the bottom that says `Import Code`. Click on that.
2. The next page is asking for a different source control repository such as SVN. We are actually going to paste in this github repo: https://github.com/kabriggs991/GithubTutorial.git
3. After this you now have a repo called `CSCI-Test` that is identical to this repo, GithubTutorial

## What Now?
We have created a copy and now have a repo, what can we do? To keep things simple we will start off with some simple command line items that every git user needs. Take note of your operating system for this, mac and linux users should be able to follow this perfectly with no issues; windows users it could depend based on how your system is set up. If you are using Gitbash you should be fine.

1. Open up a terminal (Gitbash for windows). These usually start out at the root of a user directory unless you have changed this.
2. Change your directory to the Desktop by typing `cd ~/Desktop`
3. We are now going to clone the repo we made which is remote to our local desktop; type `git clone repo-address`
4. Now change to your new cloned directory by typing `cd CSCI-Test`
5. If you type `ls` you will list the contents of the directory. The output should be just a README.md file; typing `ls -la` though will list the containing directories and hidden files, so you will see a file called `.git`. Now we know for sure that we are working with a git directory
6. If we now type `git` we should see basic git commands. It might seem like a lot at first, and it might be difficult to understand at first if you aren't used to command line, but it will be helpful in the future. 
7. Let's type `git status`. You should receive a message saying that everything is up to date with the remote branch (unless you have deviated from this walkthrough)
8. Let's start off by making a .gitignore file. We may not need it now, but at least we will have a template if we need it in the future. The .gitignore file is basically a list of files that you do not want to include in your repository. Type `touch .gitignore`
9. Type in `git status` now and we should see prompts telling us a file called .gitignore is in our local repo, which differs from our remote
   * Note for mac users, you may notice a file called .DS_Store in there as well, and it could have possibly popped up in the first git status you typed. This file is a mac specific folder structure file; this is also a great way to test your .gitignore file on macs, just type `open .gitignore` from the terminal and you should have the default text editor open with the .gitginore file. Just type in .DS_Store into your editor and save the file. Typing into the terminal `git status` now should just show the .gitignore file (need to test this as I am writing from linux at the moment, not mac, but I believe the .gitignore should ignore the store file on the local side without being added to the commit)
10. Now type in `git add .` or `git add .gitignore`. The difference between these commands is that the first adds every file you have to commit (we only have one) and the second adds a file with that name to the commit. `git add .` is good when commiting large amounts of files such as initializing a start up project, and `git add <filename>` is good when you want to do things like create a specific commit to roll back to if you think it might mess up a project or you want detailed messages for every file you are adding to the commit. You will eventually find out your workflow and become comfortable doing either and figure out which is best for the current situation.
11. Type in `git status` once more. You should now see a similar message but now it is saying a new file, .gitignore is going to be committed. 
12. Finally we will type in `git commit -m "adding .gitignore file"`. This statement `git commit` allows us to commit the file and the `-m` allows us to create the commit message we want right from the terminal. In this case we say we are "adding .gitignore file" but this message can be anything you want it to be, just remember it is there to help you figure out what changes you made to the project.
13. One more `git status` will show us we are ahead of our remote branch. Let's finally push it up. Type `git push origin master` and go check out your repo, you may have to refresh the page if you haven't navigated away from it yet, but there should now be a .gitignore file in there for you.

These same basic steps can be followed to update your README.md file and add new files. 

## Creating ssh keys
1. To make your life easier, providing an ssh key to Github will allow you to push changes to origin (the Github cloud) without having to authenticate with a username/password each time. Without going into complicated detail, you basically are going to create a public and private ssh key. These get stored in a .ssh folder in your USER_HOME folder. For example my username is kbriggs, so my .ssh keys are stored in '/home/kbriggs/.ssh'. This is usually operating system specific. To generate your ssh keys, open up a terminal shell and type 'ssh-keygen'. The program will prompt you a name for your key file. Hitting 'Enter' for the default 'USER_HOME/.ssh/id_rsa' should work fine. After pressing 'Enter', the program will ask you for a passphrase. The word you type will be used to generate a key. Do not worry if the word does not appear as you type, this is on purpose for security reasons. 
2. You should now be able to see that you have two files in your .ssh folder called 'id_rsa' and 'id_rsa.pub'. 'id_rsa' is your private key. Do not give this file out to anyone. 'id_rsa.pub' is your public key that you give out. Open this file and copy all of the contents in it.
3. Log into Github and click on your profile dropdown menu in the top right-hand corner. Next click 'Settings'. You should see different profile setting along the left-hand side. Click on 'SSH and GPG Keys'. Click on 'New SSH Key'. Place a name in the 'Title' section and paste the contents of your 'id_rsa.pub' file in the 'Key' section. Finally click the 'Add SSH Key' button.
4. Now you will be able to 'ssh' links rather than 'https' when dealing with repositories.

## Extra Resources
- Here is a guide for git called [git - the simple guide](http://rogerdudler.github.io/git-guide/)
- Another good resource for git is the Atlassian [site](https://www.atlassian.com/git/tutorials/); Atlassian created bitbucket, an alternative to github, so these tutorials reference bitbucket, but git will be the same **Need better wording here
- Some extra fun stuff for markdown: [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), [online md editor](https://jbt.github.io/markdown-editor) for those that like visualization

## TO-DO
* Add info for branches
* Add info about workflow
* Add info on pull requests