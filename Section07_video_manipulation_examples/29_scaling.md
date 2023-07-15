# Scaling

- most common case
- resizing



# commands


ffplay -v error cow_4k.mp4 -an

ffprobe cow_4k.mp4 -v error -select_streams v -show_entries stream=width,height

ffmpeg -v error -y -i cow_4k.mp4 -vf scale=1280:720 cow_720p.mp4

ffprobe cow_720p.mp4 -v error -select_streams v -show_entries stream=width,height

ffplay -v error cow_720p.mp4 -an

ffmpeg -v error -y -i cow_4k.mp4 -vf scale=640:480 cow_480p.mp4

ffplay -v error cow_480p.mp4 -an

ffmpeg -v error -y -i cow_4k.mp4 -vf scale=-1:480 cow_480_aspect_preserved.mp4

ffmpeg -v error -y -i cow_4k.mp4 -vf scale=-2:480 cow_480_aspect_preserved.mp4

ffprobe -v error cow_480_aspect_preserved.mp4 -v error -select_streams v -show_entries 
stream=width,height 

ffplay -v error cow_480_aspect_preserved.mp4 -an

ffmpeg -v error -y -i cow_4k.mp4 -vf scale=640:480:force_original_aspect_ratio=decrease cow_480_aspect_forced.mp4

ffprobe -v error cow_480_aspect_forced.mp4 -v error -select_streams v -show_entries stream=width,height 

ffmpeg -v error -y -i cow_4k.mp4 -vf "scale=640:480:force_original_aspect_ratio=decrease,pad=640:480:(ow-iw)/2:(oh-ih)/2" cow_480_aspect_forced_and_padded.mp4

ffplay -v error cow_480_aspect_forced_and_padded.mp4 -an