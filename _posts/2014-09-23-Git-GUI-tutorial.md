---
title: How to use Git GUI
layout: post
date: 2014-09-23 20:00:00
categories: git tutorial
---

## Table of Contents

* [Introduction](#introduction)
* [Terms](#terms)
* [Typical Workflow](#typical-workflow)
* [Setting Up a Repository](#setting-up-a-repository)
* [Updating to Upstream](#updating-to-upstream)
* [Creating a Branch](#creating-a-branch)
* [Committing and Pushing Changes](#committing-and-pushing-changes)
* [Installing Git on Your Own Computer](#installing-git-on-your-own-computer)
* [Common Problems](#common-problems)
    * [Git says I don't have permission to push to origin](#git-says-i-don't-have-permission-to-push-to-origin)

## Introduction

Git is an important tool, both for the club and in the larger world of development. This is not an in-depth tutorial; rather, it discusses the basic steps needed to run git on the school computers.

## Terms
* Repository (repo): A place where the history of your work is stored.
* Commit: When you have made changes to a repository and want them saved as part of its history, you *commit* these changes.
* Push: When you want to move your repository's history to a repo hosted online (like one on GitHub).
* Fork: When someone branches their work off someone else's to make their own changes. So, if an application I like has a blue background but I prefer pink, I could fork it and change the background.
* Branch: Essentially a fork within your own repository. It allows you to experiment or make changes without risking your `master` branch.
* `master`: The main branch of a repo. In general, it is best not to make changes directly to it, but instead to use it to keep up to date with the upstream repository.
* Upstream: A term for the repository from which you forked. Your repository is *downstream* from it because information flowed downstream to you.

## Typical Workflow

1. [Set up a repository](#setting-up-a-repository) (only if not done previously)
2. [Updating to upstream](#updating-to-upstream)
3. [Creating a new branch for your changes](#creating-a-branch)
4. Making any changes
5. [Committing and pushing changes](#committing-and-pushing-changes)


## Setting Up a Repository

1. Open the `Git Gui` application

    ![screenshot]({{ site.baseurl }}/images/step001.PNG)

2. Select `Clone Existing Repository`

    ![screenshot]({{ site.baseurl }}/images/step002.PNG)

3. Click on the white text box titled `Source Location` and paste in the `HTTPS clone URL` from *your* fork of the repo. Click the `Browse` button next to `Target Directory` and choose a directory.

    ![screenshot]({{ site.baseurl }}/images/step003.PNG)

4. Click at the end of the white target directory box. Type out the name of the repository.

    ![screenshot]({{ site.baseurl }}/images/step004.PNG)

5. Press the `Clone` button and wait for the operation to complete.

    ![screenshot]({{ site.baseurl }}/images/step005.PNG)

6. Click `Remote`&rarr;`Add`. Fill in the name as `upstream` and the location as the HTTPS clone URL of the *club's* repo. Press the add button.

    ![screenshot]({{ site.baseurl }}/images/step006.PNG)

## Updating to Upstream

1. In Git GUI, go to `Branch`&rarr;`Checkout` and select `master`.

2. Go to `Remote`&rarr;`Fetch from`&rarr;`All`.

3. Click `Repository`&rarr;`Git Bash`

    ![screenshot]({{ site.baseurl }}/images/step007.PNG)

4. Type the following commands:

    1. `git reset --hard upstream/master`
    2. `git clean -fdx`

5. Go to `Remote`&rarr;`Push...` and in the dialog select `master` as the branch and `origin` as the remote.
    
    <!--You will be prompted for your password. Note that the text that appears will probably be different from that pictured.-->

    <!--![screenshot]({{ site.baseurl }}/images/step008.PNG)-->

3. Your repository is now up to date with upstream! From here, you should create a branch.

## Creating a Branch

1. Click `Branch`&rarr;`Create`.
2. Fill in a descriptive name for your branch under `Name`.
3. Select `master` under `Starting Revision`.
4. Make any changes to the branch and commit them.
5. To switch between branches, go to `Branch`&rarr;`Checkout` and select the branch you want.

## Committing and Pushing Changes

1. Click the `Rescan` button, and then the `Stage Changed` button
2. Type a descriptive message in the large text box in the bottom half of the window (In the imperative present tense, e.g. "Add Player class")
3. Click the `Commit` button
4. Go to `Remote`&rarr;`Push`
5. Select the branch you want to push (probably not `master`)

## Installing Git on Your Own Computer

Go to http://git-scm.com/downloads and download the right version for your OS. Installing should be pretty simple. Afterwards, open up the Git GUI application (on OS X and Linux, you may have to go to the command line and use the command `git gui`).

Additionally, on OS X and Linux, instead of going to `Repository`&rarr;`Git Bash` as on Windows, you just type those same commands into the command line.

## Common Problems

### Git says I don't have permission to push to origin

This problem is due to your `origin` having been incorrectly set. It can be remedied through the command:

1. `git remote set-url origin https://github.com/YOUR-USER-NAME-HERE/drugwars.git`

Following this, attempt to push to `origin` and it should work.
