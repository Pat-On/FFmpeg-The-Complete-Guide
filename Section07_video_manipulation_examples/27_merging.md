# Merging - joining videos


## Commands:
vim list.txt
file 'bullfinch-5s.mp4'
file 'seagull-5s.mp4'
file 'squirrel.mp4'
ffmpeg -y -v error -f concat -i list.txt merged.mp4