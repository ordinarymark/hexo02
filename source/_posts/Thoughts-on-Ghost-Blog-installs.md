---
title: Thoughts on Ghost Blog installs
thumbnail: /gallery/201807_ghost-cms.jpg
date: 2020-01-21 21:57:21
tags:
- ideas
- howto
---
Thoughts on a suitable, repeatable process for installing Ghost Blog on a server, directly and not via Docker

The reason for this thought is having gone through the article at https://www.howtoforge.com/tutorial/docker-guide-deploying-ghost-blog-with-mysql-and-traefik-with-docker/ and while this was an interesting exercise, it left some of the links in the blog directing to https://localhost:2368/ which of course would not be suitable for a production site.

Possible Steps:
1. Install Node via Nodesource
2. Install Ghost CLI via NPM (after updating NPM if needed)
3. Install and configure Nginx to act as a Reverse Proxy and HTTPS termination point for a Let's Encrypt SSL cert
4. Install MySQL or simply use another MySQL server elsewhere

#### Update

OK, Have been able to resolve the issue with some of the URL's appearing as https://localhost:2368/. This was achieved by adding the `url` environment variable to the Ghost section of the docker-compose file(eg. `url: https://blah.com`). Also found that I had to change the image tag for Traefik from `traefik:latest` to `traefik:1.7` as the latest version of Traefik is now a 2.x version and this process was designed using Traefik 1.x (guess there is a difference with how each version is configured :-( ) but there isn't a Docker image for 1.x hence having to use the tag from the latest 1.x version with is currently 1.7!

Still want to look at a direct install process for comparison.

...
