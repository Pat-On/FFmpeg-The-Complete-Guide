# Inputs and Outputs

## Protocols, Devices and Formats

```sh
ffmpeg

-f <input device or format>
-i <input-protocol>:<input-identifier>

... <filters and other options> ...

-f <output device or format>
<output-protocol>:<output-identifier>

```

## Listing supported Protocols, Devices and Formats

```sh
ffmpeg -protocols

ffmpeg -devices

ffmpeg -formats

```

##  Files

```sh
ffmpeg -f mov -i file:input.mov ... /tmp/output.mp4

ffmpeg -i sub/dir/input.mp4 ... ../relative/path/output.mp4

ffmpeg -i input.mp4 ... -f mxf output-without-extension

```
- you do not need to specify the file protocol - ffmpeg will assumed protocol by default

## Network

- http(s), ftp, rtp, ...

```sh

ffmpeg -i https://some-server/media.mp4 ... disk-file.mp4

ffmpeg -i rtp://localhost:1234 ... ftp://abc.com/123/out.mxf

```

## Pipes, stdin, stdout

```sh
ffmpeg -f mov -i - ... -f mxf -

ffmpeg -f mov -i pipe:0 ... -f mxf pipe:1

```
- it is useful whe we want to read output from the different command that is using standard input
- it is useful to skip process of writing the file to the hard disc 
- you may need to specify format, because file extension is not specified
- we can not use pipes for seekable formats

## Generated inputs
- useful for testing

```sh
ffmpeg -f lavfi -i testsrc=duration-1:size=1920x1080 ...

ffmpeg -f lavfi -i color=color=red ...

```

lavfi - Libavfilter input virtual device.


## Screen Capture

```sh
# Windows:
ffmpeg -f gdigrab -i desktop ...

# MacOs
ffmpeg -f avfoundation -i "1" ...

# Linux
ffmpeg -f x11grab -i $DISPLAY ...

```

## Webcam capture
```sh

# Windows
ffmpeg -f dshow -i video="USB2.0 UVC WebCam" ...

# MacOs
ffmpeg -f avfoundation -i "default" ...

# Linux
ffmpeg -f v4l2 -f /dev/video0 ...

# example:
ffmpeg -f v4l2 -framerate 25 -video_size 640x480 -i /dev/video0 output.mkv

```

## Microphone Capture
```sh

# Windows
ffmpeg -f dshow -i audio="Microphone (Realtek)" ...

# MacOs
ffmpeg -f avfoundation -i "2" ...

# Linux
ffmpeg -f v4l2 -f alsa -i hw:1 ...

```
