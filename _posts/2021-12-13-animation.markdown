---
layout: posts
title:  "Emedding animated GIFs in pdf using LaTeX"
date:   2021-12-13 14:59:14 +0530
categories: jekyll update
excerpt: " "
header:
  overlay_image: /assets/images/code.jpg
  overlay_filter: rgba(255, 0, 0, 0.5)
---
# Question:

- Download a random animated GIF from internet
- Use necessary packages in LaTeX
- Make a single slide presentation that renders the animated GIF

## Solution

To embed an animated GIF in a beamer presentation, we first need to break the GIF into a sequence of several images(.png files). The command to be used is

sh
convert -coalesce GIFname.gif correspondingimagesname.png
 
Then all the images have to be animated using the `\usepackage{animate}` and the command `\animategraphics` in the following way :-

    \documentclass{beamer}\usetheme{Boadilla}
    \usepackage{animate}%package for animating
    \begin{document}
        \begin{frame}
	        \title{4\\Inserting GIFs in Beamer}
	        \author{Khandenath Parth Shivdatta, Madhur Jain, Arjit Bhamu}
		    \maketitle
		    \centering  %to keep the GIF at center
		    \animategraphics[width=7 cm,loop]{20}{KeHa-}{0}{78} 
	    \end{frame}
    \end{document}
    
    
![image](/assets/images/ani.jpeg)

In the above command of \animategraphics :


1. loop makes the GIF keep restarting and stay in in a loop
2. width sets the width for the GIF
3. framerate of GIF=20ms
4. KeHa is the common part in names of all images and the {0}and{78}ensures that all images, right from KeHa-0 to KeHa-78 are included in the GIF

### Frames appear in following way:


| Frames | 20 | 40 | 60 |
|--------|----|----|----|
| Second | 1  | 2  | 3  |
