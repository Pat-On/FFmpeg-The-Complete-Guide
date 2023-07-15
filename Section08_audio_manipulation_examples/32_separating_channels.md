# Separating/Extracting channels

ffprobe -v error two-stereo-tracks.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json

ffmpeg -y -v error -i two-stereo-tracks.m4a -filter_complex "amerge=inputs=2" four-channels-one-stream.m4a

ffprobe -v error four-channels-one-stream.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json

```sh
ffmpeg -y -v error -i two-stereo-tracks.m4a 
-filter_complex 
    "amerge=inputs=2,asplit=4[all0][all1][all2][all3];
    [all0]pan=mono|c0=c0[ch0];
    [all1]pan=mono|c0=c1[ch1];
    [all2]pan=mono|c0=c2[ch2];
    [all3]pan=mono|c0=c3[ch3]" 

    -map "[ch0]" ch0.m4a 
    -map "[ch1]" ch1.m4a 
    -map "[ch2]" ch2.m4a 
    -map "[ch3]" ch3.m4a
```

ffprobe -v error ch0.m4a -select_streams a -show_entries stream=index,codec_name,channels -print_format json
