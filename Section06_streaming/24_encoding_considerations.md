# Encoding Considerations

I - frames - contain all the information and can be decoded in separation to other frames

![Alt text](image-19.png)

P - frames - they do not have all information and needs to be decoded following close frames - `predicted pictures`. when there is not many things in video that is changing

![Alt text](image-20.png)

B - frames - bidirectional frames - they are even more compressed but to decompress them we need to use their close neighbors

![Alt text](image-21.png)

## Group of Pictures - GOP

![Alt text](image-22.png)

I - is starting point

![Alt text](image-23.png)

![Alt text](image-24.png)

## Segments in Adaptive Streaming

![Alt text](image-25.png)

## Segments: Switching and Duration

![Alt text](image-26.png)


- Long or short segments?
  - to long are not good because you need to finish downloading segments and then you can switch to different segment


## Encoding Efficiency: Short Segments

![Alt text](image-27.png)

- You need to have at least one I-frame
  - more I-frames more space so:
  - short Segments => more I-frames => less compression


## Encoding Efficiency: Long Segments

![Alt text](image-28.png)

Long Segments -> Fewer I-frames -> better compression

## Segment Duration: Recommendations
- Apple: 6 seconds
- 2-4 seconds work well for most situations


## Codecs
![Alt text](image-29.png)

## Containers
![Alt text](image-30.png)

## Muxing Audio and Vide
- Muxed together
- we can manage quality of sound too
- separate audio, separate video - different quality etc

## HLS or DASH
![Alt text](image-31.png)

## HLS and DASH
![Alt text](image-32.png)

Interesting concept of using both 


## Summary
- Frame types - I, P, B
- GOP structures
- Segmentation
  - independence
  - duration
  - encoding efficiency vs switching
- Codecs
- containers
- HLS / DASH
- HLS + DASH with common media segments

