<p align="center"><img src="https://raw.githubusercontent.com/cstate/cstate/master/images/highlight.png" alt="cState"></p>

<p align="center"><a href="https://github.com/cstate/cstate/releases"><img src="https://img.shields.io/github/release/cstate/cstate/all.svg?style=flat-square" alt="GitHub release" /></a> <a href="https://github.com/cstate/cstate/commits/master"><img src="https://img.shields.io/github/last-commit/cstate/cstate.svg?style=flat-square" alt="GitHub last commit" /></a> <a href="https://github.com/cstate/cstate/tree/master/"><img src="https://img.shields.io/github/repo-size/cstate/cstate.svg?style=flat-square" alt="GitHub repo size in bytes" /></a> <a href="https://discord.gg/EvQZdhT"><img src="https://img.shields.io/badge/discord-support-7289DA.svg?logo=discord&style=flat-square" alt="Discord Chat" /></a> <a href="https://twitter.com/cstate"><img src="https://img.shields.io/twitter/follow/mistermantas.svg?style=social&amp;label=Follow" alt="Twitter" /></a> <a href="https://github.com/matiassingers/awesome-readme#readme"><img src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" alt="Awesome README" /></a></p>

> Über fast, backwards compatible (IE8+), tiny, and simple status page built with Hugo. Completely free with Netlify & GitHub Pages.

[**Want an example? Click here to see a live demo!**](https://cstate-example.netlify.com)

[You can also see what an example cState project’s source code.](https://github.com/cstate/example)

*Looking for contributors! See Contribute section:*

## Contents

+ [Features](#features)
+ Getting started
  + [Production](#production)
  + [Development](#development)
+ [Updating](#updating)
+ [FAQ](#faq)
+ [Contribute](#contribute)
+ [License](#license)

***

## Features

+ Built with [Hugo](https://gohugo.io), a hyperfast Golang generator
+ Works not just on mobile, but also on the archaic Internet Explorer 8
+ Comes with a simple, focused, and extremely light design
+ Edit your status page from a simple config file
+ Comes pre-equipped with Netlify CMS for quick admin updates
+ Easy to edit and deploy on Netlify or GitHub Pages
+ Secure, ready for HTTPS, thanks to [JAMstack](https://jamstack.org/)
+ Extensive documentation on the [wiki](https://github.com/cstate/cstate/wiki)

## Getting started

For this tutorial, it is assumed that you have Hugo and Git installed (check with `hugo version` & `git --version`).

#### Production

We encourage you to use [Netlify](https://www.netlify.com) for cState. These are the following options you need to change in deploy settings:

+ Build command: **hugo**
+ Publish directory: **public**
+ Add one build environment variable
  + Key: **HUGO_VERSION**
  + Value: **0.41**

**The easy way**

You can simply click this button to get started:

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/cstate/example)

This sets up cState with its default settings from the cstate/example repo.

***

If you want to do this from any branch in this repository, follow the manual instructions:

1. Download the contents of the `exampleSite` directory in this repository. This will be your site guts, which will hold the content and configuration for the status page.
2. Create a `themes` folder and navigate to it on the command line.

```bash
mkdir themes; cd themes;
```

3. Now simply add a Git submodule pointing to this repository, like so:

```bash
git submodule add https://github.com/cstate/cstate
```

4. Set up cState for your liking. It is now ready to be used in production.

#### Development

1. Clone this repository in the command line:

```bash
git clone https://github.com/cstate/cstate.git
```

2. Navigate to the theme directory:

```bash
cd cstate-master
```

3. Launch the development setup much like this:

```bash
hugo serve --baseUrl=/ --theme=cstate-master --themesDir=../..
```

The main directory is the theme itself (the cState guts, basically) and the `exampleSite` folder houses all content. Use this local setup to experiment before deploying to production!

If you would like to commit/make a PR, make sure that `themesDir` is a comment before trying to merge upstream.

## Updating

Assuming the production install instructions were followed, keep cState updated by having an up to date Git submodule in the `themes` folder. containing this repository. Your content will stay separate, as to avoid any conflicts.

If you already have a Git repository set up with a filled up `themes/cstate` folder, then all you need to do is this:

```bash
git submodule foreach git pull origin master
```

If you have previously used Netlfiy CMS or have made other changes without using the command line, the easiest thing to do is just clone it in a new place, change it how you want to, push those changes, and then you can safely remove the Git folder. So, do this:

```bash
git clone --recursive <your repo link goes here> && git submodule foreach git pull origin master && git push origin master
```

More info about submodules on [updating](https://stackoverflow.com/a/5828396) & [cloning](https://stackoverflow.com/questions/3796927/how-to-git-clone-including-submodules).

## FAQ

### Where do issues go?

#### Using an admin panel (Netlify CMS)

This takes a little more effort to set up but pays off in the long run — [see the wiki](https://github.com/cstate/cstate/wiki) for up to date information.

#### Doing it from the Git repository

Create a file in `content/issues`. The name of the file will be the slug (what shows up in the URL bar). For example, this is what `major-outage-east-us.md` should look like:

```md
---
title: Major outage in East US
date: 2017-02-30 14:30:00
resolved: true
resolvedWhen: 2017-02-30 16:00:00
severity: down
affected:
  - API
section: issue
---

*Monitoring* - After hitting the ole reboot button Example Chat App is now recovering. We’re going to continue to monitor as everyone reconnects. {{< track "2018-04-13 16:50:00" >}}

*Investigating* - We’re aware of users experiencing unavailable guilds and issues when attempting to connect. We're currently investigating. {{< track "2018-04-13 15:54:00" >}}
```

Time to break that down.

`title`: This is the one of the most important parts of an incident. *(required)*  
`date`: An ISO-8601 formatted date. Does not include time zone. This is when you first discovered the issue. *(required)*  
`resolved`: Whether issue should affect overall status. Either `true` or `false`. *(boolean, required)*  
`resolvedWhen`: An ISO-8601 formatted date. Does not include time zone. This is when downtime stopped. You may set the time that downtime ended without completely resolving the issue (thus leaving time for monitoring).  
`severity`: If an issue is not resolved, it will have an applied severity. There are 3 levels of severity: `notice`, `disrupted`, and `down`. If there are multiple issues, the status page will take the appearance of the more drastic issue (such as `disrupted` instead of `notice`). *(required)*  
`affected`. Add the items that were present in the config file which should alter the status of each individual system (component). *(array, required)*  
`section`. This must be `issue`, so that Hugo treats it as one. *(required)*  

### I have more questions!

Check out [the wiki](https://github.com/cstate/cstate/wiki).

## Contribute

cState needs help to grow, not only would it benefit from stuff like unit tests, but also get influenced by fresh ideas to grow even further.

+ Glance over the [Code of Conduct](/CODE_OF_CONDUCT.md).
+ Before submitting a pull request, create an issue to [discuss the implications of your proposal](https://github.com/cstate/cstate/issues).
+ Write consistent, simple, readable code and precise documentation.
+ You may also use the mnts [Discord chat](https://discord.gg/EvQZdhT) for support.

## License

[MIT](https://github.com/cstate/cstate/blob/master/LICENSE.md) © Mantas Vilčinskas
