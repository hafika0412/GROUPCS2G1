# PROJECT OVERVIEW
## D. EXECUTING THE PROJECT
### Project Design and Coding
Flowchart Design:<br>
![image](https://user-images.githubusercontent.com/121591140/211731520-8e0cf714-10b6-43fd-8057-98d45f7e58dc.png)
<br>
### Description of the project coding and implementation
Software & Library required:
Term | Name | Version
--- | --- | ---
Software	| MATLAB	| 9.13
Library		| Image Processing Toolbox | 11.6

At the start, the coin image is read and convert to greyscale image with histogram.<br>
![image](https://user-images.githubusercontent.com/121591169/211922041-f6b9e605-be03-4c36-8176-2321d7db6c6c.png)


With using black cover and convert to greyscale image, the pixel range interval [0,255] can be separated with a obvious gap. With histogram, the pixel near to black which is near to 0 is the background, the pixel near to white which is near to 255 is coins region pixel. So here can decide the region of interest to identify the region of coins into binary image with the range [100,220]. But to reduce most of the noise cause by light reflection, it is set to [150,255]. <br>
![image](https://user-images.githubusercontent.com/121591169/211921495-8d29c106-48d9-4466-8e98-c3aab8621f45.png)

The next step is to set a threshold and make the image a binary image<br>
![image](https://user-images.githubusercontent.com/121591169/211922223-35e23e8f-b49c-4959-b2ba-1b65261faa8f.png)

After selecting the interest region, a binary image which only consist with true or false is create. The true region is coins and the false region is background. There is no obvious noise but there are holes within the coins region. With using imfill() function, the black region within the coins is fully filled with white, follow with a Morphologically Opening that Erosion to delete unobvious noises, and dilation to repair important details affect by erosion. Then a perfectly clean regions result as in the Input & Result slide will be produced.<br>
![image](https://user-images.githubusercontent.com/121591169/211922454-1a2ac7c2-e2e0-4a22-85cd-f7a1a7b68248.png)

After that, the image refinement is carried out and coins are labelled<br>
![image](https://user-images.githubusercontent.com/121591169/211922860-8a64d3de-955c-4f86-ab83-d0b50fb46e36.png)
![image](https://user-images.githubusercontent.com/121591169/211923170-ba7c6036-faee-4095-a1d7-83b961d7965c.png)
![image](https://user-images.githubusercontent.com/121591169/211923302-cf05641f-db2a-4b6c-b020-b117ae9907a7.png)

Finally, analysis and calculation.<br>
The first line is used to define variable that need to use in analysis and calculation. The outermost for loop is used to go through labelled objects. And then calculate the number of true pixel present in the object as the area, here decide the size threshold for each type of coin with the fifth line code. After deciding, change the condition statements in the if-else code. The fifth line code can be added semicolon to suppress output. The nested loop followed is used to visualise the sequence of the object, also used to detect whether there are noise still exist. Other code left are used to assign coin value based on the area then display it with a window.<br>
![image](https://user-images.githubusercontent.com/121591169/211923692-a62108c4-fb69-44ce-9fca-0dbb7be7dda4.png)

### Project Result
![image](https://user-images.githubusercontent.com/121591169/211923894-73c1949b-8703-4d32-a7fd-5994aec11914.png)

<br><br><br>
##### Next: [Project Closing](E-PROJECT_CLOSING.md)
