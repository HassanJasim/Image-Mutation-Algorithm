# Image-Mutation-Algorithm

This was the final assignment for my 2SO3 - Principles of Programming class. In this class we focused on programming in C, as well as basic data structure and algorithms.

In this assignment, we had to use a genetic algorithm to produce an image that is the closest fit to a goal image. The way the algorithm works is that it creates a population of images where the pixels are randomized. It then calculates the fitness for each individual in the population and sorts them from lowest to higher (lowest in this case being the best). It then mutates the bottom 75% of images by randomizing a certain number of pixels. It then re-sorts them according the fitness and the process continues. 

After a certain number of generations, the image with the lowest fitness is the one outputted to a new .ppm file.

The algorithm I used, specifically seen in the evolve.c file, starts with a higher rate, which then decreases as the number of generations increases. This makes it so that more pixels are mutated at the beginning, but less later on. This is done so that a lower fitness is reached quicker at the beginning, and after many generations, only a few pixels are mutated so that there is a higher chance of improving.

The goal images, then the images produced by the genetic algorithm are seen below.

![Test](https://github.com/joshuaguinness/Generating-Image/blob/master/me.jpg)  ![Test](https://github.com/joshuaguinness/Generating-Image/blob/master/me2.jpg)

![Test](https://github.com/joshuaguinness/Generating-Image/blob/master/mcmaster.jpg)  ![Test](https://github.com/joshuaguinness/Generating-Image/blob/master/mcmaster2.jpg)

To view how the transition looks, check out the gif below.

![Test](https://github.com/joshuaguinness/Generating-Image/blob/master/Generating-Image.gif)

The video was created by outputting an image every 100 fitness. I then ran a bash script to convert all the images to .jpg's, then put them together to make a video!

## What I Learned

The two ways I grew in my C programming strength while doing this assignment were in the use of pointers and dealing with memory. This assignment required a lot of working with structures as well as information inside of them, thus the use of pointers was necessary.

Due to using structures, memory allocation and then de-allocation was needed so I got further practise in using them. After running my program through valgrind, it returned with no memory leaks.

A new thing I learned while working on this program is how to profile the execution of the program. I attached a screenshot below of it. The lines of code that take up the most running time are because either they are run a lot (instead nested for loops), they access data through pointers, and/or perform multiplication operations.

## To Run

To run with the bird photo, type "make escher." To run with the McMaster logo type "make mcmaster."

To clean type "make clean"
