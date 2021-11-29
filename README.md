| ![D](gifs/D.gif) | ![o](gifs/o.gif) | ![r](gifs/r.gif) | ![k](gifs/k.gif) |  |  |  |  |  |  |
|---|---|---|---|---|---|---|---|---|---|
| ![C](gifs/C.gif) | ![h](gifs/h.gif) | ![a](gifs/a.gif) | ![r](gifs/r.gif) | ![a](gifs/a.gif) | ![c](gifs/c.gif) | ![t](gifs/t.gif) | ![e](gifs/e.gif) | ![r](gifs/r.gif) |  |   
| ![A](gifs/A.gif) | ![n](gifs/n.gif) | ![i](gifs/i.gif) | ![m](gifs/m.gif) | ![a](gifs/a.gif) | ![t](gifs/t.gif) | ![i](gifs/i.gif) | ![o](gifs/o.gif) | ![n](gifs/n.gif) | ![s](gifs/s.gif) |  

<br>

imagemagick is massive, it's too big in fact but that doesn't mean we can't mess around with it and see what we can come up with, i'm interested in making small animated gifs of keyboard characters and that's exactly what i'm going to showcase here

<br>

## how to create an image using characters with imagemagick?
this couldn't be more easier, we'll use the program `convert` (in some version it's called magick) to achieve this
```
convert -gravity center -background yellow -fill black -size 30x30 caption:"A" A.jpg
```
![A-A](temp/A-A.jpg)

as you can see `-gravity center` is supposed to center our character vertically and horizontally but it doesn't that correctly, we can correct this using `-trim` which remove white spcaes in the image and pad it to center with `-extent` and passing the same size as our output image
```
convert -gravity center -background yellow -fill black -size 30x30 caption:"A" -trim -extent 30x30 A.jpg
```
![A-B](temp/A-B.jpg)

<br>

## output all of the characters in a for loop
now that we know how to output an image we'll use a for loop to convert all the numbers and alphabet characters in lower and higher case
```
for i in {a..z} {A..Z} {0..9} ; do convert -gravity center -trim -background yellow -fill black -font ./nerd.ttf -size 30x30 caption:$i -extent 30x30 $i.jpg ; done
```

![0](images/0.jpg)
![1](images/1.jpg)
![2](images/2.jpg)
![3](images/3.jpg)
![4](images/4.jpg)
![5](images/5.jpg)
![6](images/6.jpg)
![7](images/7.jpg)
![8](images/8.jpg)
![9](images/9.jpg)
![a](images/a.jpg)
![b](images/b.jpg)
![c](images/c.jpg)
![d](images/d.jpg)
![e](images/e.jpg)
![f](images/f.jpg)
![g](images/g.jpg)
![h](images/h.jpg)
![i](images/i.jpg)
![j](images/j.jpg)
![k](images/k.jpg)
![l](images/l.jpg)
![m](images/m.jpg)
![n](images/n.jpg)
![o](images/o.jpg)
![p](images/p.jpg)
![q](images/q.jpg)
![r](images/r.jpg)
![s](images/s.jpg)
![t](images/t.jpg)
![u](images/u.jpg)
![v](images/v.jpg)
![w](images/w.jpg)
![x](images/x.jpg)
![y](images/y.jpg)
![z](images/z.jpg)
![A](images/A.jpg)
![B](images/B.jpg)
![C](images/C.jpg)
![D](images/D.jpg)
![E](images/E.jpg)
![F](images/F.jpg)
![G](images/G.jpg)
![H](images/H.jpg)
![I](images/I.jpg)
![J](images/J.jpg)
![K](images/K.jpg)
![L](images/L.jpg)
![M](images/M.jpg)
![N](images/N.jpg)
![O](images/O.jpg)
![P](images/P.jpg)
![Q](images/Q.jpg)
![R](images/R.jpg)
![S](images/S.jpg)
![T](images/T.jpg)
![U](images/U.jpg)
![V](images/V.jpg)
![W](images/W.jpg)
![X](images/X.jpg)
![Y](images/Y.jpg)
![Z](images/Z.jpg)

`{a..z} {A..Z} {0..9}` in our for loop tells our shell to iterate thru numbers 0 to 9, characters from a to z and A to Z one by one

we also used a custom font with `-font` called `nerd.ttf` which was actually `Caskaydia Cove Nerd Font Mono` which i renamed for simplicity and put inside the folder i'm making these images, you can also pass the abseloute path to it in your filesystem 

the mono in that font name refers to every character taking the same width as other, these fonts are typically used in ascii art, terminal emulators and code editors to easily be able to read them but i'm using the mono variant because it's easier to fit into the image

<br>

## printing special characters
special characters are harder to work with since they are not aload to be used in file names in windows specially so because we want to have a cross-platform solution we convert their file names to their hex counterparts, note that this command is a zsh exclusive command and doesn't work on bash
```
for char in {\!..\)} \@ \` {\*..\/} {\:..\?} {\[..\^} {\{..\~} ; do printf -v hex '%02X' $(( #char )) ; convert -gravity center -trim -background yellow -fill black -font ./nerd.ttf -size 30x30 -extent 30x30 caption:$char $hex.jpg ; done
```

![21](images/21.jpg)
![22](images/22.jpg)
![23](images/23.jpg)
![24](images/24.jpg)
![25](images/25.jpg)
![26](images/26.jpg)
![27](images/27.jpg)
![28](images/28.jpg)
![29](images/29.jpg)
![2A](images/2A.jpg)
![2B](images/2B.jpg)
![2C](images/2C.jpg)
![2D](images/2D.jpg)
![2E](images/2E.jpg)
![2F](images/2F.jpg)
![3A](images/3A.jpg)
![3B](images/3B.jpg)
![3C](images/3C.jpg)
![3D](images/3D.jpg)
![3E](images/3E.jpg)
![3F](images/3F.jpg)
![40](images/40.jpg)
![5B](images/5B.jpg)
![5C](images/5C.jpg)
![5D](images/5D.jpg)
![5E](images/5E.jpg)
![60](images/60.jpg)
![7B](images/7B.jpg)
![7C](images/7C.jpg)
![7D](images/7D.jpg)
![7E](images/7E.jpg)

notice the segmented ranges in our for loop ``{\!..\)} \@ \` {\*..\/} {\:..\?} {\[..\^} {\{..\~}`` the reason for this is that we don't want duplicate characters as our normal characters above so we exclude the ranges they are in withing our for loop, if you don't care about file names you can do ``{" "..~}`` and combine both steps together

<br>

## animating the characters
so far we've been working with static image but let's change all of that and use ffmpeg to make a simple animating, we'll combine two for loops together one for the degrees of hue change (which changes the color of the images) and one for ffmpeg to iterate thru our images
```
for h in {30..360..30} ; for i in {a..z}.jpg {A..Z}.jpg {0..9}.jpg ; do mkdir output ; ffmpeg -i $i -vf hue=h=$h output/$h-$i ; done
```

we also made a `output` folder and put the output images inside it to keep things orginized, now cd into that folder ``cd output/``

we need to pad a zero before filenames because the shell doesn't read files numberically and doesn't know the number 30 in filenames comes before 120 for example
```
for x in *.jpg ; do mv $x `printf %03d-%s ${x%-*} ${x##*-}` ; done 
```

now we are ready to animate these image sequences using the `convert` program
```
for m in {a..z} {A..Z} {0..9} ; do convert *-$m.jpg $m.gif ; done 
```
notice that the same pattern that we used when converting the input images is used for outputing the animations

![0](gifs/0.gif)
![1](gifs/1.gif)
![2](gifs/2.gif)
![3](gifs/3.gif)
![4](gifs/4.gif)
![5](gifs/5.gif)
![6](gifs/6.gif)
![7](gifs/7.gif)
![8](gifs/8.gif)
![9](gifs/9.gif)
![a](gifs/a.gif)
![b](gifs/b.gif)
![c](gifs/c.gif)
![d](gifs/d.gif)
![e](gifs/e.gif)
![f](gifs/f.gif)
![g](gifs/g.gif)
![h](gifs/h.gif)
![i](gifs/i.gif)
![j](gifs/j.gif)
![k](gifs/k.gif)
![l](gifs/l.gif)
![m](gifs/m.gif)
![n](gifs/n.gif)
![o](gifs/o.gif)
![p](gifs/p.gif)
![q](gifs/q.gif)
![r](gifs/r.gif)
![s](gifs/s.gif)
![t](gifs/t.gif)
![u](gifs/u.gif)
![v](gifs/v.gif)
![w](gifs/w.gif)
![x](gifs/x.gif)
![y](gifs/y.gif)
![z](gifs/z.gif)
![A](gifs/A.gif)
![B](gifs/B.gif)
![C](gifs/C.gif)
![D](gifs/D.gif)
![E](gifs/E.gif)
![F](gifs/F.gif)
![G](gifs/G.gif)
![H](gifs/H.gif)
![I](gifs/I.gif)
![J](gifs/J.gif)
![K](gifs/K.gif)
![L](gifs/L.gif)
![M](gifs/M.gif)
![N](gifs/N.gif)
![O](gifs/O.gif)
![P](gifs/P.gif)
![Q](gifs/Q.gif)
![R](gifs/R.gif)
![S](gifs/S.gif)
![T](gifs/T.gif)
![U](gifs/U.gif)
![V](gifs/V.gif)
![W](gifs/W.gif)
![X](gifs/X.gif)
![Y](gifs/Y.gif)
![Z](gifs/Z.gif)

<br>

## animating special characters
the same principles applies here, we just need to adjust our commands a bit, first the ffmpeg command
```
for h in {30..360..30} ; for i in 21 22 23 24 25 26 27 28 29 2A 2B 2C 2D 2E 2F 3A 3B 3C 3D 3E 3F 40 5B 5C 5D 5E 60 7B 7C 7D 7E ; do mkdir output2 ; ffmpeg -i $i.jpg -vf hue=h=$h output2/$h-$i.jpg ; done
```
because we only want speciall characters and don't need duplicates we specially named every output file we need, we also made a new output2 folder to keep things orginized, cd into the folder like before ``cd output2/`` and zero pad them just like before ``for x in *.jpg ; do mv $x `printf %03d-%s ${x%-*} ${x##*-}` ; done``

now lets convert them to animated gifs
```
for m in 21 22 23 24 25 26 27 28 29 2A 2B 2C 2D 2E 2F 3A 3B 3C 3D 3E 3F 40 5B 5C 5D 5E 60 7B 7C 7D 7E ; do convert *-$m.jpg $m.gif ; done
```

![21](gifs/21.gif)
![22](gifs/22.gif)
![23](gifs/23.gif)
![24](gifs/24.gif)
![25](gifs/25.gif)
![26](gifs/26.gif)
![27](gifs/27.gif)
![28](gifs/28.gif)
![29](gifs/29.gif)
![2A](gifs/2A.gif)
![2B](gifs/2B.gif)
![2C](gifs/2C.gif)
![2D](gifs/2D.gif)
![2E](gifs/2E.gif)
![2F](gifs/2F.gif)
![3A](gifs/3A.gif)
![3B](gifs/3B.gif)
![3C](gifs/3C.gif)
![3D](gifs/3D.gif)
![3E](gifs/3E.gif)
![3F](gifs/3F.gif)
![40](gifs/40.gif)
![5B](gifs/5B.gif)
![5C](gifs/5C.gif)
![5D](gifs/5D.gif)
![5E](gifs/5E.gif)
![60](gifs/60.gif)
![7B](gifs/7B.gif)
![7C](gifs/7C.gif)
![7D](gifs/7D.gif)
![7E](gifs/7E.gif)

<br>

###### more examples coming soon
