# How to Publish A Mission Modpack To Steam

## Assumptions
- You have authored one or more missions which are available at the following default location
    - Windows: `C:\Program Files (x86)\Steam\steamapps\common\Sea Power\Sea Power_Data\StreamingAssets\user\missions\user_missions`
- You will be creating a campaign with two missions
- Both missions contain briefing assets

## Creating Your Mod folder

This is the working folder you will be publishing to Steam. It is best to manage this folder outside of the user missions you will be sourcing. The directory tree follows a particular structure that reflects on how the mission(s) are displayed in the `Scenarios` select screen. `Sea Power` saves metadata and your missions as `.ini` files. Here are a few examples and how they display within the game. 

### Example: A single mission contained in a self-titled folder
```md
Shift Change
├── missions
│   └── Shift Change
|       └── Shift Change.ini
└── _info.ini
```

### Example: A named campaign with multiple titled missions
```md
Desert Spear
├── missions
|   └── Desert Spear
|       ├── Desert Spear.ini
|       ├── Desert Spear (Iraq).ini
|       └── Desert Spear (Night).ini
└── _info.ini
```

## Steps To Create Mod folder

1. In a managed location, create a folder named `The Missions`. This will be our campaign name.
2. Within the folder, create a file names _info.ini and open it in a text editor and save the following
```
[Language_en]
Name=The Missions
Description=A brief description of the campaign
```
3. Within the folder create a new folder named `missions`
4. Open the folder and create a new folder names `The Missions`
5. Open the new folder, this is where we will put both missions including their asset files.

## Importing a user mission into a Mod folder

6. Go to where you saved your user mission in Sea Power ( for this example `\user\missiomns\user_missions\Mission 1`)
7. Copy the `Mission 1.ini` to where we left off in Step 5
8. Go to the folder you saved your briefing assets. Copy every file into the same location you saved the mission ini.
9. (if applicable) Rename `LeftPane_en.xml` to something unique to the mission. ex: `m1_LeftPane_en.xml`
10. (if applicable) Rename `RightPane_en.xml` to something unique to the mission. ex: `m1_RightPane_en.xml`
9. Open the mission.ini, the top of the file should look something like this
```
[Debug]
DisableEnemyAIPlayer=True
[Language_en]
Name=Mission 1
Description=Shoot the enemy!
MissionBriefingAssetsDirectory=missions\user_missions\Mission 1\assets
MissionBriefingAssetsSearchPattern=*.png,*.jpg,*.bmp
MissionBriefingLeftPane=missions\user_missions\Mission 1\assets\LeftPane_en.xml
MissionBriefingRightPane=missions\user_missions\Mission 1\assets\RightPane_en.xml
```
10. Replace `\user_missions\Mission 1\assets` with `\The Missions`
11. Rename `LeftPane_en.xml` and `RightPane_en.xml` to the filenames you changed those files to.
12. Your mission file should look something like this after
```
[Debug]
DisableEnemyAIPlayer=True
[Language_en]
Name=Mission 1
Description=Shoot the enemy!
MissionBriefingAssetsDirectory=missions\The Missions
MissionBriefingAssetsSearchPattern=*.png,*.jpg,*.bmp
MissionBriefingLeftPane=missions\The Missions\m1_LeftPane_en.xml
MissionBriefingRightPane=missions\The Missions\m1_RightPane_en.xml
```
13. Repeat Steps 6-11 for every mission you want to add

See [example](./example-modpack-missions/) for reference

## Upload Mod Folder to Steam Workshop

1. Go to Steam > Library > Sea Power > Manage > Properties > Disable Steam Cloud
```
> [!IMPORTANT]
> It is important to disable Steam Cloud, as we need to copy the mod folder temporarily into the user 
> files that get backed up. If you dont, you will not be able to delete the files as they will keep 
> syncing back into the user folders.
```
2. Go into Sea Power and navigate to the user missions folder under StreamingAssets ex: `C:\Program Files (x86)\Steam\steamapps\common\Sea Power\Sea Power_Data\StreamingAssets\user\missions`
3. Copy your Mod Folder here
4. Open Sea Power
5. Go to Mod Manager
6. Select `Create a Mod` (or update existing if you are going over these steps again)
7. Add a title, description, and a thumbnail if you want to. Steam lets you update these fields from the Workshop
8. Pick the folder we added `\user\missions\The Missions` and click Open
9. I reccomend setting the publish to private for now
10. Upload your mod
11. Delete `\user\missions\The Missions` from your machine
12. Subscribe to your workshop item
13. Re-enter mod manager and your item should appear by it's title and description we added to the _info.ini
14. Check your mod and accept changes.
15. When SP re-loads go into scenarios and you should see your campaign `The Missions`, with two missions when you open the campaign folder.
16. When you are happy with the Mod, set it Public
17. Remember to turn Steam Cloud back on