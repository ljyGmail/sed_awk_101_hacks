# 90 GAWK String Functions

tolower and toupper are available only in Gawk.
```
awk '{ print tolower($0) }' items.txt
101,hd camcorder,video,210,10
102,refrigerator,appliance,850,2
103,mp3 player,audio,270,15
104,tennis racket,sports,190,20
105,laser printer,office,475,5

awk '{ print toupper($0) }' items.txt
101,HD CAMCORDER,VIDEO,210,10
102,REFRIGERATOR,APPLIANCE,850,2
103,MP3 PLAYER,AUDIO,270,15
104,TENNIS RACKET,SPORTS,190,20
105,LASER PRINTER,OFFICE,475,5
```
