---
title: Changing remote source in git from https to ssh
date: 2019-07-28 22:40:41
tags: [git]
---
WIP

Most of the time when trying to develop some code I want to link the project to Github. The basic way of doing this is to create an empty project in Github and then use `git remote` to add this to the project. By default the way to do this is to use HTTPS but this starts to become a pain as every time you want to commit changes to Github you need to enter your Github username and password (which for me means having to go to my password safe to get the password each time). So the better way of doing this to to link to Github via SSH instead of HTTPS. If you have a keyring installed on you system then you need to enter the relevant passphrase just once each time you log into the system and then you can commit as may times as you want (or need) without having to enter any authentication details.

Now Github does provide an article on how to do this at https://help.github.com/en/articles/changing-a-remotes-url under the section called 'Switching remote URLs from HTTPS to SSH' but it is missing some keys bits of info so here below is my step by step guide on how to do this.

Step 1 - Change from connecting via HTTPS to SSH
* Check that you have a remote repo linked to the project by running `git remote -v`. You should get output looking something like this (as per the Github guide):
```
$ git remote -v
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)
```
* If you see two addresses starting `https://` then you are currently using HTTPS to push to Github.
* To change this to SSH type the following:
```
$ git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

tbc
