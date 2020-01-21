---
title: Thoughts on Ghost Blog installs
thumbnail: /gallery/201807_ghost-cms.jpg
date: 2020-01-21 21:57:21
tags:
- ideas
- howto
---
Thoughts on a suitable, repeatable process for installing Ghost Blog on a server, directly and not via Docker

The reason for this thought is having gone through the article at https://www.howtoforge.com/tutorial/docker-guide-deploying-ghost-blog-with-mysql-and-traefik-with-docker/ and while this was an interesting exercise, it left some of the links in the blog directing to the internal IP address of the docker container which of course would not be suitable for a production site.

Possible Steps:
1. Install Node via Nodesource
2. Install Ghost CLI via NPM (after updating NPM if needed)
3. Install Nginx to act as a Reverse Proxy and HTTPS termination point for a Let's Encrypt SSL cert
4. Install MySQL or simply use another MySQL server elsewhere

...
