---
title: Request Buffering with Reverse Proxies
slug: request-buffering-with-reverse-proxies
description: I used a reverse proxy to buffer incoming requests.  This is why
publishDate: 1 Jul 2022
---

## What is a reverse proxy?

A reverse proxy is a server that forwards requests from the client to another server.

![Flow chart describing relationship between client, reverse proxy, and upstream server.  The client is on the left with an arrow pointing towards the reverse proxy, which is in the center of the flow chart.  The reverse proxy points towards the upstream server, which is on the right.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/leahl8u922jdon4xqad9.png)

## Why use reverse proxies

There are several reasons you might want to use a reverse proxy:

- Load balancing - a reverse proxy can be used to distribute requests across a number of servers.
- Caching - caching and serving content from a reverse proxy can increase performance.
- Security - using a reverse proxy will obscure architectural details of your backend infrastructure as well as server identities (the IP of the origin server for instance).
- Maintainability - in the event that your upstream server moves, you would only need to update the value of the upstream server in a single place.
- Request buffering - Minimizes upstream server execution time.

### A closer look at request buffering

![Flow chart describing relationship between client, reverse proxy, and upstream server.  The client is on the left with an arrow pointing towards the reverse proxy, which is in the center of the flow chart.  This relationship is described as "slow request".  The reverse proxy points towards the upstream server, which is on the right.  This relationship is described as "fast request".](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1keq8t993tm0ypxyvplg.png)

Let’s take the example of a client on a slow connection trying to upload a large file (an image for instance) to a server.  When the server receives this request it will be blocked until it receives the entire request & processes it.  Essentially, the servers execution time will be directly affected by the connection speed of the client.

A reverse proxy will wait to receive all of the request from the client before forwarding it to the upstream server.  This means that the actual execution time on the server is greatly reduced, as this server-to-server request is much faster than the client-to-server request.

This pattern can be particularly useful when your upstream server has strict execution time limitations.  For example, [Netlify’s synchronous serverless functions](https://docs.netlify.com/functions/overview/#default-deployment-options) have an execution limit of 10 seconds, which begins as soon as the http connection is opened.  Using a reverse proxy in this case could decrease the risk of hitting that execution limit.
