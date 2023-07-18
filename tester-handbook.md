# Map Tester Handbook

## Table of Contents
> I will do later; the headings will be changed

> ## Outline
> 1. Labels to be aware of
> 2. PR scheme
> 3. Map works/errors
> 4. ^ Some error specifics
> 5. Flags and the base
> 6. Team zones and testing process
> 7. Config (to be discussed later) (also includes proper fields filled)
> 8. Design/glitches/mistakes/inconsistencies, balance/opinion
> 9. Screenshot 
> 10. More to be included and discussed upon
> Ignore the above ;)

## Introduction
CTF Map Testers have a big task on their hands. The process of testing maps involves numerous steps, and everyone has their own unique style. However, how can you get started with it? What are the requirements for it? What are the points to keep in mind while testing maps? All these questions and more will be addressed in this handbook. This handbook is **not** a rigid set of rules that Map Testers should dogmatically follow. But instead, it is a compilation of guidelines and things that Map Testers should have at their disposal for greater analytical productivity in doing their job as a tester. If you have any suggestions or improvements regarding this project, feel free to make a PR or Issue for it! This project is possible only through the efforts of the community of Map Testers at CTF.
Maps for the Capture the Flag game are located in the [CTF Maps repository](https://github.com/mt-CTF/maps). 

## Structure of the Repository

### 1. Where do I find maps for CTF?
All the [maps on CTF](https://github.com/mt-CTF/maps) are in a repository on [GitHub](https://en.wikipedia.org/wiki/GitHub), the website via which you may be reading this. GitHub is one of the “many platforms and cloud-based services for software development and version control using `Git`, allowing developers to store and manage their code.” But no worries, you don't need to be a full-stack coder to use Git. 

### 2. What do the folders and files mean?
The repository contains folders dedicated to each map. For example, the folder containing the required files for the “Intervention in the Ice Age” Map is in the folder `iceage`. The scheme of a map folder in the repository should be as shown below:
```
<map folder>
	├── map.conf
	├── map.mts
	└── screenshot.png
```
1. `map.conf`: The file contains metadata about various constants and fields essential to the map.
2. `map.mts`: A schematic file (`.mts`) is used to import the map into the game world.
3. `screenshot.png`: A screenshot of the map. It should make the important parts of the map visible and is needed to have an aspect ratio of 3:2 (600×400px is suggested).

## Using GitHub and Git

The gist of Git:
> Git is a [free and open source](https://git-scm.com/about/free-and-open-source) distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
> - [The official git website](https://git-scm.com/)

And GitHub:
> _GitHub hosts Git repositories and provides developers with tools to ship better code through command line features, issues (threaded discussions), pull requests, code review, or the use of a collection of free and for-purchase apps in the GitHub Marketplace. With collaboration layers like the GitHub flow, a community of 100 million developers, and an ecosystem with hundreds of integrations, GitHub changes the way software is built._
> - [Git and how it works with GitHub](https://docs.github.com/en/get-started/using-git/about-git)

{{box op="start" cssClass="boxed noteBox"}}
**Note!**
Test box
This is something important to keep in mind.
{{box op="end"}}


Git is available universally on all operating systems. You can read the installation instructions [here](https://git-scm.com/download/). A look-up in your favourite search engine about “basic git commands” should get you started. For the purposes of this handbook, you will need to know the following commands:
- `git clone git@github.com:<repository name>.git` \-  Clones the repository into a folder named as the repository
- `git pull` \-  Fetches and merges the contents of the repository to your local working branch. You will be using this a lot.
- `git checkout <branch name>` \- Changes your current working branch to the one you want to. You will utilise this for grabbing the appropriate folders since changes (here, changes refer to Map additions) are usually on a branch other than the `master`/`main`. 

If you're wondering why it is mentioned in this handbook to use commands specifically, it is because they will significantly make the process quicker.

## Testing Maps

### 1. How to know which maps to review?
The Map PRs have labels which indicate their current stage in development. The one's that you should look for are the ***"New Map"*** and ***"Review Required'***. There are also others, such as,
- ***"PR not created properly"***: The PR is not structured as instructed or there is a conflict of the intended changes,
- ***"WIP"***: Literally means "Work in Progress". It indicates that the map is not ready for a final review and is currently in the process of making or refining,
- ***"Enhancement"***: The PR enhances a map that already was, and so on.

## Checking the PR scheme
## Cloning the PR for Testing (+ scripts WIP)
## Map
## Etc

# Individual sources
## GreenBlob's message contents 
1. Map basics
    * Flags
    * Unbreakable floor under flags
    * Team chests added for each team
    * Indestructible barrier glass around the map (Or any other unbreakable material)
    * Roof that prevents players from escaping
    * Indestructible red barrier glass in the middle of the map (Indestructible red barrier stone for underground)
    * Indestructible blocks at the bottom of the map
    * Barriers are all placed properly
    * Red barriers disappear when the match starts
    * Map does not contain blocks that are not supported
    * Players should be able to capture the flag
    
    **Players should not be able to escape the map and the map should work properly**

2. Team zones
    * Teleports player back when crosses red barrier during build time
    * Does not teleport the player back when the player did not cross the red barrier
    * Red barrier covers all the empty spaces
    
    **Players should not be teleported back if they are standing within their team boundary**
    (Make sure to check all the corners of the team boundary. For example, the areas behind the team base, in the air, below in the ground, etc....)

3. Map config
    * Map is enabled
    * Map has a license (Recommended: CC BY-SA 4.0)
    * Map has a suitable hint
    * Map has initial stuff that is compatible with the map (Take notes of the terrain, the ores, etc....)
    * Chest zones are added
    * Team zones are set for all the existing teams

4. Balance:
    * No team has a better position than the others
    * No team has advantages
    * The teams have about the same amount of ores and chests

   **All teams must have an equal chance of winning**

5. Pull request
    * Screenshot included with the PR (The screenshot ratio must be 3:2)
    * PR includes the following files: map.mts, map.conf, and screenshot.png

## -sniper-'s message contents
You can test any map anytime. It is recommended to first test Pull requests with a `Review required` label because other maps usually already have bugs/issues.

What should map tester look for? Issues or bugs such as:

- First map tester should check if map works in CTF game.
- Map should be unique and not similar to other maps. So this means that most of plain maps will be rejected if they are not interesting. The design of a map should encourage differing gameplay and tactics.
- It should be fun to play on it.
- Maps shouldn't be glitchy (i.e., no holes which lead into voids, no wrongly placed barriers). Barriers should be placed properly, red barrier should disappear on match start.
- Maps should not contain not-supported blocks (such as chests, rails, butterflies...). If there is not-supported block on a map, you will see red error in chat, starting with `Failed to resolve node name...`
- Map must have a **valid Free Software/Open Source license** . There should be a line in `map.conf`:` license = <license_name>`
- Maps should be reasonably balanced - i.e.: two team of equal ability would have the same chance of winning. One team should not have advantage (for example more ores, better position...).
- Players shouldn't be able to escape from the map - i.e. go outside of the barrier
- Pull request (=PR) should contain `map.mts`, `map.conf` and `screenshot.png`. If PR contain zip files for example, then it is not created properly. Screenshot should have ratio 3:2 (750x500px for example)
- Player should be able to pick and capture flag.
- Something what I have probably forgotten to add ¯\_(ツ)_/¯

And finally, write your review as a comment in PR. **Tell your opinion** (fun/not fun, missing license, doesn't work...). Every opinion matters.
