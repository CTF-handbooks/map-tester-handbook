# Map Tester Handbook
## Table of Contents
- [Merged Doc](#merged-doc)
    - [Outline](#outline)
- [Individual Sources](#individual-sources)
    - [GreenBlob's message contents](#greenblobs-message-contents)
    - [-sniper-'s message contents](#sniper-s-message-contents)

## Merged Doc
### Outline
1. Labels to be aware of
2. PR scheme
3. Map works/errors
4. ^ Some error specifics
5. Flags and the base
6. Team zones and testing process
7. Config (to be discussed later) (also includes proper fields filled)
8. Design/glitches/mistakes/inconsistencies, balance/, opinion
9. Screenshot 
10. More to be included and discussed upon


## Individual sources
### GreenBlob's message contents 
1. Map basics
    Flags
    Unbreakable floor under flags
    Teamchests added for each team
    Indestructible barrier glass around the map (Or any other unbreakable material)
    Roof that prevents players from escaping
    Indestructible red barrier glass in the middle of the map (Indestructible red barrier stone for underground)
    Indestructible blocks at the bottom of the map
    Barriers are all placed properly
    Red barriers disappear when the math starts
    Map does not contain blocks that are not supported
    Players should be able to capture the flag
    
    **Players should not be able to escape the map and the map should work properly**

2. Team zones
    Teleports player back when crossed red barrier during build time
    Does not teleport the player back when the player did not cross the red barrier
    Red barrier covers all the empty spaces
    
    **Players should not be teleported back if they are standing within their team boundary**
    (Make sure to check all the corners of the team boundary. For example: the areas behind the team base, in the air, below in the ground, etc....)

3. Map config
    Map is enabled
    Map has a license (Recommended: CC BY-SA 4.0)
    Map has a suitable hint
    Map has initial stuff that is compatible with the map (Take notes of the terrain, the ores, etc....)
    Chest zones are added
    Team zones are set for all the existing teams

4. Balance:
    No team has a better position than the others
    No team has advantages
    The teams have about the same amount of ores and chests

   ** All teams must have an equal chance of winning**

5. Pull request
    Screenshot included with the PR (The screenshot ratio must be 3:2)
    PR includes the following files: map.mts, map.conf, and screenshot.png

### -sniper-'s message contents
You can test any map anytime. It is recommended to first test Pull requests with `Review required` label because other maps usually already have bugs/issues.

What should map tester look for? Issues or bugs such as:

- First map tester should check if map works in CTF game.
- Map should be unique and not similar to other maps. So this means that most of plain maps will be rejected if they are not interesting. The design of a map should encourage differing game play and tactics.
- It should be fun to play on it.
- Maps shouldn't be glitchy (ie: no holes which lead into void, no wrongly placed barriers). Barriers should be placed properly, red barrier should disappear on match start.
- Maps should not contain not-supported blocks (such as chests, rails, butterflies...). If there is not-supported block on a map, you will see red error in chat, starting with `Failed to resolve node name...`
- Map must have a **valid Free Software/Open Source license** . There should be a line in `map.conf`:` license = <license_name>`
- Maps should be reasonably balanced - i.e.: two team of equal ability would have the same chance of winning. One team should not have advantage (for example more ores, better position...).
- Players shouldn't be able to escape from the map - i.e. go outside of the barrier
- Pull request (=PR) should contain `map.mts`, `map.conf` and `screenshot.png`. If PR contain zip files for example, then it is not created properly. Screenshot should have ratio 3:2 (750x500px for example)
- Player should be able to pick and capture flag.
- Something what I have probably forgotten to add ¯\_(ツ)_/¯

And finally, write your review as comment in PR. **Tell your opinion** (fun/not fun, missing license, doesn't work...). Every opinion matters.