# tk darknet
this is a fork of alexey darknet
tk version of yolos are in *mycfg/* folder

### Compile
Compile with make without modify anything in the makefile, it will use only CPU
```
make
```

### Train
```
wget https://pjreddie.com/media/files/darknet53.conv.74 # pretrained weights
./darknet detector train data cfg darknet53.conv.74 -map
```
dont use pretrained weights with 1 channel input (for instance with yolo3_flir)


### Test
```
./darknet detector demo data cfg weights test_video.mp4 -thresh 0.3
```

### Export weights to tkDNN
```
./darknet export cfg weights out/path/
```
warning: 
- out/path should already be present and empty
- debug is exported to "debug/" folder
- if you need debug export of every layer ouput you MUST compile in CPU mode
