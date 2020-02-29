---
title: Notes on adding themes to Hexo
date: 2019-07-28 22:40:09
tags: [hexo]
---
When looking at the instructions on how to install some of the themes for Hexo that can be found at [https://hexo.io/themes/](https://hexo.io/themes/) the one's I've tried to install so far have instructions telling you to use git clone to download them into a sub folder of the themes folder (into a folder that is the name of the theme).

This causes an issue when it comes to then publishing to site to Github as a `git add .` returns the following warning:

{% codeblock %}
warning: adding embedded git repository: themes/icarus
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint: 
hint: 	git submodule add <url> themes/icarus
hint: 
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint: 
hint: 	git rm --cached themes/icarus
hint: 
hint: See "git help submodule" for more information.
{% endcodeblock %}

The problem here is if you do add it as a submodule then it appears that you cannot configure the theme for you own site as it appears that the changes need to be made to the main theme repo and not your cloned version! (I might have this wrong but anecdotally this appears to be the case).

The only way I have found around this is to do the following:
* Run git clone to a folder that is outside of the Hexo folder structure on your local system.
* manually create the folder for the theme in Hexo's themes folder
* copy all content from the cloned folder to the manually created folder EXCEPT the .git and .github folders.
 
Another issue I have come across with one theme was that in the .gitignore file for the theme there was an entry for the theme's _config.yml file and this was causing the deployment to Netlify to fail (this would run fine locally using http://localhost:4000/ but gave the error `failed during stage 'building site': Deploy directory 'public/' does not exist`). From what I can tell this was due to the fact that Netlify was trying to create it's own _config.yml file which I'm guess was missing most of the config needed for the theme to work.

Had to edit the .gitignore file and remove that entry for the deployment to work.
