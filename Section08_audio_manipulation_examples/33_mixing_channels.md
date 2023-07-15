# Mixing Channels
```sh
ffprobe -v error ch0.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json

ffmpeg -v error -y -i ch0.m4a -i ch1.m4a -i ch2.m4a -i ch3.m4a -filter_complex "amerge=inputs=4" one-stream-four-channels.m4a

ffprobe -v error one-stream-four-channels.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json

# amix
ffmpeg -v error -y -i ch0.m4a -i ch1.m4a -i ch2.m4a -i ch3.m4a -filter_complex "amix=inputs=4" one-stream-one-channel.m4a

ffprobe -v error one-stream-one-channel.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json

ffmpeg -v error -y -i ch0.m4a -i ch1.m4a -i ch2.m4a -i ch3.m4a -filter_complex "amerge=inputs=4,pan=mono|c0=c0+c1+c2+c3" pan-mono.m4a

ffprobe -v error pan-mono.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json

# mono chanel
ffmpeg -v error -y -i ch0.m4a -i ch1.m4a -i ch2.m4a -i ch3.m4a -filter_complex "amerge=inputs=4,pan=mono|c0=0.5*c0+2*c1+0.5*c2+2*c3" pan-mono-weighted.m4a

# stereo channel
ffmpeg -v error -y -i ch0.m4a -i ch1.m4a -i ch2.m4a -i ch3.m4a -filter_complex "amerge=inputs=4,pan=stereo|FL=c0+c2|FR=c1+c3" pan-stereo.m4a

ffprobe -v error pan-stereo.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json
```