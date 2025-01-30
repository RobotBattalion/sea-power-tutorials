# How to Publish A Mission Modpack To Steam

## Assumptions
- You have authored one or more missions which are available at the following default location
    - Windows: `C:\Program Files (x86)\Steam\steamapps\common\Sea Power\Sea Power_Data\StreamingAssets\user\missions\user_missions`
- You will be creating a campaign with two missions
- Both missions contain briefing assets

## Creating Your Campaign folder

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



