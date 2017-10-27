# hpi2png - hpi to png image converter utility
Forked from Alexander A. Mandl

## About

hpi is an obscure image format created for the use of Hemera's image library browser. Its basically a compressed JPG image with an PNG image mask. You know, what today we just use a PNG image for.

So this tool written by Alexander A. Mandl combs through the compressed image binary, pulls out the image and the mask and makes a PNG out of it so you can get some use out of that ginormous box of CD's you paid top dollar for back in the day.

## Requirements

For it to work you'll need Perl, CPAN, and the Image::Magick Perl files all working together.

```bash
which perl
CPAN # If you haven't fired up Perl yet - this will update CPAN
upgrade # from within CPAN if so inclined
wget https://www.imagemagick.org/download/ImageMagick.tar.gz
tar xvxf ./ImageMagick.tar.gz
cd ImageMagick-7.0.7-8/
./configure -with-perl
sudo make install
perl -MImage::Magick -le 'print Image::Magick->QuantumDepth' # smoketest
```

If that works - you're ready to rock.

## Using hpi2png

The syntax for 'one file at a time' is:

```bash
hpi2png <inputfile.hpi> <outputfile.png>
```

And here's a handy one-liner to convert all HPI files in the current folder:

```bash
for filename in * ; do <path/to/your>/hpi2png.pl $filename $filename.png; done
```
