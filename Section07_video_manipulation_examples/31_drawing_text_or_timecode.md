# Drawing Test or Timecode 

ffplay bullfinch.mp4 -v error -an -top 240 -y 835

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds:fontsize=48:x=100:y=100"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds:fontsize=h/2:x=(w-text_w)/2:y=(h-text_h)/2"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds:fontsize=h/2:x=(w-text_w)/2:y=(h-text_h)/2:fontcolor=green"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds:fontsize=h/2:x=(w-text_w)/2:y=(h-text_h)/2:fontcolor=#000000AA"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds:fontsize=h/2:x=(w-text_w)/2:y=(h-text_h)/2:fontcolor=#000000AA:enable='between(t,1,3)'"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=Birds:fontsize=h/2:x=(w-text_w)/2:y=(h-t*200):fontcolor=#000000AA"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=:fontsize=60:x=(w-text_w)/2:y=(h-100):fontcolor=#000000:timecode='10\:00\:00\:00':rate=30000/1001"

ffplay bullfinch.mp4 -v error -an -top 240 -y 835 -vf "drawtext=fontfile='c\:/Windows/Fonts/courbd.ttf':text=:fontsize=60:x=(w-text_w)/2:y=(h-100):fontcolor=#000000:timecode='10\:00\:00\:00':rate=30000/1001:box=1:boxborderw=15:boxcolor=#ffffff44"
