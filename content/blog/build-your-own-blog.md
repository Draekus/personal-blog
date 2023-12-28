+++
author = "Patrick Gould"
title = "Build Your Own Blog"
date = "2023-12-23"
draft = true
description = "A comprehensive tutorial on building and hosting your own blog with Hugo and Firebase."
categories = [
    "Development",
    "Hugo",
    "Firebase",
]

tags = [
    "blog",
    "personal-blog",
    "hugo",
    "firebase",
    "git",
    "markdown",
]
+++

Whether you're a computer science student looking to land your first internship or a self-taught programmer looking to change careers, you're going to need a way to show off all those l33t h@cking skills you've gained. A great way to do that is to create a personal tech blog where you can share all the projects you're working on. It seems only natural that the first article of this blog be a guide on making your own blog with the same tech stack. A blog post about making blogs, very meta. I'll take you step by step through the process of creating a blog using Hugo, a static site generator, and hosting it for free on Google's Firebase platform. The only thing you'll need is a Github account and git installed on your local machine. So fire-up your terminal and let's get started.

## Getting Started

If you're on windows, and you haven't already, I highly recommend that you start by installing [Gitbash](https://git-scm.com/download/win) which will provide you with a bash terminal that comes with git pre-installed.

### Setting Up Hugo

The first thing you're going to need to do is install [Hugo](https://gohugo.io/) which is an open-source static site generator written in the [Go](https://go.dev/) programming language. Hugo allows you to write the content of your website using an extended markdown syntax and organize it using templates that you can create yourself or download as a theme. Hugo takes those markdown files and templates, smushes them together, and out pops a static html website.

If you're running Windows, like me, then you can install Hugo using either [scoop](https://scoop.sh/) or the [chocolatey](https://chocolatey.org/install) package manager.

For scoop run:
    
    scoop install hugo

For chocolatey run:

    choco install hugo

If you're running macOS you can use the [Homebrew](https://brew.sh/) package manager to install Hugo.

For homebrew run:

    brew install hugo

If you're running Linux or OpenBSD then installation will vary by ditribution. You can find installation instructions specific to your platform [here](https://gohugo.io/getting-started/installing/#linux).


### Setting Up Firebase

In order to deploy our site to firebase we're gonig to need to install the Firebase toolset. This requires [Node.js](https://nodejs.org/en/download/) and npm, the node package manager. 

Once you have Node.js installed you can check that it's working by running the following command.

    node --version

It should return something similar to this:

    $ node --version
    v18.16.0

You're now ready to install the Firebase toolset by running the following command:

    npm isntall -g firebase-tools

Next you'll want to open up a webbrowser and head to [Firebase](https://console.firebase.google.com/) where you can create a free account by logging in with your gmail address. Once you have an account, go back to your terminal and login to firebase there using the command:

    firebase login

This will open up a tab in your browser where you can login with the same gmail account. This will link your Firebase account to your installation of the Firebase toolset.

## Creating Your Blog

First things first, you'll need to decide on a home for you new blog. Either choose or create a directory where you'd like to store your source code and navigate to it inside of your terminal. Thankfully, Hugo provides a way to generate a new starter template automatically with the command "new site". For instance, if I wanted to create a new blog called coders-paradise i could run the following command:

    hugo new site coders-paradise

After running the new site command you should now see a new folder in the curent directory that matches the name of your blog. If you navigate into that directory you should see a layout similar to the following where you have a bunch of new folders and a single configuration file with the extension ".toml".

    archetypes/
    assets/
    content/
    data/
    hugo.toml
    layouts/
    static/
    themes/

### Selecting A Theme