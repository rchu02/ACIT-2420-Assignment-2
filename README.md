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

## Project 2