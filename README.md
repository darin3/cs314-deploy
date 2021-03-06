# Auto-Deploy Script for CS314
Automate the server deployment process for the CS314 trip project. Works with DEV and SPRINT[1-5] options.

## Script Setup
* Copy **deploy.sh** to the project **t##/bin/** directory.
* If it is not executable, add permissions with **chmod +x deploy.sh**.

## Running
1. From the t## directory, run `./bin/deploy.sh`.
1. Follow the prompts. Provide eID (used for ssh/rsync) and server (DEV or SPRINT#).
1. The script runs `./bin/run.sh -d` automatically if the target directory does not contain a server-*.jar file. Otherwise, you can optionally skip this command to turn in the current jar located in target.

*If an error occurs, run *`./bin/run.sh -d`* separately to check for errors, and/or make sure port forwarding is working if necessary*.

## Passwordless SSH Login (optional, but convienent and recommended)
* Follow the steps at this [link from linuxize](https://linuxize.com/post/how-to-setup-passwordless-ssh-login/) to use SSH with the university machines without a password. There are many resources on this topic.
* If this isn't set up, you will have to **enter your remote machine password twice** (rsync + ssh commands).

## Warnings
* This script must be run in a **Bash shell**.
* By default, the script **may attempt to check in multiple jars if there are already server-*.jar files in the remote /tmp/ directory**. This can be fixed by re-running deploy.sh since it cleans up the jars in /tmp/ after running for clean up.
* This script has only been tested on Fedora and Ubuntu.
* If you are deploying a sprint server, make sure to enter the correct sprint number (eg. SPRINT3) or it won't show up.
