# CS 445 - Project 1: Hybrid Images

Name (netid): Tomoyoshi Kimura (tkimura4)

**Total Points Claimed** 				**[126] / 130**
Hybrid image 

-   main result
-   Main result and description 		[45 ] / 45

FFT images of main result 		[ 15] / 15

Hybrid images: two additional results 	[ 10] / 10

 Image enhancement tasks (3rd is B&W)

-   Contrast enhancement		[8] / 10
-   Color enhancement			[10] / 10
-   Color shift				[10] / 10

Quality of results / report			[10] / 10  

Color Hybrid Image w/ explanation (B&W)	[5] / 5

Gaussian / Laplacian Pyramids (B&W)	[13] / 15

## Hybrid Image Main Result

### Original input images grayscale and aligned

<img src = "./input_img1.png" style = "zoom: 75%">

- Wolf (image 1, will be our high frequency image)
- Steve Jobs (image 2, will be our low frequency image)

<div style = "page-break-after: always" />

### Hybrid Image Result

#### Images with Filter

<img src = "./im1filter.png" style = "zoom: 30%"/><img src = "./im2filter.png" style="zoom: 30%"/>

-   This project works by filtering the two images with Laplacian filter and Gaussian filter to change the frequency of the two. I performed Laplacian filter on the wolf picture so that the details are sharpened. Only high frequency information is maintained, while low frequency information is filtered out. Steve Jobs picture is filtered with Gaussian filter so it is smoother, remaining a low frequency. I will talk more about the frequency in the FFT section. Finally, we add the two together to obtain the hybrid image that will be explained in the next section.

<div style = "page-break-after: always" />

#### Hybrid image

<img src = "./hybrid.png" style = "zoom: 50%" />

#### Cropped Hybrid Image

<img src = "./croppedhybrid.png" style = "zoom: 50%"/>

-   This is the hybrid image with wolf and Steve Jobs. In this picture, when we see closely, details of wolf such as the fur, eyes, ears, and nose are visible. However, as we move farther away, our eye tends to resize the image to a smaller scale that would perform something similar to a smooth filter. Therefore, these wolf details, or high frequency information, will be filtered and we can only capture the low frequency information, or Steve Jobs in this case. 

#### Comment

- Since the orientations orientation of the two images are quiet differnet, with the wolf's body on the left and steve jobs image on the right, and two objects have contrasting colors. To enhance the hybrid effect, I have lowered the sigma for Steve Jobs images so that the low frequency image can be easily captured when the observer is merely a few meters away. And I also have a lower sigma for high frequency image (not as low as the previous one), so that we can easily get rid of such information when we move further. However, with many limitations of the image color and orientatino, the hybrid effect might not be as strong as the second hybrid image that I will show later.  

### FFT Images

#### Original Images

<img src = "./fftim1.png" style = "zoom: 30%"/><img src="fftim2.png" style="zoom:30%"/>

-   We can see that the original frequencies of the two images are very similar, and you can't really distinguish between the two

#### Filtered Images

<img src="./fftfilter1.png" style="zoom: 30%" /><img src = "./fftfilter2.png" style = "zoom: 30%"> 

-   However, after you applied the filters. You can see that the Low Pass image has a significantly different frequency cmpared to the High Pass Image. 

#### Hybrid Image

<img src ="./ffthybrid.png" />

## Additional results

-   Other than the Wolf-Steve Jobs hybrid image, I also produce two other hybrid examples. The Trump and Biden hybrid image, and Owl and Cat hybrid image. 

### Trump and Biden

<img src = "./secinput.png" />

<div style = "page-break-after: always" />

### Hybrid Trump and Biden

<img src = "./secout.png" />

-   This hybrid image works better than the other two, because Trump and Biden, are both human beings with many common aspects, and their sizes align better. 

<div style = "page-break-after: always" />

### Cat and Owl

<img src = "./thirdinput.png"  />

<div style = "page-break-after: always" />

### Hybrid Cat and Owl

<img src = "./thirdoutput.png" />

<div style = "page-break-after: always" />

## Image enhancement tasks

### Contrast Enhancement

<img src = "./ce_input.png" style="zoom:30%"/><img src = "./ce_lap.png" style="zoom:30%"/>

-   I decided to use Laplacian filter to enhance my image. This is very similar to the sharpen filter, which is original plus original minus the smooth filter. So I first obtain the Laplacian filtered image (right), then add that to the original image (left).

<img src = "./ce_output.png" style = "zoom: 45%"/>

-   The result is not obvious, but if you look closely to the tree branches, we can see that each branch is more distinguishable from others. The blurred people, however, is not easy to spot the difference, which is reasonable if we look at the Laplacian filtered image. The Laplacian filtered image does not have many "people", and only a few objects are visible. 

### Color Enhancement

<img src = "./colore_input.png" />

<img src = "./color_output.png" />

-   For Color Enhancement, I first changed the image into HSV color orientation, and then enhanced the value. User can choose a value ranging from 0 to 100, and that will be the percentage of enhancement. Then, the user can also choose to enhance or reduce the image by changing the variable name to either enhancement or reduce. The image above is 50% enhancement. 

<div style = "page-break-after: always" />

### Color shift

<img src = "./cs_input.png" />

<img src = "./cs_red.png" style = "zoom:30%"/><img src = "./cs_output.png" style = "zoom: 30%"/>

-   I decided to use LAB image orientation to perform color shift, since LAB has a better control on the colors of the images. The bottom left is red enhancement with 30% and the right is yellow reduction with 30% by multiplying the first and second index of the third dimension. 

## Color hybrid result (B&W)

### Original Images

<img src = "./input_img1.jpeg" style = "zoom:30%"/> <img src = "./steve.jpeg" style = "zoom: 40%" />

-   These two inputs are the same as the grayscale hybrid image. I decided to have the same frequency orientation, that is , the wolf as the high frequency image and Steve Jobs as low frequency image.  It is very similar to the grayscale hybrid images, except that we don't grayscale in the beginning, and we perform merge to merge three layers of grayscaled Laplacian filtered image and add it with the gaussian filtered image.  

### Filtered Images

<img src = "./color_filter_high.png" style = "zoom: 28%"/> <img src = "./color_filter_low.png" style = "zoom: 28%"/>

-   I decided to use the wolf for High frequency image. This is because that wolf image contains so many pattern, the fur. These details are hard to eliinate in the low frequency domain, and would produce a less effective hybrid image. 

<img src = "./color_hybrid.png" />

-   The color result is not ås effective as the grayscale one because of the different color contrast and texture. 

## Laplacian Pyramid

<img src="./color_hybrid.png" style = "zoom: 50%"><img src = "./p1.png" style = "zoom: 30%" /> 

<img src = "./p2.png" style = "zoom: 20%" /><img src = "./p3.png" style = "zoom: 15%" /><img src = "./p4.png" style = "zoom: 12%" /><img src = "./p5.png" style = " zoom: 10%" />

-   This is the Laplacian pyramid. We can see that as the image got scaled down, the low frequency image, or Steve Jobs, is more visible while we lose information about the wolf.



<div style = "page-break-after: always" />

## Acknowledgement



1.   Color Enhancement Blur Image: https://live.staticflickr.com/8581/16497939987_ffba46e0b3_b.jpg

2.   Steve Jobs Image: https://www.cnbc.com/2018/10/02/steve-jobs-heres-what-most-people-get-wrong-about-focus.html

3.   Wolf Image: https://www.istockphoto.com/photos/wolf

4.   Trump Image: https://en.wikipedia.org/wiki/Donald_Trump

5.   Biden Image: https://en.wikipedia.org/wiki/Joe_Biden

6.   Cat: https://i.guim.co.uk/img/media/26392d05302e02f7bf4eb143bb84c8097d09144b/446_167_3683_2210/master/3683.jpg?width=1200&height=1200&quality=85&auto=format&fit=crop&s=49ed3252c0b2ffb49cf8b508892e452d

7.   Owl: https://cdn.technologynetworks.com/tn/images/thumbs/webp/640_360/unique-dna-packaging-in-owl-eyes-may-be-a-lens-that-enhances-night-vision-342327.webp?v=10962144

     