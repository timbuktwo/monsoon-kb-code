---
title: "Image Magick Commands"
date: 2022-01-28T16:32:56-07:00
draft: false
toc: false
images:
tags:
---


## ImageMagick for converting HEIC and stripping Exif data on Mac

1. Create a directory with HEIC files
2. Batch rename all files (select all photos > right click > rename > format > custom format: photo > Start numbers at: 1)
3. Launch Terminal >  `CD` to directory
4. `mogrify -format jpg *.HEIC` (converts HEIC to JPG)
5. `rm *.HEIC`(removes HEIC files)
6. `Mogrify -strip *jpg` (strips EXIF data)
