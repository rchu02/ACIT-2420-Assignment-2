# ACIT-2420-Assignment-2

## Table of Contents
- [Introduction](#introduction)
- [Project 1](#project-1)
- [Project 2](#project-2)

## Introduction

This is assignment 2 for ACIT 2420 that is to create two scripts, one for installing packages and setting up a new system, and the other script to create a new user.

To get started you must get the files and move them into the proper path.

First run the command in your home directory to get the files:
```
git clone https://github.com/rchu02/ACIT-2420-Assignment-2.git
```
Then move the the directories of project1 and project2 to your home directory, by using the commands:
```
mv ACIT-2420-Assignment-2/project1 ~
```
```
mv ACIT-2420-Assignment-2/project1 ~
```

Now get permissions to execute the scripts, run the command
```
sudo chmod -R +x project1
```
and 
```
sudo chmod -R +x project2
```
You are now done setting up!

## Project 1

For Project 1, you will be able to download a list of packages that you can configure and you will be able to download some files that will help streamline the setup process, mainly making symbolic links to necessary files.

First go into the project1 directory by running
```
cd project1
```
### Download packages
 To download the packages run the command:
```
sudo ./setup -p
```
It will ask for confirmation twice on the packages that are going to install in your system.

If you wish to change or add more packages in your system with this command, then enter the `packages.txt` file and add or subtract what you wish.

### Download files and make symbolic links
To run this part, run the command:
```
./setup -c
```
and everything will be setup properly. There will be a `startup` directory created that contains files for starting a new system. In addition there will be symbolic links:
- From the `~/bin` files ->  `/project1/startup/bin` files 
- From `~/.config` files ->  `/project1/startup/config` files 
- From `/project1/startup/home/bashrc` -> `~/.bashrc` 

For the `~/bin` directory, you can confirm this by running 
```
ls -la ~/bin
```
 For the `~/.config` directory, you can confirm this by running
```
ls -la ~/.config
```
For the `~/project1/startup/home/bashrc` directory, you can confirm this by running
```
ls -la project1/startup/home/bashrc 
```
You can also run both of the options together like 
```
sudo ./setup -pc
```

## Project 2
This part will allow you to add a new user to the system.

To run the script with default settings, run 
```
sudo ./plususer <username> 
```
Where the `<username>` is what you want to name your user.

The default settings are as follows:
- Home Directory: `/home/<username>`
- Shell: `/bin/bash`
- GECOS: Empty
- Groups: User will not be added to any groups

If you wish to customize any of these options, please have a look at all the options. 

When creating a new user, the script will create the home directory and all the `/etc/skel` files inside of the home directory. In addition it will also set all the permissions to their default perms. Lastly, it will ask for a password for the user.

### Options
- `-s <shell>`: If you want to make a custom shell for your new user. Example for custom shell for `/usr/bin/bash`:
```
sudo ./plususer user1 -s /usr/bin/bash
```
- `-d <home directory>`: If you want to make a custom home directory for your new user. Example for custom home directory for `/home/notuser1`
```
sudo ./plususer user1 -d /home/notuser1
```
- `-c "<comment>"`: If you want to add GECOS or the real name inside the new user's information. Example for comment for `"Arch lover"`
```
sudo ./plususer user1 -c "Arch lover"
```
- `-g "<groups>"`: If you want to add the new user in some groups. Put the groups in quotations and separate each group with a space. Will let the user know if one of the groups doesn't exists. Example for groups for `"arch root nobody"`
```
sudo ./plususer user1 -g "arch root nobody"
```
- `-h`: For further information and help use this command with or without a user. Either
```
sudo ./plususer user1 -h
```
or
```
./plususer -h
```
- Finally, you can also run any of the options at the same time like this:
```
sudo ./plususer user1 -s /usr/bin/bash -d /home/notuser1 -c "Arch lover" -g "arch root nobody"
```
or 
```
sudo ./plususer user1 -g "arch root nobody" -d /home/notuser1
```
### Confirmation
To confirm if your script ran, you can check the information on users and groups. Run
```
grep -iw <username> /etc/passwd
```
to see information on your new user and 
```
grep -i <username> /etc/group
```
to see information on the groups that the user is in.