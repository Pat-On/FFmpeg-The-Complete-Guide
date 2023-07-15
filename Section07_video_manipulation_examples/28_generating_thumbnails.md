# Generating Thumbnails






## Code:
ffmpeg -v error -i bullfinch.mp4 -vframes 1 bullfinch-poster-frame.jpg

ffprobe bullfinch-poster-frame.jpg -v error -select_streams v -show_entries stream=width,height

ffmpeg -v error -i bullfinch.mp4 -vframes 1 -vf scale=320:180 bullfinch-thumbnail.jpg

ffprobe bullfinch-thumbnail.jpg -v error -select_streams v -show_entries stream=width,height

ffmpeg -v error -i bullfinch.mp4 -ss 5 -vframes 1 -vf scale=320:180 bullfinch-thumbnail-at-5s.jpg

ffmpeg -v error -i bullfinch.mp4 -vf fps=1,scale=320:180 bullfinch-thumbnail-%02d.jpg
ls