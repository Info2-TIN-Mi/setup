# Setup

This repository contains the files for a correct setup for the lecture

## Root directory

Choose or create a directory dedicated to this lecture

Example:

```bash
/Users/pierre/Documents/01-HEIG-VD/11-COURS/00002-INFO2/02-LABOS
```

In this directory, copy the following directories from this repository:

- `.devcontainer`
- `.vscode`

The `.devcontainer` directory contains the `devcontainer.json` file which declares the docker's container to use.

The `.vscode` directory contains the following files:

- `launch.json`
- `settings.json`
- `tasks.json`

## Start the work

- open `VSCode`,
- menu `View / Command Palette`,
- type `Remote-Containers: Open Workspace in Container`,
- select the `wsp.code-workspace` in the root directory.

The very first time, the container will be downloaded for the docker's hub website `https://hub.docker.com/` which take a little time.

When ready, open a terminal (menu `Terminal / New Terminal`) and verify that you are running in the container :

- the terminal's prompt should be like `root@6fe1f5c2ef4b:/workspaces/00002-INFO2/02-LABOS#` 
- the result of the command `cat /etc/issue` must be `Ubuntu 18.04.3 LTS`

## Last check

- pull the `labo01` for the classroom repository in the root directory
- in the terminal, enter to this new lab's directory (command: `cd /workspaces/00002-INFO2/02-LABOS/labo01`)
- run the commande `make` which will go through the whole process of executable generation and test.

By the end, the message `ok.` must be displayed as a correct result, as shown below.

```bash
root@6fe1f5c2ef4b:/workspaces/00002-INFO2/02-LABOS/labo01# make
rm -f app
rm -f -rf obj
mkdir obj
gcc -std=c99 -Wall -Iinclude -c labo01.c -o obj/labo01.o -MMD -MF obj/labo01.d
gcc -o app obj/labo01.o  -lm
baygon -v -t t.yaml ./app
Test 1: exit code test.............. PASSED
Test 2: stdout output test.......... PASSED

Ran 2 tests in 0.01s.

ok.
```


Enjoy !
