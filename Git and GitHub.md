Git and GitHub



Git: is a software.

GitHub: is source to host git online.



Git: used to add check point in file. make versions of files. it have version control.



**\* Repository** :- A repository is a collection of files and directories that are stored together. it is a way to store and manage your code. A repository is like a folder on your computer, but it is more than just a folder. It can contain other files, folders, and even other repositories. You can think of a repository as a container that holds all your code.



There is a difference between a software on your system vs tracking a particular folder on your system. At any point you can run the following command to see the current state of your repository:





*git status*







 \* Your config settings :- GitHub has a lot of setting that you can change. You can change your username, email, and other settings. Whenever you checkpoint you changes, git will add some information about your such as username and email to the commit. There is a git config file that stores all the settings that you have changed. You can make settings like what editor you would like to use etc. There are some global settings and some repository specific settings.



Let's setup your email and username in this config file. I would recommend you to create an account on GitHub and then use the email and username that you have been created.





*git config --global user.email "your-email@examplel.com"*

*git config --global user.name "your Name"*





Now you can check your config settings:





*git config --list*



 



 \* Creating Repository :- Creating a repository is a process of creating a new folder on your system and initializing it as a git repository. It's just regular folder to code your project, you are just asking git to track it. To create a repository, you can use the following command:



*git status*

\*git init  :\*start tracking









CMD				DESCRIPTION



git --version			show the git version

