# StockpileBot Documentation


## Introduction
StockpileBot is a discord bot used for stockpile management for the MMO wargame Foxhole.
The bot’s main functions are centered around tracking stockpiles and performing query and data visualization actions on the gathered data.

## Bot Permissions
The bot only needs 3 permissions:
Read messages - needed for reading query & plot messages
Send messages - self-explainatory
Attach files - needed for sending images of item plotting results

## User Permission Levels
There are 3 permission levels that the bot uses: Everyone, NCO and Officer.

Querying & plotting commands are available to everyone as they are intended to be public; 
If there is a need to block this command, disallow the bot from seeing the channels in which you do not want it to respond.

The NCO permission level commands fall under 4 categories:
Those that display some configurations, such as the /targets view command
Those used for updating unlocked tech
The /stockpiles upload and /refresh-spreadsheet commands, used for uploading stockpile data and keeping cached data up-to-date
QOL commands, such as /spreadsheet-link

Officers have access to all commands.

## Command Tree Overview
```
priorities ───┬─── view
              ├─── add
              ├─── remove
              └─── generate
settings ────── view
targets ───┬─── view
           └─── set
tech ───┬─── view
        ├─── set-starting
        ├─── add
        ├─── remove
        └─── reset
stockpiles ───┬─── view
              └─── upload
refresh-spreadsheet
spreadsheet-link
info
```


## Modules
### Priorities
This module is used for generating production priorities, a list displaying most needed items
#### View
Displays all items to be checked when generating the priorities.

#### Add
Add an item to be checked.
Remove
Remove an item from the list of checked items.
Generate
Generate a message with the list. These messages update every 4 hours, so try not to spam them. Items that are in the checked items list, but not teched will not be added to the list

### Settings
This module is used for viewing and editing the bot’s settings.
View
View (and edit) the settings.

### Targets
This module is used for tracking and setting the target amounts of items, expressed in crates
####View
View the target amounts.

####Set
Set a target amount for an item.

### Tech
This module is used for tracking and editing the tech status.
####View
View the tech. The T column stands for currently teched items, and the S column stands for items that are starting (Day 0) tech.

####Set Starting
Set if an item is starting (Day 0) tech
####Add
Add an item to the currently teched items list
####Remove
Remove an item from the currently teched items list
####Reset
Reset the tech to only the starting tech items. You should only use on the start of a new war.

### Stockpiles
This module is used for editing tracked stockpiles/depots and uploading the stockpile data to the linked spreadsheet.
####View
View and edit/delete tracked stockpiles/depots

####Upload
Opens a modal allowing the user to upload their MapData.sav file to the linked spreadsheet.


####Querying & Plotting
Querying items and plotting the amounts over time is available via message commands.

To query an item, simply type “How many <item> do we have” in any text channel which the bot has access to. You will receive the query results as a response.


To plot an item, type “plot <item>” and you will receive the plotting result as a response.


If you type “plot all”, the result will instead plot by all items in depots.


## Data storage
The bot can currently only read/write data from/to Google Sheets spreadsheets. The spreadsheet to be used must be either viewable/editable by everyone, or the bot’s service account (stockpile-bot@stockpile-bot.iam.gserviceaccount.com) needs to be allowed to view/edit the spreadsheet.

It is recommended that the spreadsheet is cleared/changed on every start of war as to maximize performance.



## Credits
Bot created by: [UCF] Swiftyjax (discord: swiftyjax)

Special thanks to: 
[UCF] …
[UCF] Vexx
[UCF] Biggus Flickkus
		
