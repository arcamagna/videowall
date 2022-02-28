# videowall
**Mimics a video wall by creating an overlay filter for ffmpeg. Works with both videos and images.**

### Usage  
```  
videowall [options] [files..]
```
### Options
	-n
	   Number of rows (2 - 16). Default 4 (16 tiles) or 3 (18 tiles) in portrait mode.  
	
	-l
	   Landscape mode for each video (default).  
	
	-L
	   As above but use landscape files only (disabled if -s specified).  
	
	-p
	   Portrait mode.  
	
	-P
	   As above but use portrait files only (disabled if -s specified).  
	
	-o <number>
	   Offset to skip valid files e.g. -o4 use 5th file onwards.
	
	-s
	   Skip integrity check (faster start up).  
	
	-F
	   Target frame rate. Default 30 fps.  
	
	-r
	   Find files recursively.  
	
	-f <extension>
	   Filter filetype(s) e.g. "mp4 jpg".  
	
	-t <centre|left>
	   Position titles (file name) centre or left. Default no titles.  
	
	-T <centre|left>
	   As above but use title tag if it exists (otherwise use file name).  
	
	-S
	   Shuffle file order.
	
	-g <"colour thickness">
	   Grid or bezel colour and thickness e.g. "black 3" or "#000000 3". Default is no grid.  
	
	-R <"output_file.mp4">
	   Specify a file name to record output.  
	
	-d
	   demo  

### Files
Directory name or list of videos/images. If omitted current directory is used.

### Operation
If there aren't enough files available they will be repeated to fill the given area.  
Performance can be very slow for larger values of n especially when checking file validity.

Press q to quit  

### Examples
```
videowall
```
Produces a 4x4 grid of videos and/or images from the current directory. Sequence will be repeated if there aren't 16 unique valid files.
```
videowall -pSn2 -g"#054da5 4" -T centre
```
Produces a 8x2 random grid of videos each having a 4 px blue frame and title tag bottom centre if one exists.
```
videowall -rs -n6 -f "mp4 mkv" -o 50 -R "/tmp/6x6 video wall.mp4" ~
```
Produces a 6x6 grid by recursively searching for mp4 and mkv files in user directory. The first 50 files will be skipped. Files will not be checked for valid video streams. Output will be recorded to "/tmp/6x6 video wall.mp4" instead of displaying on screen.
