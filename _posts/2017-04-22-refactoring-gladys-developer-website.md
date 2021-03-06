---
layout: post
title: Refactoring Gladys Developer Platform (Part 1)
description: How I'm refactoring Gladys Developer Platform to grow Gladys community!
img: refactoring-developer-website-part-1.jpg
categories:
- blog
- gladys
redirect_from:
- /blog/nodejs/gladys/2017/04/22/refactoring-gladys-developer-website.html
---

Hi, everyone! 

The Gladys developer website was launched two years ago in 2015. The goal was to build a community of developer around Gladys. Today, the website is not as sexy as it was in 2015, and not that easy to use. I've been thinking about it a lot, and I've tried to see how I can transform this simple website into a real platform that can make the project move forward 🚀🚀.

## The goal of the new platform

### Rethinking Gladys main website

You all know that we have currently two websites on the Gladys Assistant: 

- [https://gladysassistant.com](https://gladysassistant.com)
- [https://developer.gladysassistant.com](https://developer.gladysassistant.com)

The problem is that today these websites are not well organized. The main website explains how to install Gladys, but the documentation is on the developer website. Modules are only displayed on Gladys developer website. Compatible devices are displayed on both websites. It's a mess!

I really think all information about installing and configuring Gladys should be on the main domain.

The developer platform should only be about:
 
- Creating a developer account
- Publishing a module
- Releasing new version of a module
- Sharing scripts
- Adding new sentences for Gladys' brain
- Voting for other people sentences

That's it.

### Open API

You know that in Gladys it's possible to install modules directly from the dashboard. It means that the developer platform is not only a website, it's a real open API that communicates with all Gladys instances.

### Statistics

Today, I don't have any insights about how many Gladys instances are running. I don't know if they are running on Linux, if they are running on Windows, on MacOS. I don't know which version of Node.js they use. I don't know in which countries are my users! 

I can only rely on the main website analytics to understand best my users.

I think that this platform is the best opportunity to calculate all that. The goal is not to track sensitive data about you, no, not at all. I don't care! The goal is just to have interesting data like:

- 90% of Gladys instances are running on Linux
- 50% of Gladys users are in France
- 80% of Gladys instances runs on Node.js 4.x.x

That's all!

To achieve that, Gladys is going, if you accept, to send this additional set of data in the Gladys update request everything 24 hours (Each 24 hours, Gladys check if there are some updates to download).


## Data model

I've adapted the current data model of the developer website to fit our needs for this awesome platform! 

[![Gladys Developer Platform Data Model](/assets/img/2017-04-22-refactoring-gladys-developer-website/data-model.png)](/assets/img/2017-04-22-refactoring-gladys-developer-website/data-model.png)

(Click on the image to make it bigger)

To explain a little bit more: 

- **User:** An account on the developer platform.
- **Module:** A module created by a user. A module has several version, several texts and several reviews given by users.
- **Sentence:** A user can submit directly on Gladys new sentence to train Gladys' brain. These sentences can be upvoted by the community.
- **Script:** Users can share scripts on the platform.
- **Instance:** A Gladys instance. It's not mandatory that an instance is linked to a user, it's anonymous by default.

## To conclude

I'm going to work on this and explain on this blog in real-time how I'm implementing this in terms of architecture, database, and deployment.

The goal is not only to build a faster and more awesome platform, it's also to share my passion for back-end architecture 🙂

This article is the beginning of series of 7 articles. I hope you will all enjoy it!

**Summary of this series:** 

- [Refactoring Gladys Developer Platform (Part 1)](/blog/gladys/2017/04/22/refactoring-gladys-developer-website.html)
- [Database Design with PostgreSQL (Part 2)](/blog/gladys/2017/04/25/database-design-with-postgresql.html)
- [Building a powerful REST API with Node.js (Part 3)](/blog/gladys/2017/04/30/building-rest-api-using-node-js.html)
- Setting up Unit testing, Continuous Integration and Deployment (Part 4) (Coming soon)
- Leveraging caching with Redis (Part 5) (Coming soon)
- Scheduling job with RabbitMQ (Part 6) (Coming soon)
- A front-end in React/Redux (Part 7) (Coming soon)