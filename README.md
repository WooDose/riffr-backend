# riffr-backend
UVG-CC30622020201 Project backend. riffr is ideally the final name. Based on [spooky309](https://github.com/Spooky309)'s idea.

## Libraries required
Made on Python Django; I will update which version soon.

(tbd)



## Description
Site that allows you to upload small snippets of midi and displays them in standard notation, allowing them to be played. Supports all GM instruments.
Idea is to upload a midi, note the key and give any info about it, including feeling, time signatures, tunings...
You can use it to store all the things you write so you can go into it and pull stuff out if you have to, e.g. "I'm writing this song in A Minor, I can't think of what to put next. Oh I know, I'll look at my riffr vault and see what's there in A minor"
Can be public or private, can be downloaded if public.
Has a search function with keys, genres, time signatures.

## Base requirements
* Login/Logout
  - Username, password, admin status

* Uploading files
  - Allows user to upload a MIDI file containing as many tracks (filesize limit could be figured out at a later date, probably <1M)
  - Data that we want:
  - Requires user input:
    - Name
    - The actual midi file
  - Optional user input:
    - Any custom tags (separated with colon)
    - One or more keys (root+tonality), multiple keys will assume polytonality
  - Can be found by looking at the midi file
    - Time signatures (if none in file, assume 4/4), also store what bar they start on
    - Length (seconds and bars)
    
    (NOTE: Playback of midi and other things related to more in-depth functions are NOT included in the version meant for July 02. That would be a nice bonus though.)
    
* File Page:
  - Displays all known info about the file
  - Allows download of file, or removal/editing of metadata if user is owner or admin

* Search Page:
  - Searches names and tags, returns list of files with their metadata and a link to their File Page

* Profile Page:
  - Displays all uploaded files, with powerful filters for time signatures, different keys (including the option to filter multiple keys at once, i.e. display A Minor AND C major)
  - Allows for DMs
  - Owner or admin can close account or delete/edit metadata from here.
