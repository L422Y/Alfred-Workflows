This is a simple script that uses the Plex URL command to update your directory. 
You'll need to know the directory number of the section you want to update. 
You can get that information from the [Plex advanced wiki](http://wiki.plexapp.com/index.php/PlexNine_AdvancedInfo#Scanning_and_Refreshing_Sections)

All you need to do is edit the workflow where it says htpc to reflect the IP or DNS name of your plex server.
```
response="{query}"
if [ $response == "updatemovies" ]
then
  curl http://htpc:32400/library/sections/1/refresh?deep=1
	echo "Movie directory updating"
fi
```

Right now this is set for deep scanning, if you want to do a turboscan just remove
```
?deep=1
```
