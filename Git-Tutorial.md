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

