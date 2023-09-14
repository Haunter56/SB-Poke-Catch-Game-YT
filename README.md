# SB-Poke-Catch-Game-YT
Poke Catch Game using Streamer.bot for YouTube


## **Description** 
[wrap="info"]  
This is a Pokemon Catch game for YouTube where viewers can try to catch wild pokemon that appear and fill out their Pokedex. It was designed primarily for YouTube, but could possibly work with Twitch if the Streamer.bot sub-actions and C# code is updated.   
[/wrap]



## **Resources** 

### OBS
Make sure your OBS has these two plugins. If you don’t, I have provided links to them.

[Source Copy Plugin](https://obsproject.com/forum/resources/source-copy.1261/)

[Move Transition Plugin](https://obsproject.com/forum/resources/move-transition.913/)

Then import the OBS scene collection that matches YOUR base canvas resolution (1080p or 1440p)
- 1080p
- 1440p
- Tools > Source Copy > Load Scene > Find the file and import into OBS

### Downloading Other Files

Download the Pokemon cries and Sugimori art from [veekun](https://veekun.com/dex/downloads) under "Other files"

[PICTURE GOES HERE]

Create a folder and unzip the compressed folders you downloaded into the new folder. Take note of where those folders are.
You may have to unzip using 7-zip first, and then extract it again after that. Not sure why, but that's how I got it to work

In the `Sugimori art folder` make changes to the following images:
- `201.png` > delete the file (it's broken)
- `201-f.png` > change to `201.png`
- `386.png` > delete the file (it's broken)
- `386-[style of your choice]` > change the style you want to appear to `386.png`

Download this ZIP, unzip it, and put these folders in your new folder you created as well:
- Catch Chance
- Sound Effects
- Text Names


### Last Files
Find a square image of a Pokeball and save it in the "sugimori" folder as `0.png`
Update the image source on the [S0] Pokeball Scene to that `0.png` image location

Optional - There is a "Success" image on the [S1] Catch That Pokemon scene that you can update to the Streamer.bot logo, or whatever you want


## **Streamer.bot Pre-Import Setup**

The following timers don't import to Streamer.bot so you will have to set them up:
- Pokemon Run Timer
a. Put the interval to 30-40 seconds
b. Set to Disabled
- Poke Catch Game Appear Timer
a. I would recommend 150 seconds or more
b. You can make it a random time amount with a specific range as well


## **Import Code** 

[YouTubePointsSystem.sb|attachment](upload://n0xwzaWJmuplTquifjx2gsssIOa.sb) (14.8 KB)




## **Installation** 

In Streamerbot select the Import button from the top left menu.

Drag and drop the file or copy the text from the file and paste all the text into the Import String field.

[wrap="info"]
There should be 31 actions and 12 Commands.
[/wrap]

![image](upload://yvzYxE4Lk8ptM7d2LOqFCuUqhnv.png)


## **Configuration**


### Assign Timer Triggers in Streamer.Bot

1. "3 (Timed Action) - Poke Catch Run Away Action" - add the timer trigger of “Pokemon Run Timer”
2. "3 (Timed Action) - Pokemon Catch Appeared!"  - add the timer trigger of “Poke Catch Game Appear Timer”


### File Locations

You will need to update file locations on the action "1 (Pre-Requisite Action) - Set Global Poke File Paths" so they are pointed to the correct file locations on your PC.

[wrap="warning"]
MAKE SURE TO USE " \ " and not to copy the file location from Windows Explorer or it won’t work.
[/wrap]


1. `pokeTextNamesFolder` - The Text Names folder location
2. `pokeCatchChanceFolder` - The Catch Chance folder location
3. `pokePictureFolder` - The Pokemon Pictures folder location
4. `pokeCriesFolder` - The Cries folder location
5. `soundEffectsFolder` - The Sound Effects folder location

Once you are done, right-click the "Test" trigger and test it. 

If you hear the sound of a successful Pokeball catch and see the toast notification, then it worked! This will assign the paths to global variables so the rest of the actions can work.


### Assign Timers in Sub-actions

There isn’t a way to import Timers yet so we have to set these up by opening the TImer sub-action and selecting the timer


1. `5 (Background Timer State) Disable Poke Catch Game Appear Timer` - Timer (Poke Catch Game Appear Timer :: Disabled)
2. `5 (Background Timer State) Disable Pokemon Run Timer` - Timer (Pokemon Run Timer :: Disabled)
3. `5 (Background Timer State) Enable Poke Catch Game Appear Timer` - Timer (Poke Catch Game Appear Timer :: Enabled)
4. `5 (Background Timer State) Enable Pokemon Run Timer` - Timer (Poke Catch Game Appear Timer :: Disabled)




### Pokedex Setup

By default, only a message will be sent in chat with the pokedex completion number and % complete. There are two additional optional ways for viewers to see their pokedex

1. Discord Webhook - You can have the screenshot sent to a discord channel by setting up the webhook address in the “Show Pokedex Gen #” actions and enabling the sub-action

(Only update the webhook name and the webhook address. Leave the majority of the content and image as is)

2. Pokedex scene appearing in OBS - You can have the images of the caught pokemon show up on screen by enabling the two OBS Source Visibility sub-actions in each “Show Pokedex Gen #” action


### OBS Audio Note

[wrap="warning"]
By default the sound of the pokemon cry is set to play in OBS through your Monitor ONLY, no output. Depending on your sound settings in OBS you may want to update this if you like.
[/wrap]



### Gen 1-3 Settings
By default it has Pokemon randomly appear from Gens 1-3 (#’s 1-386) but you can change it so that it selects a smaller range by changing the
 “Random Number between…” sub-action on the “Pokemon Catch Appeared” action

PICTURE

 And the “set argument %minimum%” and “set argument %maximum%” sub-actions on the “Specific Pokemon Catch Appeared!” action


PICTURE


### Difficulty Settings
If you feel that pokemon are TOO EASY to catch or TOO DIFFICULT you can go into the code and change the number.
On the “Poke Catch Action” go to the “Execute Code (Determines if Pokemon was Caught) sub-action and double-click

PICTURE


Find the number “150” in the code and change it lower if you want it to become easier, or higher if you want it to be more difficult to catch the pokemon


PICTURE

After updating the number, then hit “Compile” and make sure it compiled successfully.
Then hit “Save and Compile”





## **Commands**

### !catch & !catch2
These are the commands that can be used when:
1. A wild pokemon appears (anyone can use it)
2. A user redeems `!catchpokemon` or `!catchmypokemon`

If a user redeemed the command, then Streamer.bot will only let the redeemr use the `!catch` or `!catch2` commands.

There is an option to use `!catch2` because sometimes YouTube doesn't let the `!catch` command through. If users report their `!catch` command isn't working and you don't see any message of it, then recommend that they use `!catch2`


### !catchpokemon
example - `!catchpokemon`

This command is a redeem where a user can spend points to have their OWN chance at catching a random pokemon using `!catch` or `!catch2`
- If the random pokemon has already be caught by the user, then it will reset and refund their points.


### !catchmypokemon #

This command is a redeem where a user can spend points to have their OWN chance at catching a SPECIFIC pokemon using a number after `!catchmypokemon`

example - `!catchmypokemon 1` would make Bulbasaur appear.

By defauly the number will work from 1 through 386

Users will not be able to catch a specific pokemon they have already caught.



### !pokedex, !pokedex2, & !pokedex3

These commands will retrieve the user's Pokedex count and % completion of Gen1, Gen2, & Gen3 respectively

Gen1:
`!pokedex`
`!pokédex`
`!pokedex1`
`!pokédex1`
Gen2:
`!pokedex2`
`!pokédex2`
Gen3:
`!pokedex3`
`!pokédex3`

Please see the Pokedex Setup in the Configuration section above for more options.



### !pokeparty

This command will show a user's 6-slot pokemon party on screen
example:
`!pokeparty`
`!poképarty`

In order to set pokemon they have caught, the users will need to use the "!slot#" command


### !slot1-6
Once a user has caught a Pokemon, they can assign it to one of their 6 slots in their Pokemon party:
`!slot1 [pokedex #]`
`!slot2 [pokedex #]`
`!slot3 [pokedex #]`
`!slot4 [pokedex #]`
`!slot5 [pokedex #]`
`!slot6 [pokedex #]`
example - If a user wants to assign Mewtwo to slot 4 in their Pokemon party they would type:
`!slot4 150`
if instead they wanted to assign it to slot 2:
`!slot2 150`

[wrap="warning"]
Remember that they can only assign a Pokemon if they have caught it.

Also, If the pokemon is already assigned to a slot, they will need to assign a different pokemon first before they move it to a new slot

[/wrap]






## Contributors

Inspired by the original points system for Twitch by [VRFlad](https://www.twitch.tv/VRFlad)
Made for YouTube by  [Haunter](https://www.youtube.com/channel/UC9qO6-NFvWwhde5o2B_DMzQ)
