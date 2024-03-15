

The '-ss' argument specifies the starting position. Whilst the '-t' argument specifies the duration. For example to cut 15 minutes from 3 minutes 15 seconds. 

```

ffmpeg -i input.mp4 -ss 00:03:15 -t 00:15:00 -c:v copy -c:a copy output.mp4


```


The '-to' argument can be used to cut to a specific time code. For example to cut specifically between 2:13 to 9:30. 


```

ffmpeg -i input.mp4 -ss 00:02:13 -to 00:9:30 -c:v copy -c:a copy output.mp4

```

The '-sseof' argument can be used to cut a certain amount from the end of the video. For example to cut specifically the last 10 minutes of the video.

```

ffmpeg -sseof -00:10:00 -i input.mp4 -c copy output.mp4

```




