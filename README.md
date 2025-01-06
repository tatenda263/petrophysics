This was my term project in my Introduction to Digital Rock Petrophysics course.
For this project I used the Savonnières carbonate dataset from the Digital Rocks Portal:
https://www.digitalrocksportal.org/projects/72
The original image stack is shown below:
![image](https://github.com/user-attachments/assets/7174f098-4a48-4f7d-833a-198e552773f3)

The slices in the image stack were then aligned using the Enhanced Correlation Coefficient algorithm (RAW Alignment Code 2). 
Prior attempts using phase correlation yielded unsatisfactory results.
Parallel processing was used to improve the speed of the process.
The image was also scaled down by a factor of half.
Resulting stack is shown below:
![image](https://github.com/user-attachments/assets/30b41282-fd97-4da5-9664-9a75a005b67a)

The scaled and aligned image stack was then cropped using Fiji-ImageJ:
![image](https://github.com/user-attachments/assets/2e06af59-b987-49d1-92e8-5d32e36aa430)

Auto Otsu method within ImageJ was then used to threshold the image. Pores were given voxel values of 0 and minerals 255.
The final scaled, aligned, and thresholded image stack is shown below:
![image](https://github.com/user-attachments/assets/8c016561-35e1-49a5-b25d-5e4d9e1f2236)
![image](https://github.com/user-attachments/assets/f7159a1e-259e-4662-b97a-57ea9f6bd939)
![image](https://github.com/user-attachments/assets/1e0bbbac-9990-4a20-a09c-92d38a10005a)

Monte Carlo sampling was then used to generate random cuboid 3D samples from the image stack.
This was to enable me to calculate certain petrophysical parameters that required cuboid 3D images.

I used a random sample generator with a fixed seed.
For each seed I tried I manually went through the samples and determined which of the samples were
"high-value" i.e. did not touch the edge of the original image stack and did not include the 
outside of the image stack.

The code used for their generation is "random_sample_gen2" with the parameters I used to generate the random samples.
The number of high-value samples versus seed number is outlined in "good samples.txt"
25 samples were generated and the 11 samples chosen are shown in the table below:
![image](https://github.com/user-attachments/assets/4edc8c17-afb6-4a1b-974d-e2e052b0c16c)

In 3D, the 25 samples generated are shown below:
![image](https://github.com/user-attachments/assets/a9e7a156-a1a3-436b-861c-f80f2c6fc1cc)
The high-value samples selected are shown in red:
![image](https://github.com/user-attachments/assets/c9fe1701-81a5-492e-9117-998eb9ddc9b4)

These were then used to calculate the petrophysical properties of the Savonnières carbonate.
