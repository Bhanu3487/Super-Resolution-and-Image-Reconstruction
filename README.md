# Super-Resolution-and-Image-Reconstruction

Begin by exploring the instructor's notebook that introduces the application of Random Fourier Features (RFF) for image reconstruction. Demonstrate the following applications using the cropped image from the notebook:

Superresolution: perform superresolution on the image shown in notebook to enhance its resolution by factor 2. Show a qualitative comparison of original and reconstructed image. 
The above only helps us with a qualitative comparison. Let us now do a quantitative comparison. First, skim read this article: https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Super-Resolution 
Start with a 400x400 image (ground truth high resolution).
Resize it to a 200x200 image (input image)
Use RFF + Linear regression to increase the resolution to 400x400 (predicted high resolution image)
Compute the following metrics:
RMSE on predicted v/s ground truth high resolution image
Peak SNR
Completing Image with Random Missing Data: Apply RFF to complete the image with 10%, 20%, and so on up to 90% of its data missing randomly. Randomly remove portions of the data, train the model on the remaining data, and predict on the entire image. Display the reconstructed images for each missing data percentage and show the metrics calculated above. What do you conclude?. 
Use the instructor's notebook on matrix factorisation, and solve the following questions.

Image Reconstruction- Here, ground truth pixel values are missing for particular regions within the image- you don't have access to them.

Use the above image from Q4 and reconstruct the image in the following two cases, where your region is-

a rectangular block of 30X30 is assumed missing from the image.
a random subset of 900 (30X30) pixels is missing from the image.
Choose rank r yourself. Perform Gradient Descent till convergence, plot the selected regions, original and reconstructed images, compute the metrics mentioned in Q4 and write your observations. Obtain the reconstruction using RFF + Linear regression and compare the two. 

Vary region size (NxN) for N = [20, 40, 60, 80] and perform Gradient Descent till convergence. Again, consider the two cases for your region as mentioned in Part (a). Demonstrate the variation in reconstruction quality by making appropriate plots and metrics. 

Write a function using this reference and use alternating least squares instead of gradient descent to repeat Part 1, 2 of Q5, using your written function. 

Data Compression- Here, ground truth pixel values are not missing- you have access to them. You want to explore the use of matrix factorisation in order to store them more efficiently.

Consider an image patch of size (NxN) where N=50. We are trying to compress this patch (matrix) into two matrices, by using low-rank matrix factorization. Consider the following three cases-
a patch with mainly a single color.
a patch with 2-3 different colors.
a patch with at least 5 different colors.
Vary the low-rank value as r = [5, 10, 25, 50] for each of the cases. Use Gradient Descent and plot the reconstructed patches over the original image (retaining all pixel values outside the patch, and using your learnt compressed matrix in place of the patch) to demonstrate difference in reconstruction quality. Write your observations.


Here is a reference set of patches chosen for each of the 3 cases from left to right.

Image 1 Image 2 Image 3
