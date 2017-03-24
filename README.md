# ImageJ_Semi-auto
ImageJ Scripts for Microscope Images of Florescently Labled Cells

--------------------------------------------------------------------------------------------------------------------------------------
# Color Merge Script

To analyze cells in different experimental conditions, image analysis was necessary.  
Cells were labeled with three fluorescent probes indicative of nuclei, proliferating cells, and cell type (DAPI, CY5, and CY3, respectively).  
Images were captured using light at the excitation wavelengths of each fluorescent label.

![Same area imaged with three excitation wavelengths](https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/BeforeRGB_Labeled1.png)
                 
The script applies a color to images based on file name “suffix” (DAPI -> Blue, CY5 -> Green, and CY3 -> Red).
![Pseudo-color applied](https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/20a.5_RGB_Montage.png)
 
The script then merges the color images into a RGB image stack based on file name “prefix” (i.e. - 20a.5)
<p align="center">
  <img src="https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/20a.5(RGB)_Merged.png?raw=true" alt="RGB Merged"/>
</p>
<p align="center">
  20.5a
</p>
When manually counting positively labeled cells, each color (red, green or blue) in the merged image can be scrolled through in the image stack; instead of switching between images in different windows. 
Images overlaid with this script allows the investigator to:

1) Easily compare and analyze differences between images and experimental conditions
2) Merge batches of 100s of images, saving time by not having to manually color and merge images
3) Save one file with image counts instead of three files

--------------------------------------------------------------------------------------------------------------------------------------
# Automated Image Analysis Script
<p align="center">
  <img src="https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/WindowShots1.PNG?raw=true" alt="Input GUI"/>
</p>
Scripted ImageJ to perform the following tasks:
1)	Automatically count the number of cells (DAPI labeled nuclei)
2)	Automatically count the number of cells that had proliferated (CY5 labeled nuclei) 
3)	Help determine which cells had changed into a specific cell type (CY3 label).   

The script was designed to identify positively labeled cells based on intensity and morphology.  

A folder with the images of interest is selected.  Cells/pixels with CY3 intensity within the input threshold range are highlighted in red, see “Analysis of 20a.5 CY3” in proceeding image montage.

In this case a web-like morphology is indicative of the cells of interest.  This morphology fits better in a circular area rather than an elongated area.  Therefore, values for circularity from 0.6 to 1 (where 1 is a circle) are appropriate.  The script then highlights cells or clusters of pixels (within the intensity threshold) in white, if their circularity and area are within the values set in the “Particle Sizes to Count” prompt.  
	
Eliminates guessing if the intensity of a cell indicates the cell is positively labeled.
The script guides the researcher to count only those cells with the appropriate morphology.
<p align="center">
  <img src="https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/WindowShots2.PNG?raw=true" alt="Input GUI and Results Table"/>
</p>

Similarly for images of CY5 and DAPI labeled nuclei (Rows 2 – 4 in proceeding image).  The script can accurately count nuclei because they are spaced apart and their contrast or intensity above background “noise” is large.  

A positive count creates an outline of the cell nuclei which is color coded and overlaid on the nuclei (DAPI image).  Outlines in red, blue and green indicate positive DAPI, CY5, and CY3 counts (see images labeled “Analysis of …” in proceeding image montage).

Counts for images from multiple fields of views in the selected directory are printed into a table, which can then be compiled into excel for data processing and statistical analysis.  

This script analyzes images in batches, saves time, and makes the analysis more accurate and far less cumbersome compared to manual analysis.

<p align="center">
  <img src="https://github.com/caticoa3/ImageJ_Semi-auto/blob/master/ReadMe_images/SemiAutomatic_Image_Analysis.png?raw=true" alt="Semi-automated Cell Analysis"/>
</p>
