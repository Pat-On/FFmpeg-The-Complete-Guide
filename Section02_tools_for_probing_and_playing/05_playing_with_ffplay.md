# Playing with ffplay

- this is very basic media player 

`ffplay bullfinch.mp4 -v error`

---

`ffplay bullfinch.mp4 -v error -x 600 -y 600`

`ffplay bullfinch.mp4 -v error -x 600 ` - it is going to auto-calculate

`ffplay bullfinch.mp4 -v error -x 600 -noborder`

`ffplay bullfinch.mp4 -v error -x 600 -top 0`

---

`ffplay bullfinch.mp4 -v error -x 600 -top 0 -fs `

`ffplay bullfinch.mp4 -v error -x 600 -top 0 -fs  -an` - disabled audio

`ffplay bullfinch.mp4 -v error -x 600 -top 0 -fs -vn ` - disabled video

---

`ffplay bullfinch.mp4 -v error -y 600 -loop 0`

`ffplay bullfinch.mp4 -v error -y 600 -showmode waves`


---

short-cuts

- m (mute)
- w (audio visualization - video)
- s (proceeding one frame at the time)
- arrows left right - 10 second jumping
- arrows up and down - 1 minute jumping
- esc - close window


--- 

Can play videos, images, music

Can play from the URL link

ffplay https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/1080/Big_Buck_Bunny_1080_10s_10MB.mp4