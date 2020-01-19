---
title: Adding an existing Dev project to Github
thumbnail: /gallery/Github_Case_Study_Header_New.jpg
date: 2020-01-14 05:03:29
tags: [howto]
---
The steps you need to take to enable Git on a existing project and then add it to a Git repository on Github.

...

Partial:

1) Log into GitHub and create an empty Repo (ie. Do not tick the `Initialize this repository with a README` option)
2) In the root folder of the Dev project in question run `git init` and then `git add .`
3) Then run git commit (eg. `git commit -m 'First Commit'`)
4) Now link the remote repo on GitHub to the local folder with the dev project in it using `git remote add origin git@github.com:[your GitHub username]/[Repo name].git` or the HTTPS version which is ...
5) Now push the content on the local folder to GitHub with `git push -u origin master`
