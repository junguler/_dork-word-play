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

## output all of the characters in a for loop
now that we know how to output an image we'll use a for loop to convert all the numbers and alphabet characters in lower and higher case
```
for i in {a..z} {A..Z} {0..9} ; do convert -gravity center -trim -background yellow -fill black -font ./nerd.ttf -size 30x30 caption:$i -extent 30x30 $i.jpg ; done
```
![0](https://user-images.githubusercontent.com/59083599/143859243-7bbaf48e-1866-4786-8034-e76ca3920213.jpg)
![1](https://user-images.githubusercontent.com/59083599/143859246-e22c0d53-0fd6-47be-98d2-a4a45c1223a9.jpg)
![2](https://user-images.githubusercontent.com/59083599/143859249-5e41f928-11f3-4f3c-8acd-866478622f01.jpg)
![3](https://user-images.githubusercontent.com/59083599/143859253-ab66335d-3be6-4652-8e64-626b5d080d1d.jpg)
![4](https://user-images.githubusercontent.com/59083599/143859257-3933e2b6-71f1-4aaa-a799-2a9c7c45bf35.jpg)
![5](https://user-images.githubusercontent.com/59083599/143859261-1b0447e9-811e-4112-9e1f-4dd27f4f4997.jpg)
![6](https://user-images.githubusercontent.com/59083599/143859265-9fc9aaee-7fc5-4af7-bac5-4ace2b595b32.jpg)
![7](https://user-images.githubusercontent.com/59083599/143859267-97cdba30-9c0f-41b9-b827-dcd4d5ca4f21.jpg)
![8](https://user-images.githubusercontent.com/59083599/143859268-eb8ee886-c16a-4a16-969a-a1df13173792.jpg)
![9](https://user-images.githubusercontent.com/59083599/143859271-58efe3a1-33a1-41a1-a5cc-d54eef610358.jpg)
![a](https://user-images.githubusercontent.com/59083599/143859273-ae15f200-4df1-4852-a44d-40b162210ae9.jpg)
![A](https://user-images.githubusercontent.com/59083599/143859275-0381021f-51d7-45c8-9057-c3e7d659a7ad.jpg)
![b](https://user-images.githubusercontent.com/59083599/143859280-2e089a1b-601c-49b4-99f0-7804cf8e28b6.jpg)
![B](https://user-images.githubusercontent.com/59083599/143859282-517c312c-3392-408c-b4e3-55da9d22e6c3.jpg)
![c](https://user-images.githubusercontent.com/59083599/143859284-96db189e-4e38-4a59-a434-157758ddc7e5.jpg)
![C](https://user-images.githubusercontent.com/59083599/143859289-2db3d214-159f-41e2-9563-e8901aa566b3.jpg)
![d](https://user-images.githubusercontent.com/59083599/143859291-6de7c41c-e5a0-4e9b-8085-8d56d045da6f.jpg)
![D](https://user-images.githubusercontent.com/59083599/143859294-67fc027e-47de-444a-af1d-462e54770b2b.jpg)
![e](https://user-images.githubusercontent.com/59083599/143859295-3c5771fd-2030-4e85-93a3-2f4b770204a1.jpg)
![E](https://user-images.githubusercontent.com/59083599/143859297-8af3a6a8-8212-4a22-b4b9-957768bf8474.jpg)
![f](https://user-images.githubusercontent.com/59083599/143859301-7b75cbcd-9863-4cd8-b373-3729d369bbc2.jpg)
![F](https://user-images.githubusercontent.com/59083599/143859304-686eefcc-8c38-4c65-9444-73ed44c2320d.jpg)
![g](https://user-images.githubusercontent.com/59083599/143859306-69db0a7d-2abf-4ebf-9ed2-144e9cb13896.jpg)
![G](https://user-images.githubusercontent.com/59083599/143859309-f0b9e327-36a5-4392-b642-b99a0cfdd66b.jpg)
![h](https://user-images.githubusercontent.com/59083599/143859313-5a92530e-fc62-4789-ac57-6245066de34b.jpg)
![H](https://user-images.githubusercontent.com/59083599/143859314-0d5846f1-f034-4375-a523-fd1fc5488b54.jpg)
![i](https://user-images.githubusercontent.com/59083599/143859316-13ef4e95-9ce1-4012-9616-33d17238e331.jpg)
![I](https://user-images.githubusercontent.com/59083599/143859317-913fd245-03d4-4031-9ede-9d1a8ee71c90.jpg)
![j](https://user-images.githubusercontent.com/59083599/143859319-6047719f-4371-4818-88c8-3cf499ca9305.jpg)
![J](https://user-images.githubusercontent.com/59083599/143859321-198c0243-1054-45f7-9e67-40de200ac670.jpg)
![k](https://user-images.githubusercontent.com/59083599/143859325-46250ebb-8d74-4291-8ead-ce0d9a91dab4.jpg)
![K](https://user-images.githubusercontent.com/59083599/143859329-054bfbd3-ea59-426f-a8c3-e68ff064e0bc.jpg)
![l](https://user-images.githubusercontent.com/59083599/143859330-d599a440-a5be-4dc6-a182-42535e5b83db.jpg)
![L](https://user-images.githubusercontent.com/59083599/143859333-f71aa803-0891-4685-8122-2311b1def08a.jpg)
![m](https://user-images.githubusercontent.com/59083599/143859338-d04a29d9-080b-4d3b-8466-270492e10519.jpg)
![M](https://user-images.githubusercontent.com/59083599/143859339-6470c350-ffdd-4e00-b070-cbd2b7852c3e.jpg)
![n](https://user-images.githubusercontent.com/59083599/143859340-ddc5092c-5deb-4fb5-98c0-ac7060725cb7.jpg)
![N](https://user-images.githubusercontent.com/59083599/143859350-a5912080-046b-43fd-8abb-b92083a381bc.jpg)
![o](https://user-images.githubusercontent.com/59083599/143859352-d9c88732-caf6-4b24-9bb5-0766b2129eeb.jpg)
![O](https://user-images.githubusercontent.com/59083599/143859358-381e3ad7-519e-43b0-8983-7ee3d0d62444.jpg)
![p](https://user-images.githubusercontent.com/59083599/143859379-cd20b67a-e23a-4cbc-9b5a-bea1612c9236.jpg)
![P](https://user-images.githubusercontent.com/59083599/143859384-be4bca98-1a4c-4372-8484-9c2b6aab440f.jpg)
![q](https://user-images.githubusercontent.com/59083599/143859387-8f37e169-964f-4120-adeb-be3ebdc9ee69.jpg)
![Q](https://user-images.githubusercontent.com/59083599/143859392-e955c0de-2f30-4edf-9e00-45b21d665695.jpg)
![r](https://user-images.githubusercontent.com/59083599/143859396-e4fcec47-787b-4e80-816d-a2178a7d33f9.jpg)
![R](https://user-images.githubusercontent.com/59083599/143859400-8362f840-0423-4774-9639-49ef1ddea901.jpg)
![s](https://user-images.githubusercontent.com/59083599/143859404-3687b1df-2aab-463d-a6ca-47c08be239bb.jpg)
![S](https://user-images.githubusercontent.com/59083599/143859405-610bdbb7-83f6-47bb-9bec-ddf3a7707ba0.jpg)
![t](https://user-images.githubusercontent.com/59083599/143859408-bc72e343-6ca8-4434-bcad-8f06ff6cdcf1.jpg)
![T](https://user-images.githubusercontent.com/59083599/143859410-2056ecc8-0689-43ef-97a9-fc2dc0dd9de5.jpg)
![u](https://user-images.githubusercontent.com/59083599/143859412-481a5a9e-0eb4-4247-85d7-8b9cc8d68ea2.jpg)
![U](https://user-images.githubusercontent.com/59083599/143859414-a7741b2e-595b-47b7-b07a-d17626826880.jpg)
![v](https://user-images.githubusercontent.com/59083599/143859416-5363537e-a564-4063-a78f-6f1566b0c83c.jpg)
![V](https://user-images.githubusercontent.com/59083599/143859418-0e1ac66c-920a-48f6-b013-a6e2acf94dcb.jpg)
![w](https://user-images.githubusercontent.com/59083599/143859422-0a9acf23-bd76-4803-b591-3d4aeb56a836.jpg)
![W](https://user-images.githubusercontent.com/59083599/143859423-c375bd06-0d0a-4be0-b793-e56d536c7780.jpg)
![x](https://user-images.githubusercontent.com/59083599/143859424-53a7acaf-4db1-4cf0-ac9f-b32d755c16ff.jpg)
![X](https://user-images.githubusercontent.com/59083599/143859427-f5018906-d48e-4d3a-9bca-0aa51f026387.jpg)
![y](https://user-images.githubusercontent.com/59083599/143859432-907221aa-0be5-43aa-95fd-cbda99d9c6cf.jpg)
![Y](https://user-images.githubusercontent.com/59083599/143859435-8a0f58a7-1e37-47e8-ac12-26ada2c79a23.jpg)
![z](https://user-images.githubusercontent.com/59083599/143859437-1aa5b10d-bcd8-4377-9e62-6f43174f8e5c.jpg)
![Z](https://user-images.githubusercontent.com/59083599/143859438-d85c7f57-4ba5-4282-a907-eedfbff92f99.jpg)

`{a..z} {A..Z} {0..9}` in our for loop tells our shell to iterate thru numbers 0 to 9, characters from a to z and A to Z one by one

we also used a custom font with `-font` called `nerd.ttf` which was actually `Caskaydia Cove Nerd Font Mono` which i renamed for simplicity and put inside the folder i'm making these images, you can also pass the abseloute path to it in your filesystem 

the mono in that font name refers to every character taking the same width as other, these fonts are typically used in ascii art, terminal emulators and code editors to easily be able to read them but i'm using the mono variant because it's easier to fit into the image

## printing special characters
special characters are harder to work with since they are not aload to be used in file names in windows specially so because we want to have a cross-platform solution we convert their file names to their hex counterparts, note that this command is a zsh exclusive command and doesn't work on bash
```
for char in {\!..\)} \@ \` {\*..\/} {\:..\?} {\[..\^} {\{..\~} ; do printf -v hex '%02X' $(( #char )) ; convert -gravity center -trim -background yellow -fill black -font ./nerd.ttf -size 30x30 -extent 30x30 caption:$char $hex.jpg ; done
```
![2A](https://user-images.githubusercontent.com/59083599/143861236-049dd0b8-7591-4906-b322-7d76f845b229.jpg)
![2B](https://user-images.githubusercontent.com/59083599/143861238-af7329f0-4dfe-4b45-8bf4-1c1923e7779b.jpg)
![2C](https://user-images.githubusercontent.com/59083599/143861239-100161af-6962-4e13-b6d8-b27aedb90740.jpg)
![2D](https://user-images.githubusercontent.com/59083599/143861242-279b38c3-48e6-4825-830e-99f43829594d.jpg)
![2E](https://user-images.githubusercontent.com/59083599/143861247-d7bda9e3-3dea-4561-89b5-3c7e1565715d.jpg)
![2F](https://user-images.githubusercontent.com/59083599/143861252-6f342676-9767-4f14-affc-1b786b1a4c00.jpg)
![3A](https://user-images.githubusercontent.com/59083599/143861254-31384c9c-0b8d-467e-8efe-7ab913ee045f.jpg)
![3B](https://user-images.githubusercontent.com/59083599/143861256-ecb154de-fb84-43d1-8d09-7fddc6540c52.jpg)
![3C](https://user-images.githubusercontent.com/59083599/143861263-8479dcf5-4584-42fa-bc6e-ccb89cbce1cd.jpg)
![3D](https://user-images.githubusercontent.com/59083599/143861265-fbecd40d-95cf-45a0-9009-883405596fc1.jpg)
![3E](https://user-images.githubusercontent.com/59083599/143861269-68162cca-e7c2-40dd-abae-ffce2ba0586c.jpg)
![3F](https://user-images.githubusercontent.com/59083599/143861270-719b588a-8c8b-4412-a5d9-c3101a2bf49a.jpg)
![5B](https://user-images.githubusercontent.com/59083599/143861273-16bc73ef-dd4a-4ac3-b2e2-4b0e5f3cab90.jpg)
![5C](https://user-images.githubusercontent.com/59083599/143861274-d776521e-6022-49f8-afdb-887ee10f8ed2.jpg)
![5D](https://user-images.githubusercontent.com/59083599/143861278-dbb49ab8-cc29-4274-b7a8-157e8ca5b769.jpg)
![5E](https://user-images.githubusercontent.com/59083599/143861283-e1eab6e8-cea3-408d-bdfc-ce28ddaa469c.jpg)
![7B](https://user-images.githubusercontent.com/59083599/143861286-b16bbbcf-d234-4d61-bc9e-2095d635acfd.jpg)
![7C](https://user-images.githubusercontent.com/59083599/143861287-c08e01a8-7b2b-4a9c-a649-cc373ab67aa7.jpg)
![7D](https://user-images.githubusercontent.com/59083599/143861290-6290d37d-db8f-4cc7-ac97-c88c0c12e297.jpg)
![7E](https://user-images.githubusercontent.com/59083599/143861295-8a53fad3-7c57-42bf-ad2e-08e469c71650.jpg)
![21](https://user-images.githubusercontent.com/59083599/143861297-a82ccd5b-7b1e-4149-b3e4-b292cba54c01.jpg)
![22](https://user-images.githubusercontent.com/59083599/143861298-de2e114f-a22c-40e6-a8dc-ed9cb9166457.jpg)
![23](https://user-images.githubusercontent.com/59083599/143861302-636f55e9-3d2b-4c8d-b5ce-65491784eaa5.jpg)
![24](https://user-images.githubusercontent.com/59083599/143861304-6071b4ce-c69f-4f4b-b142-3a1f68629fda.jpg)
![25](https://user-images.githubusercontent.com/59083599/143861307-f4faa7b9-959f-4e88-a4d5-c6d1983febee.jpg)
![26](https://user-images.githubusercontent.com/59083599/143861311-5d402c63-c36a-4d49-9448-939d161be6fd.jpg)
![27](https://user-images.githubusercontent.com/59083599/143861313-04ef5c80-b856-40c5-a2d2-4634ae7fd7d8.jpg)
![28](https://user-images.githubusercontent.com/59083599/143861315-63c4c65d-cd88-4426-b645-6576af11bf9b.jpg)
![29](https://user-images.githubusercontent.com/59083599/143861316-0dbe40ac-eaec-4d62-8c65-6dfb896ffa35.jpg)
![40](https://user-images.githubusercontent.com/59083599/143861320-7cfe7867-6240-46c8-8c9c-f51deb5a3a61.jpg)
![60](https://user-images.githubusercontent.com/59083599/143861323-e5ec056c-cb37-432f-9474-43010a844160.jpg)

notice the segmented ranges in our for loop ``{\!..\)} \@ \` {\*..\/} {\:..\?} {\[..\^} {\{..\~}`` the reason for this is that we don't want duplicate characters as our normal characters above so we exclude the ranges they are in withing our for loop, if you don't care about file names you can do ``{" "..~}`` and combine both steps together

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
