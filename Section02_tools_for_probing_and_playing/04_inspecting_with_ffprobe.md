# Inspecting with ffprobe


Practical examples:

`ffprobe seagull.mp4`

output:
```bash
ffprobe version 6.0 Copyright (c) 2007-2023 the FFmpeg developers
  built with gcc 11 (Ubuntu 11.3.0-1ubuntu1~22.04.1)
  configuration: --prefix=/home/linuxbrew/.linuxbrew/Cellar/ffmpeg/6.0 --enable-shared --enable-pthreads --enable-version3 --cc=gcc-11 --host-cflags= --host-ldflags= --enable-ffplay --enable-gnutls --enable-gpl --enable-libaom --enable-libaribb24 --enable-libbluray --enable-libdav1d --enable-libmp3lame --enable-libopus --enable-librav1e --enable-librist --enable-librubberband --enable-libsnappy --enable-libsrt --enable-libsvtav1 --enable-libtesseract --enable-libtheora --enable-libvidstab --enable-libvmaf --enable-libvorbis --enable-libvpx --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxml2 --enable-libxvid --enable-lzma --enable-libfontconfig --enable-libfreetype --enable-frei0r --enable-libass --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libopenjpeg --enable-libspeex --enable-libsoxr --enable-libzmq --enable-libzimg --disable-libjack --disable-indev=jack
  libavutil      58.  2.100 / 58.  2.100
  libavcodec     60.  3.100 / 60.  3.100
  libavformat    60.  3.100 / 60.  3.100
  libavdevice    60.  1.100 / 60.  1.100
  libavfilter     9.  3.100 /  9.  3.100
  libswscale      7.  1.100 /  7.  1.100
  libswresample   4. 10.100 /  4. 10.100
  libpostproc    57.  1.100 / 57.  1.100
Input #0, mov,mp4,m4a,3gp,3g2,mj2, from 'seagull.mp4':
  Metadata:
    major_brand     : isom
    minor_version   : 512
    compatible_brands: isomiso2avc1mp41
    encoder         : Lavf57.56.101
  Duration: 00:00:10.84, start: 0.000000, bitrate: 1927 kb/s
  Stream #0:0[0x1](eng): Video: h264 (High) (avc1 / 0x31637661), yuv420p(progressive), 1920x1080 [SAR 1:1 DAR 16:9], 1918 kb/s, 25 fps, 25 tbr, 12800 tbn (default)
    Metadata:
      handler_name    : VideoHandler
      vendor_id       : [0][0][0][0]
  Stream #0:1[0x2](eng): Audio: aac (LC) (mp4a / 0x6134706D), 48000 Hz, stereo, fltp, 2 kb/s (default)
    Metadata:
      handler_name    : SoundHandler

```


`ffprobe -v error seagull.mp4`
output: nothing

`ffprobe -v error seagull.mp4 -show_format`

output:
```bash
[FORMAT]
filename=seagull.mp4
nb_streams=2
nb_programs=0
format_name=mov,mp4,m4a,3gp,3g2,mj2
format_long_name=QuickTime / MOV
start_time=0.000000
duration=10.840000
size=2611163
bit_rate=1927057
probe_score=100
TAG:major_brand=isom
TAG:minor_version=512
TAG:compatible_brands=isomiso2avc1mp41
TAG:encoder=Lavf57.56.101
[/FORMAT]
```

`ffprobe -v error seagull.mp4 -show_format -show_streams`

output:
```sh

[STREAM]
index=0                 <--- First stream 
codec_name=h264
codec_long_name=H.264 / AVC / MPEG-4 AVC / MPEG-4 part 10
profile=High
codec_type=video
codec_tag_string=avc1
codec_tag=0x31637661
width=1920
height=1080
coded_width=1920
coded_height=1080
closed_captions=0
film_grain=0
has_b_frames=2
sample_aspect_ratio=1:1
display_aspect_ratio=16:9
pix_fmt=yuv420p
level=40
color_range=unknown
color_space=unknown
color_transfer=unknown
color_primaries=unknown
chroma_location=left
field_order=progressive
refs=1
is_avc=true
nal_length_size=4
id=0x1
r_frame_rate=25/1
avg_frame_rate=25/1
time_base=1/12800
start_pts=0
start_time=0.000000
duration_ts=138752
duration=10.840000
bit_rate=1918177
max_bit_rate=N/A
bits_per_raw_sample=8
nb_frames=271
nb_read_frames=N/A
nb_read_packets=N/A
extradata_size=44
DISPOSITION:default=1
DISPOSITION:dub=0
DISPOSITION:original=0
DISPOSITION:comment=0
DISPOSITION:lyrics=0
DISPOSITION:karaoke=0
DISPOSITION:forced=0
DISPOSITION:hearing_impaired=0
DISPOSITION:visual_impaired=0
DISPOSITION:clean_effects=0
DISPOSITION:attached_pic=0
DISPOSITION:timed_thumbnails=0
DISPOSITION:captions=0
DISPOSITION:descriptions=0
DISPOSITION:metadata=0
DISPOSITION:dependent=0
DISPOSITION:still_image=0
TAG:language=eng
TAG:handler_name=VideoHandler
TAG:vendor_id=[0][0][0][0]
[/STREAM]
[STREAM]
index=1                                  <--- Second stream 
codec_name=aac
codec_long_name=AAC (Advanced Audio Coding)
profile=LC
codec_type=audio
codec_tag_string=mp4a
codec_tag=0x6134706d
sample_fmt=fltp
sample_rate=48000
channels=2
channel_layout=stereo
bits_per_sample=0
initial_padding=0
id=0x2
r_frame_rate=0/0
avg_frame_rate=0/0
time_base=1/48000
start_pts=0
start_time=0.000000
duration_ts=516096
duration=10.752000
bit_rate=2275
max_bit_rate=N/A
bits_per_raw_sample=N/A
nb_frames=505
nb_read_frames=N/A
nb_read_packets=N/A
extradata_size=5
DISPOSITION:default=1
DISPOSITION:dub=0
DISPOSITION:original=0
DISPOSITION:comment=0
DISPOSITION:lyrics=0
DISPOSITION:karaoke=0
DISPOSITION:forced=0
DISPOSITION:hearing_impaired=0
DISPOSITION:visual_impaired=0
DISPOSITION:clean_effects=0
DISPOSITION:attached_pic=0
DISPOSITION:timed_thumbnails=0
DISPOSITION:captions=0
DISPOSITION:descriptions=0
DISPOSITION:metadata=0
DISPOSITION:dependent=0
DISPOSITION:still_image=0
TAG:language=eng
TAG:handler_name=SoundHandler
TAG:vendor_id=[0][0][0][0]
[/STREAM]
[FORMAT]
filename=seagull.mp4
nb_streams=2
nb_programs=0
format_name=mov,mp4,m4a,3gp,3g2,mj2
format_long_name=QuickTime / MOV
start_time=0.000000
duration=10.840000
size=2611163
bit_rate=1927057
probe_score=100
TAG:major_brand=isom
TAG:minor_version=512
TAG:compatible_brands=isomiso2avc1mp41
TAG:encoder=Lavf57.56.101
[/FORMAT]
```


`ffprobe -v error seagull.mp4 -show_format -show_streams -print_format json`


output:
```json
{
    "streams": [
        {
            "index": 0,
            "codec_name": "h264",
            "codec_long_name": "H.264 / AVC / MPEG-4 AVC / MPEG-4 part 10",
            "profile": "High",
            "codec_type": "video",
            "codec_tag_string": "avc1",
            "codec_tag": "0x31637661",
            "width": 1920,
            "height": 1080,
            "coded_width": 1920,
            "coded_height": 1080,
            "closed_captions": 0,
            "film_grain": 0,
            "has_b_frames": 2,
            "sample_aspect_ratio": "1:1",
            "display_aspect_ratio": "16:9",
            "pix_fmt": "yuv420p",
            "level": 40,
            "chroma_location": "left",
            "field_order": "progressive",
            "refs": 1,
            "is_avc": "true",
            "nal_length_size": "4",
            "id": "0x1",
            "r_frame_rate": "25/1",
            "avg_frame_rate": "25/1",
            "time_base": "1/12800",
            "start_pts": 0,
            "start_time": "0.000000",
            "duration_ts": 138752,
            "duration": "10.840000",
            "bit_rate": "1918177",
            "bits_per_raw_sample": "8",
            "nb_frames": "271",
            "extradata_size": 44,
            "disposition": {
                "default": 1,
                "dub": 0,
                "original": 0,
                "comment": 0,
                "lyrics": 0,
                "karaoke": 0,
                "forced": 0,
                "hearing_impaired": 0,
                "visual_impaired": 0,
                "clean_effects": 0,
                "attached_pic": 0,
                "timed_thumbnails": 0,
                "captions": 0,
                "descriptions": 0,
                "metadata": 0,
                "dependent": 0,
                "still_image": 0
            },
            "tags": {
                "language": "eng",
                "handler_name": "VideoHandler",
                "vendor_id": "[0][0][0][0]"
            }
        },
        {
            "index": 1,
            "codec_name": "aac",
            "codec_long_name": "AAC (Advanced Audio Coding)",
            "profile": "LC",
            "codec_type": "audio",
            "codec_tag_string": "mp4a",
            "codec_tag": "0x6134706d",
            "sample_fmt": "fltp",
            "sample_rate": "48000",
            "channels": 2,
            "channel_layout": "stereo",
            "bits_per_sample": 0,
            "initial_padding": 0,
            "id": "0x2",
            "r_frame_rate": "0/0",
            "avg_frame_rate": "0/0",
            "time_base": "1/48000",
            "start_pts": 0,
            "start_time": "0.000000",
            "duration_ts": 516096,
            "duration": "10.752000",
            "bit_rate": "2275",
            "nb_frames": "505",
            "extradata_size": 5,
            "disposition": {
                "default": 1,
                "dub": 0,
                "original": 0,
                "comment": 0,
                "lyrics": 0,
                "karaoke": 0,
                "forced": 0,
                "hearing_impaired": 0,
                "visual_impaired": 0,
                "clean_effects": 0,
                "attached_pic": 0,
                "timed_thumbnails": 0,
                "captions": 0,
                "descriptions": 0,
                "metadata": 0,
                "dependent": 0,
                "still_image": 0
            },
            "tags": {
                "language": "eng",
                "handler_name": "SoundHandler",
                "vendor_id": "[0][0][0][0]"
            }
        }
    ],
    "format": {
        "filename": "seagull.mp4",
        "nb_streams": 2,
        "nb_programs": 0,
        "format_name": "mov,mp4,m4a,3gp,3g2,mj2",
        "format_long_name": "QuickTime / MOV",
        "start_time": "0.000000",
        "duration": "10.840000",
        "size": "2611163",
        "bit_rate": "1927057",
        "probe_score": 100,
        "tags": {
            "major_brand": "isom",
            "minor_version": "512",
            "compatible_brands": "isomiso2avc1mp41",
            "encoder": "Lavf57.56.101"
        }
    }
}
```


## Selecting streams


`ffprobe -v error seagull.mp4 -show_streams -select_streams v`

```
[STREAM]
index=0                 <--- output that we got is only related to video stream>
codec_name=h264
codec_long_name=H.264 / AVC / MPEG-4 AVC / MPEG-4 part 10
profile=High
codec_type=video
codec_tag_string=avc1
codec_tag=0x31637661
width=1920
height=1080
coded_width=1920
coded_height=1080
closed_captions=0
film_grain=0
has_b_frames=2
sample_aspect_ratio=1:1
display_aspect_ratio=16:9
pix_fmt=yuv420p
level=40
color_range=unknown
color_space=unknown
color_transfer=unknown
color_primaries=unknown
chroma_location=left
field_order=progressive
refs=1
is_avc=true
nal_length_size=4
id=0x1
r_frame_rate=25/1
avg_frame_rate=25/1
time_base=1/12800
start_pts=0
start_time=0.000000
duration_ts=138752
duration=10.840000
bit_rate=1918177
max_bit_rate=N/A
bits_per_raw_sample=8
nb_frames=271
nb_read_frames=N/A
nb_read_packets=N/A
extradata_size=44
DISPOSITION:default=1
DISPOSITION:dub=0
DISPOSITION:original=0
DISPOSITION:comment=0
DISPOSITION:lyrics=0
DISPOSITION:karaoke=0
DISPOSITION:forced=0
DISPOSITION:hearing_impaired=0
DISPOSITION:visual_impaired=0
DISPOSITION:clean_effects=0
DISPOSITION:attached_pic=0
DISPOSITION:timed_thumbnails=0
DISPOSITION:captions=0
DISPOSITION:descriptions=0
DISPOSITION:metadata=0
DISPOSITION:dependent=0
DISPOSITION:still_image=0
TAG:language=eng
TAG:handler_name=VideoHandler
TAG:vendor_id=[0][0][0][0]
[/STREAM]

```

`ffprobe -v error seagull.mp4 -select_streams v -show_entries stream=codec_name`

```
[STREAM]
codec_name=h264
DISPOSITION:default=1
DISPOSITION:dub=0
DISPOSITION:original=0
DISPOSITION:comment=0
DISPOSITION:lyrics=0
DISPOSITION:karaoke=0
DISPOSITION:forced=0
DISPOSITION:hearing_impaired=0
DISPOSITION:visual_impaired=0
DISPOSITION:clean_effects=0
DISPOSITION:attached_pic=0
DISPOSITION:timed_thumbnails=0
DISPOSITION:captions=0
DISPOSITION:descriptions=0
DISPOSITION:metadata=0
DISPOSITION:dependent=0
DISPOSITION:still_image=0
TAG:language=eng
TAG:handler_name=VideoHandler
TAG:vendor_id=[0][0][0][0]
[/STREAM]

```


`ffprobe -v error seagull.mp4 -select_streams v -show_entries stream=codec_name `

```
[STREAM]
codec_name=h264
[/STREAM]

```
_
`ffprobe -v error seagull.mp4 -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1 `

```
codec_name=h264

```

`ffprobe -v error seagull.mp4 -select_streams v -show_entries stream=codec_name -print_format default=noprint_wrappers=1:nokey=1 `

```
h264
```

`ffprobe -v error seagull.mp4  -show_entries format=format_long_name -print_format default=noprint_wrappers=1:nokey=1 `
```
QuickTime / MOV
```


## Big buck bunny

`ffprobe -v error https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/1080/Big_Buck_Bunny_1080_10s_10MB.mp4 -show_format -show_streams -print_format json`

```json
{
    "streams": [
        {
            "index": 0,
            "codec_name": "h264",
            "codec_long_name": "H.264 / AVC / MPEG-4 AVC / MPEG-4 part 10",
            "profile": "High",
            "codec_type": "video",
            "codec_tag_string": "avc1",
            "codec_tag": "0x31637661",
            "width": 1920,
            "height": 1080,
            "coded_width": 1920,
            "coded_height": 1080,
            "closed_captions": 0,
            "film_grain": 0,
            "has_b_frames": 2,
            "sample_aspect_ratio": "1:1",
            "display_aspect_ratio": "16:9",
            "pix_fmt": "yuv420p",
            "level": 42,
            "chroma_location": "left",
            "field_order": "progressive",
            "refs": 1,
            "is_avc": "true",
            "nal_length_size": "4",
            "id": "0x1",
            "r_frame_rate": "60/1",
            "avg_frame_rate": "60/1",
            "time_base": "1/15360",
            "start_pts": 0,
            "start_time": "0.000000",
            "duration_ts": 153600,
            "duration": "10.000000",
            "bit_rate": "8382668",
            "bits_per_raw_sample": "8",
            "nb_frames": "600",
            "extradata_size": 48,
            "disposition": {
                "default": 1,
                "dub": 0,
                "original": 0,
                "comment": 0,
                "lyrics": 0,
                "karaoke": 0,
                "forced": 0,
                "hearing_impaired": 0,
                "visual_impaired": 0,
                "clean_effects": 0,
                "attached_pic": 0,
                "timed_thumbnails": 0,
                "captions": 0,
                "descriptions": 0,
                "metadata": 0,
                "dependent": 0,
                "still_image": 0
            },
            "tags": {
                "language": "und",
                "handler_name": "VideoHandler",
                "vendor_id": "[0][0][0][0]"
            }
        }
    ],
    "format": {
        "filename": "https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/1080/Big_Buck_Bunny_1080_10s_10MB.mp4",
        "nb_streams": 1,
        "nb_programs": 0,
        "format_name": "mov,mp4,m4a,3gp,3g2,mj2",
        "format_long_name": "QuickTime / MOV",
        "start_time": "0.000000",
        "duration": "10.000000",
        "size": "10484984",
        "bit_rate": "8387987",
        "probe_score": 100,
        "tags": {
            "major_brand": "isom",
            "minor_version": "512",
            "compatible_brands": "isomiso2avc1mp41"
        }
    }
}


```