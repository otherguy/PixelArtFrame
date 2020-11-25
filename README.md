# 👾 Pixel Art Frame


## Prepare Images

The code is designed to read 24 bit bitmaps because they store the colors for each pixel directly, and don't require a palette (essentially a lookup table). Since the images are only 16×16px small, the ~30% increase in filesize doesn't have a big impact – the images are still smaller than 1kB each.

In order to convert the `.png` to our 24bit bitmaps, use the following command:

	$ mkdir bitmaps
	$ ls -1 images/*.png | xargs -n 1 bash -c 'convert -type TrueColor -flatten -background "#000000" "$0" "BMP2:bitmaps/`basename ${0%.*}`.bmp"'
	
You need [ImageMagick](https://imagemagick.org/) installed for that:

	$ brew install imagemagick
