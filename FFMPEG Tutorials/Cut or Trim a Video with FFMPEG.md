

The '-ss' argument specifies the starting position. Whilst the '-t' argument specifies the duration. For example to cut 15 minutes from 3 minutes 15 seconds. 

```

ffmpeg -i input.mp4 -ss 00:03:15 -t 00:15:00 -c:v copy -c:a copy output1.mp4


```
