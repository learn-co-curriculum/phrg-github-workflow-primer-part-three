# Pairing Project No. 3

## The Plan

In the middle of this lesson's tasks, your responsibilities will pivot. Whomever starts as the driver will switch and become the navigator where the lesson specifies. And vice versa.

Before you start, acquire your designated project repo from the course instructor.

# Links and Style

## Objectives

* Learn more about `git pull`, `git branch` and `git checkout`
* Learn about adding an `upstream` git remote to a fork
* Apply html links and its core attributes
* Apply basic css styles

## Where are my repos?

Today you may be working on a project that you own, a project that you've copied before, or new project. Before you begin, you must know exactly what you have stored in your `pairing_projects` directory to know what `git` commands to use.

If the repo you are working from today is new, then you can follow the same forking and cloning procedures from yesterday. If it's one you have cloned before, or if you are the original owner, the next sections apply to you.

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

Next we need update our fork with the most recent changes. To do this, pull the `master` branch from the upstream remote:

```bash
git pull upstream master
```

Now our fork will be up to date.

## Instructions

Using the instructions above, or the instructions from a previous lesson, update the project you are working on today to its most recent version. When you are done, verify that you are on the `master` branch with `git branch`.

* Create a new branch called `favorite_websites`
* In the project's `index.html`, add a paragraph element below each students image with a class of "favorite-website" and the text "Favorite website:"
* Acquire every class member's favorite website in Connect
* Inside each of the paragraph elements, after the text, add an anchor tag that references each member's favorite website
* Be sure to add the name of the website between the anchor tags so you can see it in the browser

If you haven't yet, open up your index.html in the browser and refresh between each change. Verify each link opens correctly.

* When one clicks on a link, make a change so that it opens in a new window (hint: What should the link `target`?)
* Add a `title` attribute to each link with a description of the website
* Add your changes with `git`
* Commit the change with a message of "Add favorite websites"

Your page should now look like this:

![Nitro is my Favorite](img/favorite-nitro.png?raw=true "Nitro is my Favorite")

Before we push our commit, let's make one more change. Since we have made our page more accessible by adding a `title` attribute to the links, let's do something similar to our images.

* Add an `alt` attribute to each img tag that contains the name of the person in the image
* Git add the change
* Commit the change with a message of "Add alternate text to developer images"
* Push your changes
* Open a Pull Request against the main project with a screen shot of your index page

## Switch Drivers

Using the instructions above, or the instructions from a previous lesson, update the project you are working on today to its most recent version, including the last PR. When you are done, verify that you are on the `master` branch with `git branch`.

* Create a new branch called `add_stylesheet`
* Create a directory called `css` on root
* Create a file called `style.css` inside the new directory
* In the new file, add a style that applies the font-style of *italic* to all h1 elements
* In the index.html, `<link>` this "stylesheet" inside the `<head>` element. You will know when the syntax is correct when the title of your index.html shows up italicized, like so:

![Italic Header](img/italic-header.png?raw=true "Italic Header")

* Add a `text-align` attribute to the h1 style, with a value of `center`
* Make all elements with the class of `.favorite-website` the `color: LightSeaGreen`
* Finally, open up a style for all `div`s with the class of `.developer` and copy these styles into it:

```css
div.developer {
  width: 200px;
  display: inline-block;
  border: 2px solid grey;
  border-radius: 5px;
  padding: 6px;
  text-align: center;
}
```

Your final product should look something like this:

![Developers with Style](img/styled-students.png?raw=true "Developers with Style")

* Add, commit and push your changes
* Open a Pull Request against the main project with a screen shot of your index page
