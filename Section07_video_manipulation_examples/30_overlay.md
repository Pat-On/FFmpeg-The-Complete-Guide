# Overlay
- putting video or image one on another




ffplay bullfinch.mp4 -v error -an -top 0 -y 875

ffmpeg -v error -y -i bullfinch.mp4 -i ffmpeg-logo.png -filter_complex "overlay" out.mp4 && ffplay out.mp4 -v error -an -top 0 -y 875

ffmpeg -v error -y -i bullfinch.mp4 -i ffmpeg-logo.png -filter_complex "overlay=x=main_w-overlay_w-50:y=50" out.mp4 && ffplay out.mp4 -v error -an -top 0 -y 875

ffmpeg -v error -y -i bullfinch.mp4 -i ffmpeg-logo.png -filter_complex "[1:v]colorchannelmixer=aa=0.4[transparent_logo];[0:v][transparent_logo]overlay=x=main_w-overlay_w-50:y=50" out.mp4 && ffplay out.mp4 -v error -an -top 0 -y 875

ffmpeg -v error -y -i bullfinch.mp4 -i ffmpeg-logo.png -filter_complex "[1:v]scale=-1:100[smaller_logo];[0:v][smaller_logo]overlay=x=main_w-overlay_w-50:y=50"  out.mp4 && ffplay out.mp4 -v error -an -top 0 -y 875

ffmpeg -v error -y -i bullfinch.mp4 -i ffmpeg-logo.png -i tux.png -filter_complex "[1:v]scale=-1:100[smaller_logo];[0:v][smaller_logo]overlay=x=main_w-overlay_w-50:y=50[after_one_logo];[after_one_logo][2:v]overlay=W-w-50:H-h-50" out.mp4 && ffplay out.mp4 -v error -an -top 0 -y 875

ffmpeg -v error -y -i bullfinch.mp4 -i ffmpeg-logo.png -i squirrel.mp4 -filter_complex "[1:v]scale=-1:100[smaller_logo];[0:v][smaller_logo]overlay=x=main_w-overlay_w-50:y=50[after_one_logo];[2:v]scale=-1:400[smaller_squirrel];[after_one_logo][smaller_squirrel]overlay=W-w-50:H-h-50" out.mp4 && ffplay out.mp4 -v error -an -top 0 -y 875
