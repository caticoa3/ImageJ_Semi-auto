# ImageJ_Semi-auto
ImageJ Scripts for Microscope Images of Florescently Labled Cells
Color Merge Script

To analyze cells in different experimental conditions, image analysis was necessary.  
Cells were labeled with three fluorescent probes indicative of nuclei, proliferating cells, and cell type (DAPI, CY5, and CY3, respectively).  
Images were captured using light at the excitation wavelengths of each fluorescent label.

![Same area imaged with three excitation wavelengths](https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/BeforeRGB_Labeled1.png)
                 
The script applies a color to images based on file name “suffix” (DAPI -> Blue, CY5 -> Green, and CY3 -> Red).
![Pseudo-color applied](https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/20a.5_RGB_Montage.png)
 
The script then merges the color images into a RGB image stack based on file name “prefix” (i.e. - 20a.5)
<p align="center">
  <img src="https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/20a.5(RGB)_Merged.png?raw=true" alt="RGB Merged"/>
  \n20.5a
</p>
<p align="center">
  20.5a
</p>

When manually counting positively labeled cells, each color (red, green or blue) in the merged image can be scrolled through in the image stack; instead of switching between images in different windows. 
Images overlaid with this script allows the investigator to: 
1) More easily compare and analyze differences between images and experimental conditions
2) Merge batches of 100s of images, saving time by not having to manually color and merge images
3) Save one file with image counts instead of three files
