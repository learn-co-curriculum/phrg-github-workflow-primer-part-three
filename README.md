# Pairing Project No. 3

## The Plan

This pairing lesson will pivot team member responsibilities in the middle its tasks. Whomever starts as the driver will switch and become the navigator where the lesson specifies. And vice versa.

Before you start, acquire your designated project repo from the course instructor.

# Links and Style

## Objectives

* Learn about adding an `upstream` git remote to a fork
* Learn more about `git pull`, `git branch` and `git checkout`
* Apply html links and its core attributes
* Apply basic css styles

## Where are my repos?

Today you may be working on a project you've copied before, or you may be working from a new repo. Before you begin, you must know exactly what you have stored in your `pairing_projects` directory to know what `git` commands to use.

If the repo you are working from today is new, then you can follow the same forking and cloning procedures from yesterday. If it one you have cloned before, or if you are the original owner, the next sections apply to you.

## Changing branches

When returning to a git project you've worked on before, the first item you want to check is what branch you are on. Because you have copied over a custom `.bashrc` and `.bash_profile`, your shell prompt gives you this information. But we want to know about all the branches we have on our project. We check this with `git branch`. Here is an example of the output of `git branch` in a project with 4 local branches:

```bash
garettarrowood: ~/Power/nitro (ruby-2.5.0) feature/deny_access_when_no_current_user
[Wed May 02 17:21:34]$ git branch
  bugfix/user_without_role
* feature/deny_access_when_no_current_user
  master
  replace_broken_images
```

The code snippet above should look a lot like your prompt. It shows a Mac OSX `User` name, the path to current directory, the Ruby version, and the current branch that is checked out. What does it mean to have a branch checked out? At any given time, you can only have one branch checked out. Each branch represents a different set of file changes.

IMPORTANT NOTE: By default, every new git project names its main branch `master`. It is possible to rename, but that would be a very ill-advised thing to do. By convention, every one working with git understands the `master` branch naming design. With that said, the `master` branch is just a branch. It behaves like any other branch on a project.

In the above example, the `feature/deny_access_when_no_current_user` is checked out. We see this in the shell prompt, and we also see it by the star in the output of the `git branch` command.

Before we do anything in our project, we want to relocate back to the `master` branch. We can move between branches using the `checkout` command.

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

If you are the Github owner of the project you are working on today, then you are not on a fork. All you need to do is make sure all open PRs are merged, then run `git pull` to "pull down" all the new changes into your local copy of the codebase.

### From a fork
