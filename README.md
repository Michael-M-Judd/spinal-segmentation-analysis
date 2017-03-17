# Welcome to the Spinal Segmentation Wiki!

This is a work in progress project where over the course of the next few weeks we'll be updating the wiki for information on how to use the module, and how we solved the spinal segmentation problem.

## Our approach to the problem

Currently there is no perfect way to solve a spinal segmentation problem, and spines with scoliosis and kyphosis make segmentation even more difficult. We're going to attempt to get accurate segmentations, and once we have the segmented images, we'd like to run an image reconigition algorithm to try and tell if the segmented image is a patient with scoliosis or not.

## User Guide

In order to use this module, you'll need 3D Slicer installed on your computer and the module downloaded. Fork the repository to get a working copy of the repository.

1. Once you've installed Slicer 3D and downloaded the module, you'll have to add the module to slicer.
2. Adding a module can be done by going to Edit > Application Settings (Or by pressing Ctrl+2). Once you're in Application settings, navigate to the Modules tab and add the file path of the downloaded spinal-segmentation-analysis folder where the spineSeg module is located.
3. Once the module has been added, select the Spinal Segmentation Module from the module section of Slicer.
4. You'll now see the interface on the side. Here is where you can select the type of filtering you'd like to choose and what output to send it to. 
5. Load your chosen CT spinal data by pressing the data button and adding the path to your CT file (.mrml or .nrrd) , preferably a CT scan of a spine with scoliosis as this module was specifically designed for segmenting those spines.
6. Select the type of filters to segment the spine from the drop-down menu.
7. Depending on your choice of filter, you will be presented with a few different choices of parameters to set for the filter to get a perfect segmentation, modify these for the best image.
8. Once all parameters have been filled, press "Segment". This does take some time but should output the proper segmentation of the spine.
9. The final product should look something like this: (insert sucessful segmentation here)

