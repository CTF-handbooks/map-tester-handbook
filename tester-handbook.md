# Map Tester Handbook

## Table of Contents
> I will do later; the headings will be changed

> ## Outline
> 1. Labels to be aware of ✅
> 2. PR scheme ✅
> 3. Map works/errors 
> 4. ^ Some error specifics
> 5. Flags and the base
> 6. Team zones and testing process
> 7. Config (to be discussed later) (also includes proper fields filled)
> 8. Design/glitches/mistakes/inconsistencies, balance/opinion
> 9. Screenshot 
> 10. More to be included and discussed upon
> Ignore the above ;)

## Prequisites
First of all, you need the `Capture the Flag` game. To do so,
- Go to the `Content` Tab in your Minetest client.
- Click `Browse Online Content` 
- Search for `capturetheflag` (make sure that the `Games` category is selected)
- Click on the `+` icon to install it.
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

## What is GitHub and Git?
GitHub is a platform that hosts Git repositories and provides developers with several tools to assist their projects. Git is a free and open source version control system designed to handle everything from small to very large projects. Basically, GitHub is a site for managing code and various other projects using the Git. For now, this handbook will only cover the basic ways of obtaining the files you require for testing maps without the need of any command line interface. The handbook for that is a work in progress.

### 3. Git Terms
Below is a list of a few terms you should be aware of while map making. Don't be intimidated by these, but keep them in mind for future reference. 
- A **repository**, is the remote storage in which code is stored.
> In this case, the map's repository only contains the map folders and their respective files.
- A **fork** is a new repository that shares code and settings from the original repository. It can be modified and then be made into a **pull request** if needed.
> Here, map makers will be _forking the maps repository, making their needed additions, like adding maps, and then making a Pull Request_ (more on that below).
- A **branch** refers to a separate line of development that initially has the same code base as the repository in which it was made. This new branch can have its own set of files and commits.
- A **commit** means saving changes made to a project's files to the repository itself.
- A **pull** from a repository simply means getting the source code from the remote repository to one's local machine
- A **push** means pushing the locally built source code to a remote repository on a repository management platform such as GitHub.
- A **pull request** (PR) refers to when you make changes in one of your branches and try to integrate those changes with the main repository.

## How to know which maps to review?
#### *Where to find Map PRs?*
- Go to the [maps repository](https://github.com/mt-CTF/maps) on your web browser.
- Click the "Pull Requests" section like this:
![PR button](pr-s_section_example.png)
- You will come to notice PRs with some labels. If you click the PR, it will take you to it.
- There will be a series of tabs that will help you navigate through the things related to it. (An example image is shown below)
![Intra-PR Ribbon Example](ribbon_example.png)
- You can discuss about the PR and leave your reviews in the ***Conversation*** section. The ***Commits*** tab lists the commits that the (will do).

#### *Labels on Pull Requests*
The Map PRs have labels which indicate their current stage in development. You should look for the ***"New Map"*** and ***"Review Required :mag:"***. There are also others, such as, ***"PR not created properly"*** ***"WIP :building_construction:"*** (= Work In Progress), ***"Enhancement"***, ***"Action/change needed :grey_exclamation:"*** and so on. All these describe about a particular PR. An example of one that you can test is:
![Labels Example](label_example.png)

## Getting the PR files for testing
- Go the the `Pull Requests` and click on the Map PR you would like to review. 
- Click on the blue text indicating the `<username>:<branch-of-their-fork>` as shown below.
![PR Fork/Branch Example](pr-fork-branch-example.png)
- After doing so, use the `Download ZIP` option like this:
![Getting the files Example](pr-forked-repo-code-example.png)
- Extract the ZIP folder and select the particular map folder that has been added by the author of the PR within the extracted folders. In the example PR mentioned, the folder is `sewer_village`
- After successfully identifying the new map folder, copy and paste it to `<YOUR MINETEST FOLDER>/games/capturetheflag/mods/ctf/ctf_map/maps/` on your computer.
- You have now retrieved the required map folder!
> Make sure that the map has all the required files, namely, `map.mts`, `map.conf`, and `screenshot.png`. If not, then drop a message regarding it in the PR 
## Testing the Map
### 1. Playing the map
- 


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
