# ezip

![chall]

This challenge simply gives you two files, `flag.zip` and `cat.png`. `flag.zip` is a password protected zip file and `cat.png` is an image.

The solution is to analyse the image using a tool such as ExifTool which will give you the password for the zip file. This can be done by going to the [ExifTool Website](https://exiftool.org) and downloading the version for your OS and folowing the installation instructions (on Linux you can just run it straight from the download). After it is installed you can `exiftool cat.png` which will output the metadata for the image including a comment of `e4syp4ssf0rz1p`.

![term]

You can then use this password to decrypt the zip file which inside has the `flag.txt` file which is the flag: `utc{ex1f_ru135_4ll_7h3_w4y}`.

## Closing thoughts on the challenge

This challenge was fairly easy to complete however it would be much harder if you didn't know how to extract the metadata from an image and the alternative is to bruteforce the zip file using a program such as `fcrackzip` which is not a good solution as it would take a long time to bruteforce the password due to its' length.



[chall]: challenge.png "Challenge screenshot"
[term]: exif.png "Terminal screenshot"