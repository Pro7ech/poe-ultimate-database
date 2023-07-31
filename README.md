
# PoE-Ultimate-Database

## Introduction

 Here we will manage the excel sheet and scripts to host the database made by pathofmatth.

## Required

AutoHotKey: https://www.autohotkey.com/

Google Drive App: https://www.google.com/drive/download/

## Setting up the Google Drive

Download the google drive application and set it up to have a local folder synchronized (e.g. `C:\poe\upload`).

This folder is where the result of the local script will be exported. It will be synchronized on the cloud and shared on your google drive, enabling the scripts of the excel sheet to access the data.

## Setting up the Spreadsheet

Go to: https://docs.google.com/spreadsheets/d/18WQBtmmPk7XfFnOnBb0rGN2Y7D5GFOTzD81YfdZr1vo/edit?usp=sharing -> `File` -> `Make a Copy`

Go to `Google Document` -> `<name of your excel sheet>` -> `Extensions` -> `App Scripts` and change in both `xeskeko script.gs` -> `function` -> `FolderName = <upload_google_drive_folder_ID>` (the `ID` of your shared local folder on Google Drive)

NOTE: is the excel sheet automatically updated? Or should the scripts be ran manually by the user.

## Setting up the Scripts

Clone the repository into `C:\poe` (this is currently required as the paths are hard-coded into the code).

### Setting up info.ini

1) `League = <current_league_name>`.

2) `sesid = <POESESID>`. We recommend you to create a throw away PoE account and to log in with remember my credential. To get the `POESESSID` press F12 on Firefox -> `storage`. If the script isn't updating data correctly, you might want to check that the account is still logged in your browser and that the `POESESSID` hasn't changed. This will notably happen often if your IP is dynamic.

3) `Filepath = <path_to_your_local_upload_synchronized_google_drive_folder>` (e.g. `C:\poe\upload`).

4) `time = <hours_before_data_is_updated`. You can speed this up based on how many proxies you have but 12/4/2/1 is solid to prevent errors or problems.

### Linking Reference Data

To generate queries and fetch the correct data, the scripts need base line information (e.g. currency names). This information is available in:

https://pastebin.com/pzrzCkMp (queries pt3)

https://pastebin.com/vydwA326 (queries pt2)

https://pastebin.com/hnhLqz26 (queries pt1)

https://pastebin.com/ewd7Hhnf (enchants)

https://pastebin.com/DMHvYZYc (keywords)

https://pastebin.com/ZdwnEZ7t (content creators)

1) Open your own pastebin account and clone these files to your own account (use the `clone`option).
2) Update the 3 urls (`queries pt1, pt2, pt3`) in `/scriptnew/itemnew.ahk`, the one url (`enchants`) in`/lab/lab.ahk` and last 2 url (`keywords` & `content creators`) in `youtube/meta.ahk`.

Note: PoEStack NEEDS to work. No PoEStack = no data. So good luck dealing with Zach, or have someone else build PoEStack.

### Setting up Proxies

Proxies are recommended to not be limited by the API rate limit. 15 to 20 proxies are enough to have real time data 24/7. You will also need a server to run the script 24/7 (e.g. your PC 24/7 online).

You can get your own proxies wherever you want (e.g. https://www.sharedproxies.com/).

Copy past the IPs of your proxies in `proxy list.txt` following the same the format of the example. It is important to have the ports!

If the proxies require a login/password, it can be setup at the end of `/scriptnew/itemnew.ahk`.

### Running All Scripts

To run all scripts launch `upload.ahk` and all scripts will turn on, scripts will auto-restart if they fail after after a few minutes.

### Stopping All Scripts
The `killswitch.bat` file is to stop all scripts. This is useful early league when website keeps going down, the scripts will just throw constant pop-up errors if you let them run otherwise. 

NOTE: THIS SEEMS TO NOT WORK ATM.

### Issues & Others

Honestly if you have any other issues... You're going to have to figure it out on your own, because neither myself or Xeskeko will be willing
to put much more time into this. 

Shout-out to Xeskeko for being an absolute legend, building the scripts, the excel sheets, the formulas... Everything. 

Good luck!

The "error.txt" file in the "poe" folder will let you know if any of your proxies is acting up or if any specific script is acting up. 

A simple restart of that script will typically fix everything alongside delete the .txt file with it's data. (in the shared folder)
