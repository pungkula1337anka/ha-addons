# Home Assistant Add-on: 🦆 **duck-TV** 📺
<h1 align="center">
<img src="https://github.com/pungkula1337anka/duck-TV/blob/main/ducktv.png?raw=true" width="200" height="200"  />

<br><br>



</h1><br>

## What is duck-TV?

duck-TV is a super easy way to power-up your Chromecast and give it voice controlling capabilities. <br>
The duck-TV Addon can be used to control all kinds of media! <br>
<br>
🦆 Quack and play, no delay, <br>
🗑️ Clicks and taps? A thing of the past, <br>
🎙 Just speak up, and have a blast!
<br><br>
 


## 🦆 __Installation__ <br>


- **1: Add duck-TV Addon Repository** <br>
Add this repository to your Home Assistant OS instance:

`https://github.com/pungkula1337anka/ha-addons`

Then install the duck-TV Addon.<br><br>

- **2: Install the official DuckDNS Addon** <br>
Follow the DuckDNS official documentation.. <br>
Make sure to create two domains on [DuckDNS](https://duckdns.org). <br><br>

- **3: Configure duck-TV Addon** <br>
Define your new duckDNS domain & auth key in the `configuration` tab. <br>
Make sure to set your media folders for all the different media types. <br>
Setting your Assist language will automatically create a custom sentence yaml file for you. <br>
__If you wish to edit this file to change how you trigger the different features of this Addon, <br>
you can find the file in `/config/custom_sentences/<language_code>/duck-TV.yaml`.__

__yay__ <br>
  - 🎉 _congratulations! 🎉 you can now control_ <br>
    - _your media like a pro voice ninja!_  <br>
<br><br>

# __Full media control With Assist__ <br>

duck-TV utilizes the portability of Chromecast and the power of LibVLC to broadcast your local media to your devices. <br>
The difflib module is used to maximize your search potential and to create an __lightning fast__ "fuzzywuzzy" alike search effect, which can be clearvly used<br> 
especially when spaking in a language other than your Assist pipeline defaults. <br>
This allows for (most likely) calling an artists name or song title thats not in your native language. <br>
Even if the STT generates the wrong word, the addon will still _(try to)_ point you to the right directory path.<br>
A correction function is also implemented as fallback to ensure as high success rate as possible for your voice commands. <br>
All search results are stored in temporary .m3u files when being sent to your media player to simplify the playback process as much as possible. <br><br>
The addon comes with custom sentences, combined these has every possible command you could ever think off,  to control your Android TV's or Media boxes. <br>
<br>
Due to Chromecast limitations a https domain is required to be able to stream. <br>
duck-TV provides a [Caddy]() Reverse Proxy on your /media directory. <br>
DuckDNS is used to dinamically update your IP adress. <br>
<br>

_Example usage:_
```
- "play tvshow family guy"
- "play movie godzilla"
- "play channel 6"
- "play artist the rolling stones"
- "play song death to all but metal"
- "play music"
- "play youtube funny cats"
- "play podcast self hosted"
- "add this song to my playlist"
[...] and many more.
```
<br>

__Available Media Types:__

1. 🎬 __YouTube__  <br> 
Plays <search_query>'s closeest match on YouTube. <br>
Specify a `remote.*` entity. _(not `media_player.*`)_ <br>
_Requires API key._ <br>

2. 🎙️ __Podcast__  <br>
Fuzzy searches a Podcast directory, lists all files in that directory, orders them after creation date. Sends them to your HA media player for playback.
I use the container based service [Podgrab](https://github.com/akhilrex/podgrab) to automatically download new episodes.  
And this [PythonPodCleanup](https://github.com/pungkula1337anka/Voice-Stuff/blob/main/PythonPodCleanup.md) script to automatically  remove old episodes.  

3. 🔀 __Jukebox__  <br>
Shuffles & randomizes 150 songs from your music directory. <br>
Sends them back to your media player remote for playback. <br>

4. 🎵 __Music__ <br>
Fuzzy searches your music directory for an artist (folder) of your choice. <br>
Lists all files in that folder and creates a temporary playlist which are shuffled and sent back to your HA media players remote entity. <br>

5. 🎵 __Song__  <br>
Fuzzy searches your music directory and all its subdirectories for a song. <br>
The closest matches compared to your search query is stored in order of closest_match ratio. <br>

6. 📽️ __Movie__ <br>
Fuzzy searches for a movie title (folder in your movie directory). <br>
Lists all file inside that folder, order them after filepath name, path gets stored in the temp file sent to remote entity id. <br>

7. 📖 __Audiobook__  <br>
Fuzzy searches your audiobook directory for a folder. <br>
Lists all files in that folder, order them by filepath name and stores in a temporary playlist file casted to your media player.<br>

8. 📹 __OtherVideos__ <br>
Searches for a file in your othervideos directory. <br> 
Just like everything else its processed into a m3u file and sent to a `remote.`

9. 🎵 __Musicvideos__ <br>
Searches your musicvideo directory, for an artist (folder). <br>
list all files, shuffles & randomizes the m3u order before sending for playback. <br>

10. 📺 __TV__ <br>
Searches your TV directory for a TV Show (folder).
Lists all files in that directory and all its subdirectories, shuffles them all and randomizes order. <br>
Sends them all in a .m3u file to your `remote` entity id.

11. 🎼 __Playlist__  <br>
Specify full playlist filepath in search query. _(or define default playlist)_ <br>

12. 🎼 __Add__  <br>
Add currently playing song to your default playlist. <br>


13. 🗞️ __News__ <br>
Define your newscasts RESTful API's in the Python file. <br>
If the newscast items has not been heard before, they will be played. _(if played before, they are skipped)_ <br>
The script stores some data about played items in a .txt file in your config directory, <br>
dont worry though, the Python wont let it get big and grow strong. <br>

14. 📡 __Live-TV__ <br>
Simply define your Live-TV http URLs in the python. <br>
You can then call a channel by saying `play channel 5`. <br>

 
<br> 

__Additional Media Player Commands:__

__Volume Control__  <br> 
Increase/Decrease volume by saying `up` or `down`.<br>

__Next Track/Episode__  <br> 
Simply say `Next`.<br>

__Previous Track/Episode__  <br> 
`Previous` is the word. <br>

<br>


<br>

## 🦆 __troubleshooting__ <br>


- **More information will come, please be patient.** <br>


<br><br>


<h1 align="center">
<br>
 
 __🎈 enjoy 🎈__ 

</h1><br><br>
