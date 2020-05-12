This is the folder that will be maintained the most.

**Overview:**

1. Use a separate directory to test these files until you are comfortable with their performance. Remove any file(s) that have the same name and target extension of what you're working with. 
2.  There are 2 types of files here: Directory and FileDrop
	a. Directory- Reads a directory and converts all file(s) (that match the extension) to the destination.
	b. Filedrop-Allows a drag and drop onto the program in order to convert that one file.
3.  The only exception to rule #2 would be the VideoRedo Project version 5 to version 2 for Kodi. Since both files use the same extension, I decided to add v2 to the end of the filename. I wasn't sure what else to do. 
4. The EDL,Vrj,and Comskip files specification and descriptions are found on the Kodi and XBMC Wikis. I tested the Vrj and EDL files on several videos. From my experience, the cut function is unreliable in Kodi on EDL and Vrj files. The commercial skip and mute work great for me. I couldn't get bookmarks to work for EDL and Vrj files, but it could have been operator error, bad code, or bad output file.
Again, I used the Kodi Wiki to give me guidance on what the output file for Kodi should look like. I use Kodi Leia 18.6 on the Raspberry Pi 4 to test the Kodi files.

**Specifics:**
**Kodi Edl to Potplayer Pdf-** This accepts the Kodi Edl time formats of 123.0, 123, 2:03, and 2:03.1 formats for time. The frame format of #1234 isn't supported. Bookmarks are supported. 

**Potplayer Pbf to Kodi Comskip With 2997 fps**-This attempts to convert between time and frames. Since I don't understand timecode and dropped frames, I just divided frames by 29.97 to get seconds. If your video is something other than 29.97fps or maybe 30fps, this won't be accurate. This doesn't check videos for fps, but I may pursue ways to check and import fps but not now.

**Potplayer Pbf to Kodi Edl**-Kodi Edl output format is like 00.0 in seconds with 1 decimal place. Mute isn't supported because Potplayer doesn't have mute. Bookmarks are supported

**Potplayer Pbf to Zoomplayer Cut with All Cuts**- All playskips are converted to cuts in Zoomplayer. Bookmarks are converted to chapters and cuts and chapters are separated into 2 files in .cut and .zpchp extensions. Mute isn't supported.

**Potplayer Pbf to Zoomplayer Cut with Cut and Jump-** All playskips are converted to jump or cut. From my experience, any jump less than 2 seconds will probably have undetermined results. Therefore, any playskip duration less then 2 seconds is converted to a cut and >= 2 seconds will be a jump. Bookmarks are supported. Mute isn't supported.

**VideoRedo Vrj5 to Kodi Vrj2-** This converts VideoRedo version 5 to Kodi version 2 from the layout on the Kodi Wiki. I couldn't get the bookmarks to show on Kodi even though the layout looks correct in the output file. The cut scenes I know are working but have undetermined results. I don't intend to do anything with converting to VideoRedo version 5 since I don't know what's relevant in the file nor do I understand a lot of what is there.  

**Zoomplayer Cut to Edl no Scenemarks 0 1 3**-Cuts are converted to EDL cuts. Jumps are converted to EDL Commercial breaks. Mutes are converted to EDL mutes. Bookmarks aren't supported yet. 

**Zoomplayer Cut to Potplayer Pbf**-Looks for cut files and proceeds to look for its zpchp chapter file. Zoomplayer zpchp files aren't required. I don't intend to make a program that looks only for zpchp files.

**Srt to Zoomplayer cut**-This is my attempt to make a file that will find a list of words in srt subtitles and guess at the times those words were spoken and try to mute them. There are issues that arise with this in different areas. Because words are spoken at different speeds, it will be impossible to code a formula to accurately predict when words are spoken based on subtitle text. All of the words that are searched for come from http://www.bannedwordlist.com/ I removed some of the words due to my preference. The following files are optional for the user but not needed if you want to use my list:
1. replacewords.txt -This completely replaces the words on my list with another list. This requires 1 word per line
2. addwords.txt - This adds a list of words to my list. 1 word per line.
3. excludewords.txt - This tries to remove words that contain the words on the list but aren't those exact words. For example, the word 'hello' will be caught if the word 'hell' is searched for. My list is small so far because there are many exceptions and I've only looked at 2 srt files prior to posting this.

Feedback is greatly appreciated

More to follow.... 
