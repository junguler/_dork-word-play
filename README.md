# dork character animations
imagemagick is massive, it's too big in fact but that doesn't mean we can't mess around with it and see what we can come up with, i'm interested in making small animated gifs of keyboard characters and that's exactly what i'm going to showcase here

## how to create an image using characters with imagemagick?
this couldn't be more easier, we'll use the program `convert` (in some version it's called magick) to achieve this
```
convert -gravity center -background yellow -fill black -size 30x30 caption:"A" A.jpg
```
![A](https://user-images.githubusercontent.com/59083599/143858120-f9e11d81-0de5-49ce-a264-286971095cc9.jpg)

as you can see `-gravity center` is supposed to center our character vertically and horizontally but it doesn't that correctly, we can correct this using `-trim` which remove white spcaes in the image and pad it to center with `-extent` and passing the same size as our output image
```
convert -gravity center -background yellow -fill black -size 30x30 caption:"A" -trim -extent 30x30 A.jpg
```
![A](https://user-images.githubusercontent.com/59083599/143858576-5b20d726-2568-4df6-a56c-73681f2cb05d.jpg)
