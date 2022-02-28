# videowall
Mimics a video wall by creating an overlay filter for ffmpeg.
Works with both videos and images.

Usage: videowall [options] [files..]

options:
 -n    Number of rows (2 - 16). Default: 4 (landscape), 3 (portrait).
 -l    Landscape mode for each video. This is the default.
 -L    As above but use landscape files only (disabled if -s specified).
 -p    Portrait mode.
 -P    As above but use portrait files only (disabled if -s specified).
 -o    Use valid files from offset onwards.
 -s    Skip integrity check (faster start up).
 -F    Target frame rate. Default 30fps.
 -r    Find files recursively.
 -f  <extension> Filter filetype(s) e.g. "mp4 jpg".
 -t  <centre|left> Position titles (file name) centre or left. Default no titles.
 -T  <centre|left> As above but use title tag if it exists.
 -g  <"colour thickness"> Grid or bezel colour and thickness e.g. "black 3". Default is no grid.
 -R  <output_file.mp4> Specify a file name to record output.
 -d    demo

files:
Directory name or list of videos/images. Leave blank to use current directory.

If there aren't enough valid files available they will be repeated to fill the given area.
Larger values for n may be very slow especially when checking file validity.

q to quit
