Create a text file containing file paths to videos:

```
# videos.txt
file 'input1.mp4'
file 'input2.mp4'
file 'input3.mp4'
```

Run the following command

```
$ ffmpeg -f concat -i videos.txt -c copy output8.mp4
```

Alternatively you can use one command only.

```
ffmpeg -i "concat:input1.mp4|input2.mp4|input3.mp4|input4.mp4" -c copy output10.mp4
```