## Introduction
StockpileBot is a discord bot used for stockpile management for the MMO wargame Foxhole.
The bot’s main functions are centered around tracking stockpiles and performing query and data visualization actions on the gathered data.

## Bot Permissions
The bot only needs 3 permissions:
Read messages - needed for reading query & plot messages
Send messages - self-explanatory
Attach files - needed for sending images of item plotting results

## Setting permissions
When the bot is first added, the server owner needs to assigned a admin role.
After the role is assigned, admins can use /settings to set permissions to individual functionalities of the bot.

## Command Tree Overview
```
settings
priorities ───┬─── view
              ├─── add
              ├─── remove
              ├─── generate
              └─── update
targets ───┬─── view
           ├─── edit-presets
           └─── set
tech ───┬─── view
        ├─── set-starting
        ├─── add
        ├─── remove
        ├─── reset
        └─── auto-tech
stockpiles ───┬─── edit
              ├─── upload
              ├─── list-codes
              ├─── code-button
              ├─── overview
              └─── verify
transport-tasks ───┬─── generate
                   └─── update
refresh-spreadsheet
spreadsheet-link
info
```


## Modules
### Priorities
This module is used for generating production priorities, a list displaying most needed items
#### view
Displays all items to be checked when generating the priorities.
#### add
Add an item to be checked.
#### remove
Remove an item from the list of checked items.
#### generate
Generate a message with the list. These messages update every 4 hours, so try not to spam them. Items that are in the checked items list, but not teched will not be added to the list

![](/assets/production_prios.png)

#### update
Manually update the currently active priorities message.

### Settings
This command is used for viewing and editing the bot's settings.

### Targets
This module is used for tracking and setting the target amounts of items, expressed in crates
#### view
View the target amounts.

![](/assets/targets.png)

#### set
Set a target amount for an item.
#### edit-presets
Change or add targets presets.

### Tech
This module is used for tracking and editing the tech status.
#### view
View the tech. The T column stands for currently teched items, and the S column stands for items that are starting (Day 0) tech.

![](/assets/tech_view.png)

#### set-starting
Set if an item is starting (Day 0) tech
#### add
Add an item to the currently teched items list
#### remove
Remove an item from the currently teched items list
#### reset
Reset the tech to only the starting tech items. You should only use on the start of a new war.
#### auto-tech
Automatically marked items as tech depending on their presence in the spreadsheet.

### Stockpiles
This module is used for editing tracked stockpiles/depots and uploading the stockpile data to the linked spreadsheet.
#### view
View and edit/delete tracked stockpiles/depots

![](/assets/depot_list.png)

#### upload
Opens a modal allowing the user to upload their MapData.sav file to the linked spreadsheet.
#### list-codes
Lists all codes that are available to you.
#### code-button
(Admin-only) Generate a button that runs list-codes when clicked on
#### verify
Checks the validity of all depots
#### overview
Allows for mass queries of items.

### Transport Tasks
This module is centered around the transport tasks message. Transport tasks are a collection of auto-generated tasks telling players where to move different items.
#### generate
Generate the transport tasks message. Limited to 1 per server.

![](/assets/transport_tasks.png)

#### update
Update the currently active transport tasks message.

#### Querying & Plotting
Querying items and plotting the amounts over time is available via message commands.

To query an item, simply type "How many <item> do we have" in any text channel which the bot has access to. You will receive the query results as a response.

![](/assets/query.png)

To plot an item, type "plot <item>" and you will receive the plotting result as a response.

![](/assets/plot_item.png)

If you type "plot all", the result will instead plot by all items in depots.

![](/assets/plot_all.png)


## Data Sources
The bot can currently only read/write data from/to Google Sheets spreadsheets. The spreadsheet to be used must be either viewable/editable by everyone, or the bot’s service account (stockpile-bot@stockpile-bot.iam.gserviceaccount.com) needs to be allowed to view/edit the spreadsheet.

It is recommended that the spreadsheet is cleared/changed on every start of war as to maximize performance.

## Disclaimer
All per-server data, such as settings, depots including __depot passcodes__ are stored __unencrypted__ at this point in time.
I can guarantee that I WILL __NOT__ read the data unless requested by the respective server owner.

## Credits
Bot created by: [UCF] Swiftyjax (discord: swiftyjax)

Special thanks to: 
[UCF] ...
[UCF] Vexx
[UCF] Biggus Flickkus
		
