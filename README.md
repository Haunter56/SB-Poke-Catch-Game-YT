## **Description** 

This is a Pokemon Catch game for YouTube where viewers can try to catch wild pokemon that appear and fill out their Pokedex. It was designed primarily for YouTube, but could possibly work with Twitch if the Streamer.bot sub-actions and C# code is updated.   


## **Video Tutorial** 

https://youtu.be/eWh4gqa9_5I?si=NXy9NvrzZ_UobED2



## **Resources** 

### OBS
Make sure your OBS has these two plugins installed. If you don’t, I have provided links to them:

[Source Copy Plugin](https://obsproject.com/forum/resources/source-copy.1261/)

[Move Transition Plugin](https://obsproject.com/forum/resources/move-transition.913/)


Then import the OBS scene collection that matches YOUR base canvas resolution (1080p or 1440p)
- [OBS Poke Catch Game 1080p Base Canvas Scenes.json](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/blob/main/OBS%20Poke%20Catch%20Game%201080p%20Base%20Canvas%20Scenes.json)



- [OBS Poke Catch Game 1440p Base Canvas Scenes.json](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/blob/main/OBS%20Poke%20Catch%20Game%201440p%20Base%20Canvas%20Scenes.json)

  
- Tools > Source Copy > Load Scene > Find the file and import into OBS


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/eb7c2c9d-8928-416a-91b4-294ba03ee516)






If for some reason your OBS filter and move actions don't work you may need to go to Stream Apps > OBS > right-click on the connection > and update all actions to use "OBS [v5.x]"



![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/a09bdde3-f0a0-4c79-a60b-3337378640bb)




### Downloading Other Files

Download the Pokemon cries and Sugimori art from [veekun](https://veekun.com/dex/downloads) under "Other files"




![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/bda3f631-c322-4ec9-85a2-71099dd1865e)




Create a folder and unzip the compressed folders you downloaded into the new folder. Take note of where those folders are.


You may have to unzip using 7-zip first, and then extract it again after that. Not sure why, but that's how I got it to work



In the `Sugimori art folder` make changes to the following images:
- `201.png` > delete the file (it's broken)
- `201-f.png` > change to `201.png`
- `386.png` > delete the file (it's broken)
- `386-[style of your choice]` > change the style you want to appear to `386.png`



Download [this ZIP](https://drive.google.com/file/d/1bPwf9X3UyhVe2cGsJUCgp-cS6XTX_9UN/view?usp=sharing), unzip it, and put these folders in your new folder you created as well:
- Catch Chance
- Sound Effects
- Text Names

You should now have these folders in a location you can reference later:


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/1e863799-507a-4032-a1b2-a799220b2a50)




### Last Files
Find a square image of a Pokeball [like this](https://static.wikia.nocookie.net/pokemon-fano/images/6/6f/Poke_Ball.png/revision/latest?cb=20140520015336) and save it in the "sugimori" folder as `0.png`
Update the image source on the [S0] Pokeball Scene to that `0.png` image location


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/a9afadc6-9b48-43ca-9d55-78155e4c1749)




Optional - There is a "Success" image on the [S1] Catch That Pokemon scene that you can update to the Streamer.bot logo, or whatever you want



## **Streamer.bot Pre-Import Setup**

The following timers don't import to Streamer.bot so you will have to set them up:

- Pokemon Run Timer

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/18cecbb7-e775-47a2-bd69-9ef6bda427d4)


 
    a. Put the interval to 30-40 seconds
  
    b. Set to Disabled

- Poke Catch Game Appear Timer


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/24788b09-6d02-4791-958e-a5a8652d654c)


  
    a. I would recommend 150 seconds or more
  
    b. You can make it a random time amount with a specific range as well


## **Import Code** 



[Pokemon Catch Game.sb](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/blob/main/Pokemon%20Catch%20Game.sb)




## **Installation** 

In Streamer.bot select the Import button from the top left menu.

Drag and drop the file or copy the text from the file and paste all the text into the Import String field.


There should be 37 actions and 13 Commands.



![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/5f44bd65-7825-4dd6-8410-a3f4e2bf24c0)





## **Configuration**


### Assign Timer Triggers in Streamer.Bot

1. `3 (Timed Action) - Poke Catch Run Away Action` - add the timer trigger of “Pokemon Run Timer”
(example of where to find the trigger)

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/9329421b-6682-4cba-abbe-92e24bcf1fe4)



2. `3 (Timed Action) - Pokemon Catch Appeared!`  - add the timer trigger of “Poke Catch Game Appear Timer”
(example of what this trigger will look like. The other will be similar with the appropriate name)

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/7b007754-8185-485c-a586-e2873e8fb3c7)




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


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/76927c2e-3d9f-444f-847c-04c5678aeed3)




Once you are done, right-click the `Test` trigger and test it. 


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/32a45b0d-1d88-4610-83d7-ddac4b1500ee)




If you hear the sound of a successful Pokeball catch and the toast notification looks correct, then it worked! This will assign the paths to global variables so the rest of the actions can work.



### Assign Timers in Sub-actions

There isn’t a way to import Timers yet so we have to set these up by opening the TImer sub-action and selecting the timer


1. `5 (Background Timer State) Disable Poke Catch Game Appear Timer` - Timer (Poke Catch Game Appear Timer :: Disabled)
2. `5 (Background Timer State) Disable Pokemon Run Timer` - Timer (Pokemon Run Timer :: Disabled)
3. `5 (Background Timer State) Enable Poke Catch Game Appear Timer` - Timer (Poke Catch Game Appear Timer :: Enabled)
4. `5 (Background Timer State) Enable Pokemon Run Timer` - Timer (Poke Catch Game Appear Timer :: Disabled)

(double-click and select the correct timer for each)

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/b9e23146-7f2e-4517-8523-a711eb29ff04)



### Pokedex Setup


By default, only a message will be sent in chat with the pokedex completion number and % complete. There are two additional optional ways for viewers to see their pokedex


1. Discord Webhook - You can have the screenshot sent to a discord channel by setting up the webhook address in the “Show Pokedex Gen #” actions and enabling the sub-action


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/ec9e7e58-eaa5-4aef-90b4-6124eebaa538)




*  Make sure to do this for ALL 3

* Only update the webhook name and the webhook address. Leave the majority of the content and image as is



2. Pokedex scene appearing in OBS - You can have the images of the caught pokemon show up on screen by enabling the two OBS Source Visibility sub-actions in each “Show Pokedex Gen #” action


### OBS Audio Note


By default the sound of the pokemon cry is set to play in OBS through your Monitor ONLY, no output. Depending on your sound settings in OBS you may want to update this if you like.




### Gen 1-3 Settings
By default it has Pokemon randomly appear from Gens 1-3 (#’s 1-386) but you can change it so that it selects a smaller range by changing the `Random Number between…` sub-action on the `3 (Timed Action) - Pokemon Catch Appeared!` & `5 (Background Action) - Pokemon Catch Appeared! (Redeem)` actions.


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/a3e61f95-2440-4fb4-ad3f-92efcf67d3f5)




And the `Set argument %minimum%` and `Set argument %maximum%` and `Set argument minimum` sub-actions on the `5 (Background Action) - Check Pokemon Range Limit` action.


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/372c8998-adb6-4cfc-988b-93714568f41b)




### Difficulty Settings
If you feel that pokemon are TOO EASY to catch or TOO DIFFICULT you can go into the code and change the number.

On the `5 (Background Action) - Poke Catch Action` go to the “Execute Code (Determines if Pokemon was Caught) sub-action and double-click


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/dd134a58-9e15-46e7-b2aa-c0b25f9b63e3)




Find the number “160” in the code and change it lower if you want it to become easier, or higher if you want it to be more difficult to catch the pokemon

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/b4998ea8-9bf9-4995-a6eb-c6160ba8f6b0)




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

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/b8b7076d-9411-4a7f-aa90-f2da0337be4a)




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


Remember that they can only assign a Pokemon if they have caught it.

Also, If the pokemon is already assigned to a slot, they will need to assign a different pokemon first before they move it to a new slot




## **Manual Actions**
If needed there are two actions you can use to update slots or the Pokedex

### Manually Assign Caught Pokemon
By "testing" the trigger in this action, you can set a Pokemon as "caught" for a user.
- Make sure to have their User ID ready

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/2df34f11-10b0-4363-afc4-7f8ce75699c6)



- Make sure you know what Pokedex ID you want to use

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/aa5a2cbb-b7d7-4786-9906-e5a0b7db9b2c)




Then enter the details in the input windows.

Their pokedex will update the next time they catch a Pokemon, but they will be able to assign it to their party.

### C# Compiler
Make sure to add System.Core.dll to the C# compiler within Settings > C# Compiler > Common References > Right-Click > Add reference from file...


![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/2d038b77-635d-49f6-b51b-3e199ae1945e)



![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/f26339ab-c28c-45e2-aa52-62e3c65b7b62)



This will help make sure all the C# code found in the sub-actions compiles.


### Transfer PokeSlot Numbers to New Slots and Pokedex
This is available for anyone who used the old system and will update everything from the old system's record.
To update the Pokedex records, "test" the trigger in this action.

![image](https://github.com/Haunter56/SB-Poke-Catch-Game-YT/assets/107263697/e654d5fe-88f7-4cb9-8dc9-4c9a8f032e54)




It will NOT update the old system record, so use it only once, and only use it before implementing the new system LIVE



## Contributors

Idea for the game from [Shane Alan Gower](https://www.youtube.com/@ShaneAlanGower)

Created and Designed by  [Haunter](https://www.youtube.com/channel/UC9qO6-NFvWwhde5o2B_DMzQ) 👻

Downloads from [veekun](https://veekun.com/dex/downloads)
