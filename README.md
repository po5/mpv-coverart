# mpv-coverart

This script is for automatically loading external coverart files into mpv media player as additional video tracks.

## Valid Coverart
The script will automatically search the various scan locations for valid coverart. By default this will be all image files with the specified file names; names and image extensions can be modified through the config file. By setting the list of names to an empty string any image file in the scan locations will be loaded, by setting the list of image extensions to an empty string any file with the right name will be loaded. Naturally, it's a bad idea to disable both filters.


## Scan Locations
By default the script will search the directory of the currently played file for valid coverart. However, if the file system is unnavailable (when playing a network file), the script will then also search the current playlist, but still require that the file has the same directory. Both file system scanning and playlist scanning can be disabled in the config file.

Through config options scanning of the parent folder for the current file can also be enabled. The requirements that the file system must be unavailable for the playlist to be scanned, and the subsequent directory requirements, can also be disabled.


## Scan Conditions
By default the script only searches for coverart if the current file is detected to be an audio file. An audio file is defined as one where the first entry in the track list is an audio track, or is tagged as coverart. The script can be changed to always scan for coverart in the options.


## Placeholder
This script supports loading a placeholder image when coverart is not found. This can be useful for people who don't like thier music running in the terminal, but also dislike the default black box that mpv player shows.


## Misc Behaviour
If --audio-display=no is set then this script will not load any coverart. If --vid=no is set then this
script will load external coverart, but will not select them by default. Any other value for vid will only
properly select internal coverart, though you might get lucky and have it select the right track by chance.


## Other Functionality
I've thrown a few other small features into the script that may be useful:

### Skip Coverart
When this is enabled the script will automatically skip any valid coverart files in the playlist, this can be very useful when loading a whole folder directly.

### Decode URLs
When this is enabled mpv will attempt to undo URL percent encoding for the specified protocols. This is probably only useful for the ftp protocol, for which ffmpeg does not support percent encoding.

## Configuration
Look at coverart.conf for the full list of options. This config file can be placed into the script-opts folder inside the mpv config directory to be loaded automatically.