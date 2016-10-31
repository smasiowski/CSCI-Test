# GithubTutorial
==================================================
Git and Github have many features, but the intent of this tutorial exercise is to show you how to add repositories (think projects) to your account and add to/edit those repositories from your computers. This tutorial will also show you how to create a repository in Github from an exisiting project on your local filesystem.


## Downloading Git
1. Follow this link and choose your OS https://git-scm.com/downloads
2. After download completes, go through the install 
   * Windows users wanting to use command line should install GitBash (it should be automatically selected) and read the rest of the install instructions carefully; it really comes down to how you want your environment set up; if you would like help understanding this portion find a git guy with a windows set up


## Creating Repositories in Github
1. In the repository section of your profile, click 'New'. This will bring up a form for you to name the repository, chose if it is to be public or private, and whether or not to generate a README file.
2. Once you have created the repository, you will see it listed as one of your available repositories. Click on the title. You should see a 'Clone or download' button. Clicking it should allow you to copy the link. An example would be: 'git@github.com:kabriggs991/GithubTutorial.git'
3. On your computer in a terminal, navigate to where you want your project to reside. An example would be '/home/kbriggs/cofc/csci115/projects/' (The command 'cd' is usually used to navigate your filesystem in a terminal).
4. Finally type 'git clone yourCopiedGitCommandFromGithub' (in my example: git clone git@github.com:kabriggs991/GithubTutorial.git)
5. You should see your repository files (if you had any) download into your computer. To check, navigate into the folder (my example: cd GithubTutorial). Type 'git status' and you should see 'Your branch is up-to-date with 'origin/master'.nothing to commit, working directory clean'
6. You can now add, edit, etc files. You can create folders and edit as you normally would. The difference now is that you can commit these changes to your local Git server and push those commits to Github. Recall the class demo. There are four commands you really need to familiarize yourself with. 'git status', 'git add filename', 'git commit -m "Type a good commit message"', and 'git push origin master'. These are not nearly all the things you can do with git, but it's a good start. These four commands will push changes you have to a file into your Github account. 

## Adding your existing project to Github
1. You probably already have a project you want to get into Github. In that case, still follow the steps above in creating a repository in Github, but ensure that you use the correct project name.
1.  Open a terminal and navigate to where your project files are. Most of you have a project folder and inside that folder is where you have index.html and maybe a css folder. Navigate to that point and type 'git init'. This will create a git repository for your project.
2. Typing 'git status' should reveal all the files in your project as needing to be added. Type 'git add .' to add all of them.
3. Type 'git commit -m "Initial commit"' to commit to your local git server.
4. Type 'git remote add linkFromGithub'. THIS IS WHERE YOU PASTE THE LINK FROM GITHUB
5. Type 'git push origin master' 
6. Your existing project is now under source control with git and stored in Github. This is a very useful and powerful tool. When you get a section of your project working, you can now push the changes to Github. When you continue to work on your project and change things, you can code with confidence that you will not lose any code if your new changes are not going well. You can simply 'rollback' to a previous commit if you need to. 

## Creating ssh keys
1. To make your life easier, providing an ssh key to Github will allow you to push changes to origin (the Github cloud) without having to authenticate with a username/password each time. Without going into complicated detail, you basically are going to create a public and private ssh key. These get stored in a .ssh folder in your USER_HOME folder. For example my username is kbriggs, so my .ssh keys are stored in '/home/kbriggs/.ssh'. This is usually operating system specific. To generate your ssh keys, open up a terminal shell and type 'ssh-keygen'. The program will prompt you a name for your key file. Hitting 'Enter' for the default 'USER_HOME/.ssh/id_rsa' should work fine. After pressing 'Enter', the program will ask you for a passphrase. The word you type will be used to generate a key. Do not worry if the word does not appear as you type, this is on purpose for security reasons. 
2. You should now be able to see that you have two files in your .ssh folder called 'id_rsa' and 'id_rsa.pub'. 'id_rsa' is your private key. Do not give this file out to anyone. 'id_rsa.pub' is your public key that you give out. Open this file and copy all of the contents in it.
3. Log into Github and click on your profile dropdown menu in the top right-hand corner. Next click 'Settings'. You should see different profile setting along the left-hand side. Click on 'SSH and GPG Keys'. Click on 'New SSH Key'. Place a name in the 'Title' section and paste the contents of your 'id_rsa.pub' file in the 'Key' section. Finally click the 'Add SSH Key' button.
4. Now you will be able to 'ssh' links rather than 'https' when dealing with repositories.

## Extra Resources
- Here is a guide for git called [git - the simple guide](http://rogerdudler.github.io/git-guide/)
- Another good resource for git is the Atlassian [site](https://www.atlassian.com/git/tutorials/); Atlassian created bitbucket, an alternative to github, so these tutorials reference bitbucket, but git will be the same **Need better wording here
- Some extra fun stuff for markdown: [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), [online md editor](https://jbt.github.io/markdown-editor) for those that like visualization