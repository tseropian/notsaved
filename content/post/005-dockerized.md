---
author: author
date: 2016-05-27T12:07:50+01:00
published: true

tags:
- docker
- blog
- sysadmin
- https
- server-love
title: "005 : Dockerized"
type: post
---

Hi there.
Long time no see.

I've been busy but is working on getting back to writing :-)

Meanwhile I've been geeking a bit with Docker.I wanted a practical exercise so why not trying to host a website on it. This blog is now served from a Docker container on a Digital Ocean VPS. I've also deployed a Let's Encrypt certificate. This blog is now full HTTPS Yay :)

Links and notes on the setup:

- [Setting up Nginx through a container](https://www.digitalocean.com/community/tutorials/how-to-run-nginx-in-a-docker-container-on-ubuntu-14-04) (through Digital Ocean)

- Setting up Let's Encrypt cert for Nginx
 <pre><code class="bash">git clone https://github.com/letsencrypt/letsencrypt  `
./letsencrypt/letsencrypt-auto certonly --standalone --email thomas@seropian.io -d notsaved.org -d www.notsaved.org
</code></pre>

- Final container start call 
 <pre><code class="bash">sudo docker run --name docker-nginx -p 80:80 -p 443:443 -v ~/notsaved.org/html:/usr/share/nginx/html -v ~/notsaved.org/nginx/default.conf:/etc/nginx/conf.d/default.conf -v /etc/letsencrypt:/etc/letsencrypt -d nginx
</code></pre>
This call includes
- Port mapping for HTTP and HTTPS
- Mounting volumes for Nginx root 
- Mounting config file for Nginx 
- Mounting Let's Encrypt SSL cert and keyfile


As I have now a container infrastructure, I can deploy other apps super quickly. So my 2nd exercise came to mind very quickly. Let's deploy a Tor relay using a container. 

There is a link for that

- [Setting up Tor in a Docker container](https://blog.jessfraz.com/post/running-a-tor-relay-with-docker/)

A couple of minutes later, [here is the result](https://atlas.torproject.org/#details/AEC9958F7A1AD5C15875536EC09346DB3266AB0D). 

A couple of Todo items for me to play with in the next couple of weeks

- Implement Docker-composer
- Implement a  reverse proxy container so I can host multiple sites on the same server
- Deploy Drupal websites via Docker



</code></pre>
