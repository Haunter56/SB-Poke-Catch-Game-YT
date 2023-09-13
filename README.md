# SB-Poke-Catch-Game-YT
Poke Catch Game using Streamer.bot for YouTube


## **Description** 
[wrap="info"]  
This is a points system for YouTube. Viewers will be able to accumulate points by chatting regularly and then redeem their points to trigger actions you create in Streamer.Bot. **Updated for version 0.2.0**    
[/wrap]

[wrap="warning"]
Be aware that there is not a way to give points to lurkers as we don't have access to that through YouTube. Also, viewers will not get extra points for spamming chat.
[/wrap]

## **Resources** 

### OBS
Make sure your OBS has these two plugins. If you don’t, I have provided links to them.

[Source Copy Plugin](https://obsproject.com/forum/resources/source-copy.1261/)

[Move Transition Plugin](https://obsproject.com/forum/resources/move-transition.913/)

### Downloading Files

Download the Pokemon cries and Sugimori art from [veekun](https://veekun.com/dex/downloads) under "Other files"

[PICTURE GOES HERE]

Create a folder and unzip the folders you downloaded into the new folder. Take note of where those folders are.

In the `Sugimori art folder` make changes to the following images:
- `201.png` > delete the file (it's broken)
- `201-f.png` > change to `201.png`
- `386.png` > delete the file (it's broken)
- `386-[style of your choice]` > change the style you want to appear to `386.png`

Download this ZIP, unzip it, and put the folders in your folder you created as well:
- Catch Chance
- Sound Effects
- Text Names
- OBS Pokemon Scenes


## **Import Code** 

[YouTubePointsSystem.sb|attachment](upload://n0xwzaWJmuplTquifjx2gsssIOa.sb) (14.8 KB)




## **Installation** 

In Streamerbot select the Import button from the top left menu.

Drag and drop the file or copy the text from the file and paste all the text into the Import String field.

[wrap="info"]
There should be 17 actions and 6 Commands.
[/wrap]

![image](upload://yvzYxE4Lk8ptM7d2LOqFCuUqhnv.png)


## **Configuration** 


### C# Compiler
Make sure to add System.Core.dll to the C# compiler within Settings > C# Compiler > Common References > Right-Click > Add reference from file...

![image](upload://aY0obJyjPCwRxClvKCoIMy5hFtU.png)
![image](upload://ilUpTmBqdbXnjl1XzhfHyIhTY8l.png)

This will help make sure all the C# code found in the sub-actions compiles.

### Present Viewers
![image](upload://g2mFzxYLCVtem0Zm20fWf4qiIm0.png)


This will give viewers points every MINUTE. The slider is meant to select how many minutes of inactivity to no longer consider a chatter as "active". For example, 5 minutes means that if the Present Viewers event runs and the chatter hasn't been active for 5 mins 12 secs, then the chatter will no longer be receiving points every minute.

To adjust the points given every minute change the `%pointsPerMinute%` argument in the "Action - Present Viewers Trigger" action to the number value you want.

![image](upload://yLXvfmDUhUHYZbjljsfbjI6NP3.png)


### First Words
In the action "Action - First Words":
- Update/Add any users that you don't want triggering the "First Words" event.
![image](upload://rhSnFrgpjvNIdNtS4LfHe6wD4Iu.png)
- Update/Add any user IDs that you don't want triggering the "First Words" event.
![image](upload://6FKnC6rLtXpicbmWiNF698sbz1m.png)
- Update the points every chatter receives for chatting the first time each stream.

![image](upload://ybZJWMgn8R6bWoBmo3dkaMUdwj7.png)


## **Commands**


### Points Name and Command
The !setpointsname command sets the name of your loyalty points to whatever you want to call it. This is the format: 

```!setpointsname[space]["name"]```

```!setpointsname Coins```

In the !setpointsname command:
- Check the "enabled" box
- This command is only be for you because you will need to update the command for users to check their points balance if you ever change the name.
![image](upload://bHNExHksCn7lQPzwNORrRu32JFp.png)

- Use the command during a stream to update the name to whatever you choose.
![image](upload://5p9lJ0Nbo6f0tUSmqvuVh6zxBxv.png)

In the !points command:
- Check the "enabled" box
- Update the command to whatever points name you are using (if desired)
- You can also add a cooldown if you want to avoid people spamming the command
![image](upload://pg5VPstd8XN0TQTzhJYQuFKO72K.png)
![image](upload://xiZHHhRAHbJOD9hUBbOVaEiAdP1.png)



### Add and Set Points Commands
The !addpoints command adds points to the viewer listed. This is the format: 

```[command][space][username]+[# of points to add]```

``` !addpoints Haunter+100```

You can also use the @ symbol if you are on desktop

``` !addpoints @Haunter+100```

In the !addpoints command:
- Check the "enabled" box
- Update the command to whatever points name you are using (if desired)
- Update the Group Permissions to "Moderators"

![image](upload://aAN6eiY1FpgQI34Cgh4EBszrV2r.png)
![image](upload://axXvvS0OiqSeAo5sN49GHcXTiiS.png)

The !setpoints command adds points to the viewer listed. This is the format: 

```[command][space][username]=[# of points to set]```

``` !setpoints Haunter=100```

You can also use the @ symbol if you are on desktop

``` !setpoints @Haunter=100```

In the !setpoints command:
- Check the "enabled" box
- Update the command to whatever points name you are using (if desired)
- Update the Group Permissions to "Moderators"

![image](upload://aktpI6LppgBNX3ti12sIbdPkvKC.png)
![image](upload://qIAJnt1BgzAQK0uRNVk9d5oH6Sf.png)

[wrap="warning"]
PLEASE NOTE! - Due to the fact that YouTube does not require unique usernames, there is a small chance that two viewers with the same username are in your viewer records. If this happens the bot should send a message that there are duplicate usernames. They will have to change their username or get their points added another way.
[/wrap]

![image](upload://csAq17TLJZQS8ExQxZENsnV2Cgc.png)

[wrap="warning"]
Also, if you are trying to add/set points for a brand new user, you may have to click "Save" in Streamer.Bot if it says they don't exist yet.


![image](upload://kAm9JmdUSMQzcHiIjDyM5PyL2Le.png)
[/wrap]

### Shout-Out
The !so command puts a link in chat for the user who was shouted-out. This is the format: 

```!so [username]```

```!so Haunter```

In the !so command:
- Check the "enabled" box
- Update the Group Permissions to "Moderators"

![image](upload://pqwgZkPekaxQo36YoVHeg6efoG3.png)
![image](upload://zyVxzcCfdgVg1CD4igI8OtYl3oQ.png)

## Points Redeem
For each points redemption command you create do the following:
- Duplicate the action "Command - Sample Redeem Something YT (duplicate this)"
- Rename the action to whatever you like
![image](upload://nFlMz2CN9vBpGQ2T9I1N2WLLiOV.png)

- Update [this is your redeem name] in the "Set argument %redeemName%..." sub-action

![image](upload://i5b3wKj7Z6HDNUThyew4cSrEmeU.png)

- Add sub-action/s to the action

![image](upload://6MDElpL3vD44s2riwjdLWqEVZK7.png)

- Create a command for the new action and link the new action to the new command
- You can add the command trigger first by righ-click > Core > Commands > Command Triggered.

![image](upload://xQeH1bfK0BeDUBhr9CgjXRoKOl5.png)

- You can create the command in the dialog box if needed:

![image](upload://pQdooiMhe4NVxODMEryvzrKY2XM.png)

- It will take you to the command window for configuration

![image](upload://l2eCDXwGUb7tEqHpDonO8HnK57M.png)



## Contributors

Inspired by the original points system for Twitch by [VRFlad](https://www.twitch.tv/VRFlad)
Made for YouTube by  [Haunter](https://www.youtube.com/channel/UC9qO6-NFvWwhde5o2B_DMzQ)
