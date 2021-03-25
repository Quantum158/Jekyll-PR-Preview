# Jekyll-PR-Preview
A nodejs script, written in Typescript, to track, download, and enable seamless contribution to Jekyll site repositories

## Functions
The script is designed to be hosted on an external provider. It listens for the pull_request webhook type sent from a repository. When a payload is received, the script attempts to download the pull request's branch and build the site using a Jekyll instance. Multiple jekyll instances can be run simultaneously, one per pull request. Everytime a new commit is added to a PR, the script will restart only that instance and merge the new changes.

The script attempts to keep each instance open for a certain, definable number of hours following the most recent commit to a PR. An instance is destroyed after this time, or earlier if the PR is closed for any reason.

The script also accepts basic commands in PR threads (provided that they are registerd and the issue_comments type is enabled in the webhook). This allows a user to request a preview site without needing to commit new code to their PR.

## Getting Started
This project was not initially designed to be public so it is intentionally not documented.

This project is currently used for the E.P. Scarlett Technical Theatre Program to maintain a wiki for new student joining the program. This repo is open source and can be [Found here](https://github.com/epstechtheatre/epswebpreviewer).

It takes a little work to get this script running, this is because of a weird fork of Jekyll that Github pages uses. You can try referring to information in the meta folder of the repo (for linux). For Windows, good luck.
