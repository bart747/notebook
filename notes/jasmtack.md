# Jamstack notes

Pre-built files served over a CDN means shorter time to first byte.
A user doesn't wait for build process.
Geolocation of assets is better.

A site can be served via CDN entirely.

Static assets are easy to cache inside a CDN.

Files served via CDN are easier to scale and more global.
CDN services usually offer global scaling solutions.
CDNs are the most global networks when it comes to sending software.

Server side processes are available to front-end processes through APIs.

Pre-generated assets are read only, which is a security benefit.

It's relatively easy to find talent.
Jamstack is based on well known tools. 

Jamstack tools are all the best (arguably) stuff from the Node/JS/TS/Deno world. 
It includes build processes, one of the core concepts here.

Static files mean easy deployment. 

Flow:

```

|||||||| <<+>> |CDN|
|Client|
|||||||| <<?>> |services| <<?>> |database|

```
