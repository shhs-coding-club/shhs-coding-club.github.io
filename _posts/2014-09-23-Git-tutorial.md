---
title: How to use Git
layout: post
date: 2014-09-23 20:00:00
categories: git tutorial
---


Git is an important tool, both for the club and in the larger world of development. This is not an in-depth tutorial; rather, it discusses the basic steps needed to run git on the school computers.


### Steps

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

7. Click `Repository`&rarr;`Git Bash`

    ![screenshot]({{ site.baseurl }}/images/step007.PNG)

8. Type the following commands: `git pull upstream master` and then `git push origin master`. You will be prompted for your password. Note that the text that appears will probably be different from that pictured.

    ![screenshot]({{ site.baseurl }}/images/step008.PNG)

9. You may now close the console window. Your repository is now up to date with upstream! Congrats!

### Notes

If you clone the repository to a flash drive or your network drive, you will not have to do steps 1-6. Just open up the repository, and do steps 7-9 to ensure your branch is up to date.

