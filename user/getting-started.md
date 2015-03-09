---
title: Getting started
layout: en
permalink: /user/getting-started/
---

### Linthub Overview

Linthub will check the quality of pull requests by performing static code analysis. All (potential) problems will be commented on as line comments allowing the submitter to review and update the pull request. It will increase code quality and save time to the repository owner. 

### Step one: Sign in

To get started with Linthub, sign in with your GitHub account. Go to [Linthub](https://linthub.io) and follow the Sign In link at the top of the page.

Note that for private repositories, the [Linthubot](https://github.com/linthubot/) should be added to your team with the read-only access.

While signing in, GitHub will ask you for a set of access permissions on our
behalf. We've [outlined them and their use in greater detail](/user/github-oauth-scopes).

### Step two: Activate GitHub Webhook

Once you're signed in, and we've initially synchronized your repositories from
GitHub, go to your [profile page for open source](https://linthub.io/profile).

You'll see all the organizations you're a member of and all the repositories you
have access to. You can enable the service hook for the repositories you have access to.

Flip the switch to on for all the repositories you'd like to enable.

###  Step three: Add .linthub.yml file to your repository

Linthub can be configured using the .linthub.yml configuration file. 

If `.linthub.yml` is not in the repository, is misspelled or is not a [valid
YAML](http://yaml-online-parser.appspot.com/), Linthub will ignore it,
and use the defaults instead.

### Step four: Trigger Your First Build With a Git Push

Once a GitHub hook is set up, push your commit that adds .linthub.yml to your repository. That should add a build into one of the queues on [Linthub](https://linthub.io) and your build will start as soon as at least one worker for your language is available.

To start a build perform one of the following:

1. Commit and push something to your repository
1. Go to your repository's settings page, click on "Webhooks & Services" on the left menu, choose "Linthub" in the "Services",  and use the "Test service" button.

Please note that **you cannot trigger your first build using the Test Hook button**. It has to be triggered by a push to your repository.

### Step five: Tweaking your configuration

Your project might require some customization to the build process.

After making some changes to the `.linthub.yml`, don't forget to check that it is a [valid YAML](http://yaml-online-parser.appspot.com/).

### Step seven: We are here to help!

For any kind of questions feel free to join our IRC channel [#linthub on chat.freenode.net](irc://chat.freenode.net/%23linthub). We're there to help :)
