---
title: Deploying to Heroku
type: lesson
duration: "1:25"
creator:
    name: Gerry Mathe
    city: London
competencies: Deployment
---


# Deploying to Heroku

### Objectives
*After this lesson, students will be able to:*

- Explain Heroku as a service and why it's useful
- Set up a new Heroku app & push to production
- Push & pull from Heroku PG DB

### Preparation
*Before this lesson, students should already be able to:*

- Describe what a server is
- Use Git to push code to a remote server (such as GitHub)

## Deploying, why? Intro (15 mins)

When we have finished developing a version of our app, we might want to put it on the internet for other people to see.

### Localhost

Most of what we've developed so far has just run on our own computers. Both our database and our web server have been on our computer. We've done this because it's much easier to develop locally because we don't actually need an internet connection.  However, people can't access it easily unless they are also on our local network.

### What is Heroku?

Heroku is a cloud-based web app hosting service, often called a _PaaS_ (Platform-as-a-Service). Essentially it's a collection virtual machines that run on Amazon Web Services (EC2) that host your applications in the cloud. By using Git, you can deploy your code directly to a Heroku VM (they call them "dynos") and seconds later your changes will be live in production.

By the way: All of Heroku lives on Amazon's Web Services (AWS).

To deploy an app to Heroku, it's a fairly straightforward step-by-step process.

First you need to link your machine to your Heroku account - a similar process to what we did with GitHub.

## Creating your Heroku and MongoLab Accounts

You will need to create accounts for _Heroku_ and _MongoLab_ before you can deploy your _MEN_ or _MEAN_ Stack apps. Both _Heroku_ and _MongoLab_ provide free hosting for a small number of applications.

## Preparing to push to Heroku

### Install Heroku Toolbelt

Next we need to install the [Heroku Toolbelt](https://toolbelt.heroku.com).

This is a command-line tool that allows us to use commands in the terminal, similar to the way that we use git.

Once it is installed, you need to login with your heroku credentials:

```bash
$ heroku login
Enter your Heroku credentials.
Email: adam@example.com
Password (typing will be hidden):
Authentication successful.
```

### Heroku create

Once you have a project that is managed with _Git_ (a Git project), you can run the `heroku` command to prepare the project for deployment to Heroku:

```bash
heroku create
```

Now you can push to Heroku with this command:

```bash
git push heroku master
```

> Note that git will only push your latest committed code to Heroku. Any uncommitted code will _not_ be deployed!

##Conclusion - 5 mins

- How does Heroku relate to AWS?
- Why can't you use Rails' default settings when pushing to Heroku?


