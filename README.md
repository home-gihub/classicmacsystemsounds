# classicmacsystemsounds
Mac classic system sounds in wav format
Theese were grabbed from https://mac-classic.com/downloads/system-sounds but they made it so hard to get the actual system sounds
## how i converted them
1. go to https://mac-classic.com/downloads/system-sounds and download "Original Mac OS Sound Files (Including .WAVE formats)"
2. go to https://www.webutils.pl/index.php?idx=binhex and unpack the `.hqx` file you just downloaded
3. go to https://convert.guru/sit-converter to convert the `.sit` file into a `.zip`
4. extract the zip and go into the directory with the `.wave` files (why not wav)
5. convert the `.wave` files into `.wav` files using this batch script (ffmpeg needed)
```
FOR /F "tokens=*" %G IN ('dir /b *.wave') DO ffmpeg -i "%G" -acodec pcm_f32le -ar 44100 "%~nG.wav"
```
6. profit
