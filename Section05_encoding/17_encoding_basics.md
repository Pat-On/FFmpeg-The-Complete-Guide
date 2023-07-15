# Encoding Basics

## Choosing a code
- compression
- quality vs size
- stream vs post-production
- target application
- Compatibility of codecs in the container
  - some containers are not supporting some codecs
  - ffmpeg if you are not going to specify the codec it will do by itself considering the container and compatiblity

## Encoder options
- Global
  - Profile
  - Bitrate
  - GOP size
- Private
  - x264-params

## Encoding Examples


```sh
ffprobe -v error bullfinch.mov -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1

ffmpeg -v error -y -i bullfinch.mov transcoded.mxf
ffprobe -v error transcoded.mxf -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1

ffmpeg -v error -y -i bullfinch.mov transcoded.mp4

ffprobe -v error transcoded.mp4 -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1

ffmpeg -v error -y -i bullfinch.mov -vcodec libx264 transcoded.mxf

ffprobe -v error transcoded.mxf -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1

ffmpeg -encoders # plenty


# not all containers support all codecs
ffmpeg -v error -y -i bullfinch.mov -vcodec libvpx-vp9 transcoded.mxf

# output:
[mxf @ 0x56322f432380] track 0: could not find essence container ul, codec not currently supported in container
[out#0/mxf @ 0x56322f432dc0] Could not write header (incorrect codec parameters ?): Operation not permitted
[vost#0:0/libvpx-vp9 @ 0x56322f458400] Error initializing output stream: 

# ----------------------------------------------------------------------------

ffmpeg -v error -y -i bullfinch.mov -vcodec libvpx-vp9 transcoded.mp4

ffprobe -v error transcoded.mp4 -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1

# AUDIO CODECS

ffprobe -v error transcoded.mp4 -select_streams a -show_entries stream=codec_name -print_format default=noprint_wrappers=1

ffmpeg -v error -y -i bullfinch.mov -vcodec libvpx-vp9 -acodec libmp3lame transcoded.mp4

ffprobe -v error transcoded.mp4 -select_streams a -show_entries stream=codec_name -print_format default=noprint_wrappers=1
```