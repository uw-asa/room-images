# To run this automatically when pdfs are updated, add the make
# command to a "post-merge" git hook, i.e. "make -C schematics"

thumbnails := $(patsubst %.pdf,%_thumbnail.png,$(wildcard *.pdf))

%_thumbnail.png: %.pdf
	convert -trim $< $@
# 	mogrify -rotate -90 $@
	mogrify -thumbnail 320 -border 10 -bordercolor white $@
	mogrify -border 1 -bordercolor black $@

all: $(thumbnails)

clean:
	rm *_thumbnail.png
