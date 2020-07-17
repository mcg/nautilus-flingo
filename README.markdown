A [nautilus-script](https://help.ubuntu.com/community/NautilusScriptsHowto) that enables Nautilus to "fling" video to a [Flingo](http://flingo.org) enabled device, such as Vizio televisions or the Western Digital TV Live Hub.

# Prerequisites
 - You will need a web server that has access to your media repository.
 - pynotify

# Installation
- Clone this repo 
- Copy the "Fling to Device" script into your ~/.gnome2/nautilus-scripts directory.
- Edit the script changing...
    - host = "SOMELOCALHOST" <-This is the IP address or host name of the local machine hosing your media files.
    - port = 80 <- This is the port of the web server hosting your media files.
    - base_uri = "file:///PATH_TO_MEDIA" <- This is the path on the local file system to your media files.
    - base_location = "WEB_LOCATION_OF_MEDIA" <- This is the path from the web to your media files.
    - Setup a path in your local web server that points to your media files(this is the base_location).
 
# Example Config
- My media files live in /home/share/media/movies
- I will serve these files using Apache from the URL of http://bigserver.lan/media
- In Apache I have setup an Alias directive as:
    - Alias /media /home/share/media/movies
- My script config looks like:
    - host = "bigserver.lan"
    - port = 80
    - base_url = "file:///home/share/media/movies/"
    - base_location = "media/"

# How it works
Select some video files in Nautilus that live in your "base_uri", right click, then Scripts->Fling to Device. The selected videos should appear in your device queue and be playable if they are a supported type/codec.
