# Git for Beginners

## What is Git?

Git is a **Version Control System** which helps you collaborate and work with other programmers on projects easily. So now the question is what is a Version Control System? Version Control is a system that records all the changes you do to your files and logs them. This enables you to go back to them and start working on your files from that point. It's basically like time travel. If while working on your files you realise that you have done something majorly wrong but can't sit and undo every change. The best option for you is to ask your version control system to simply go back to the instance from where you want to start again.
There is a slight difference between Git and other version control systems. Usually VCSs, store all the files again when you ask it to. But Git instead of saving all the files only saves the files in which changes have been made. To be efficient, if files have not changed, Git doesn’t store the file again, just a link to the previous identical file it has already stored. 

Checkout this [link](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for installing Git.

## Configuring Git
The first thing you should do after installing Git is configuiring it with your email id and username. This is a necessary step specially when you're collaborating. Everytime you commit (save the state of you files), Git will ask you for your identity so that it is clearly visible to other collaborators who made the changes in a particular commit. To this is you'll have to run the following two commands:

`git config --global user.name "yourcoolusername"`

`git config --global user.email "youremail@example.com"`

To check if you have done everything correct till now, run

`git config --list`

## Initialising a Repository
For this you'll also like a basic level knowledge of command line tools. Here's a nice [cheatsheet](http://learntocodewith.me/command-line/unix-command-cheat-sheet/) for it.
So once you `cd` into your repository you have to run

`git init`

## Cloning an Exisiting Repository
If you have already have a repository hosted on Github, to copy it locally and make changes to it all you have to do this run

`git clone https://github.com/TheFlash98/Git-Tutorial.git`

This particular command will be clone the Git-Tutorial repository to your computer locally. As you can see the command, I've written `git clone` followed by a link. This link is unique to every repository. **Note**: This is the only step except installing for which you need an internet connection. Everything else can be simple done offline.
You can see the link to this repository below the Green button which reads "Clone or Download"

![alt-text](https://github.com/TheFlash98/Git-Tutorial/blob/master/Getting-link.png)

## Code Time!
#### Commiting
Now that you have your repository locally with you it's time for you make changes and build your project. So now comes the most major part and the actually reason as why we used Git(Version Control) at all. After you complete something substantial like fixing a bug or adding a new feature you should save the instance of your files aka commit. To see the changes you have made since the last commit run

`git status`

Now this command might show you file names in two different colours. The files shown in green are the ones that have been staged, that is commiting now will commit the changes the made to them. The other category of files shown in red colour are the untracked files. To commit these files you will have to first stage them. To stage them you run

`git add filename.extension`

or if you want to just stage all the files, simply do one of these

`git add .`
`git add -A`
`git add -u`

`git add -A` is the safest one as it adds all stages all changes, including the new files you've added, the ones you've modified, as well as the ones you've deleted.
`git add .` does not stage the deleted files, while `git add -u` doesn't stage the new files.


If you run `git status` now, all the files would be stages and ready to be commited. To commit run

`git commit -m "Commit message"`

The Commit Message should be short and sweet such that someone reading it gets an idea as to what you have done. To see a record of all the commits you have made run

`git log`

Let's say you are working on your project and have made 5 commits. But after the 5th commit you realise that you(or someone else) did someting wrong in the second commit and now you have want your repository to go back to that commit. Meaning you want your repository to be the way it was in that commit. Every commit has it's own commit id which is a long hexadeimal number eg cffb604020ec0d9bdd9b5b23de14fcac40a661be. Now, to go back to this commit you have to run

`git checkout cffb604020ec0d9bdd9b5b23de14fcac40a661be`

What this command does is that it will create a new branch, I have spoken about branches briefly below. Think of this something like time travel. There is one time line but you realised you have screwed this time line and want to travel back in time to fix things. So you travel back and make your changes the result of which is that you end up creating a new timeline(branch).

#### Pushing 
So by now you know how to make a copy of your repository locally and how to make changes. So now what you have to do is **push** these changes to the repository you have online so that others can see what you've done and keep up. To do these we'll need to talk a little about two things:
- **Remote:** A remote is like a connector between your local repository and the online one. By default if you clone a repository a remote called origin is made. You can see the list of remotes by doing `git remote`
- **Branches:** Branching means you diverge from the main line of development and continue to do work without messing with that main line. There is always a default branch called master provided my git. To read up more about branches and their use, click [here](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell).

To push your changes online you will have to run 

`git push origin master`

Basically `git push` followed by the local remote name and the branch you want to push to.

#### Pulling
You will probably have more than one person working on your repository. All of them will make their changes locally and push them to the the online repository. To build on their changes you will have to get those changes locally. Cloning the repository again would be foolish. It's like uninstalling and reintalling an app when it gets updates. Hence, git provides you with a very useful command. 

`git pull origin master`

Basically `git pull` followed by the local remote name and the branch you want to pull from.

#### Merge Conflicts
This is the most painful thing about collaborating with others. Usually when you merge git smartly merges everything and you don't have to bother. But in some cases it occurs. For example if two people changed the same lines in the same file, or if one person decided to delete it while the other person decided to modify it, Git simply cannot know what is correct. Git will then mark the file as having a conflict - which you'll have to solve before you can continue your work. A merge conflict looks something like 
```
<<<<<<< HEAD
The content of the while you're trying to merge
=======
The content that you have written
<<<<<<< commit id in which you wrote the conflicting commit
```

I think these basics are enough for you to build a project with your pals. However there are various other features which github and git offer. You can check out the following links.
1. [http://gitreal.codeschool.com/levels/1](http://gitreal.codeschool.com/levels/1)
2. [http://learngitbranching.js.org/](http://learngitbranching.js.org/)
3. [https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2)
