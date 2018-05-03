# Pairing Project No. 3

## The Plan

This pairing lesson will pivot team member responsibilities in the middle its tasks. Whomever starts as the driver will switch and become the navigator where the lesson specifies. And vice versa.

Before you start, acquire your designated project repo from the course instructor.

# Links and Style

## Objectives

* Learn more about `git pull`, `git branch` and `git checkout`
* Learn about adding an `upstream` git remote to a fork
* Apply html links and its core attributes
* Apply basic css styles

## Where are my repos?

Today you may be working on a project that you own, a project that you've copied before, or new project. Before you begin, you must know exactly what you have stored in your `pairing_projects` directory to know what `git` commands to use.

If the repo you are working from today is new, then you can follow the same forking and cloning procedures from yesterday. If it one you have cloned before, or if you are the original owner, the next sections apply to you.

## Changing branches

When returning to a git project you've worked on before, the first item you want to check is what branch you are on. Your shell prompt gives you this information, but we want to know about *all* the branches we have on our project. We find this out with `git branch`. Here is an example of the output of `git branch` in a project with 4 local branches:

```bash
garettarrowood: ~/Power/nitro (ruby-2.5.0) feature/deny_access_when_no_current_user
[Wed May 02 17:21:34]$ git branch
  bugfix/user_without_role
* feature/deny_access_when_no_current_user
  master
  replace_broken_images
```

The code snippet above should look just like your prompt. It shows your Mac OSX `User` name, the path to current directory, the Ruby version, and the current branch that is checked out. What does it mean to have a branch checked out? At any given time, you can only have one branch checked out. Each branch represents a different set of file changes. When you are on a branch and have the codebase open in your text editor, the text you see in your editor is what is on your branch. If you were to switch branches with your text editor open, you will see the text change on an altered file.

IMPORTANT NOTE: By default, every new git project names its main branch `master`. It is possible to rename `master`, but that would be a very ill-advised thing to do. By design, everyone working with git understands the `master` branch naming convention. With that said, the `master` branch is just a branch. It behaves like any other branch on a project.

In the above example, the `feature/deny_access_when_no_current_user` branch is checked out. We see this in the shell prompt, and we also see it by the star in the output of the `git branch` command.

Before we do anything in our project, we want to relocate back to the `master` branch. We can move between branches using the `git checkout <branch>` command.

```bash
garettarrowood: ~/Power/nitro-web (ruby-2.5.0) feature/deny_access_when_no_current_user
[Wed May 02 17:38:29]$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.

garettarrowood: ~/Power/nitro-web (ruby-2.5.0) master
[Wed May 02 17:38:37]$
```

## Updating the project

### As Project owner

If you are the Github owner of the project you have today, then you are not on a fork. All you need to do is make sure all open PRs are merged, then run `git pull` to "pull down" all the new changes into your local copy of the codebase.

### From a fork

If you have a fork of the project already, you need to update it.

Do you remember what we originally copied with `git clone` when we pulled down the files locally? We made of a copy of your account's fork of the main project. Since then, your fork has stayed the same. Only the main project has been merging pull requests. So what is the right path to acquire the most up to date version of the main project?

We have to add a `git remote`, which is conventionally named `upstream`, to the main project. This way our computer can see if there is anything to update (right now, it is only linked to our account's fork). To achieve this, we need to navigate to the main project's page and grab its ssh_remote_url.

Once we verify that we are on our local `master` branch, run this command:

```bash
git remote add upstream <ssh_remote_url>
```

You can verify this works correctly by running `git remote -v`. Your output should look like this:

```bash
garettarrowood: ~/Development/awesome_project (ruby-2.5.1) master
[Thu May 03 07:08:00]$ git remote -v
origin  git@github.com:garettarrowood/awesome_project.git (fetch)
origin  git@github.com:garettarrowood/awesome_project.git (push)
upstream  git://github.com/main_project_owner/awesome_project.git (fetch)
upstream  git://github.com/main_project_owner/awesome_project.git (push)
```

## Instructions
