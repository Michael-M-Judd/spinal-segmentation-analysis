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

## Discussion and Future of Project

Were we to continue our project in the future, some of our goals for the final implementation of the spine segmentation would be the following:

We would begin by developing a more perfect way of thresholding and modeling the individual vertebrae of the spine. In particular, using a statistical shape model for spines would help us reduce processing time and improve results for 3D representation in Slicer or other visualization programs [1]. The most likely issues would be the variability of spinal shape and on a greater level individual vertebral shape in the population. Using pre-existing data for the physiological variability of vertebral body volumes would help us to minimize this issue, however [2]. By using Statistical shape modeling (SSM) we will be able to represent the shape variability of individual vertebrae as well as perform partially automatic segmentation and 3D model generation of the spine, possibly aiding surgical planning. 

![alt tag](http://i.imgur.com/sHaNF3m.png)

Fig 1. Flow diagram for generating a surface shape model from input CT scans.

By using known vertebral body volume we can ensure we maintain consistent and accurate results when performing SSM [3]. In effect, we can minimize the over/under representation of portions of the spine and create a more perfect model.

Another form of segmentation could be found using the GrowCut method [4]. By using a random number of points and converging on a natural segmentation we may be able to make image segmentation even faster than by using Statistical Shape Modeling.

![alt tag](http://i.imgur.com/PKezAnz.png)

Fig 2. Proof of concept showing fiducial land marks scattered across vertebral model and segmentation of individual vertebra.

## Referenced Works

1. Marine Clogenson, John M. Duff, Marcel Luethi, Marc Levivier, Reto Meuli, Charles Baur, Simon Henein (2014) A statistical shape model of the human second cervical vertebra
2. Tobias Heimann, Hervé Delingette (2013) Model-based Segmentation
3. Limthongkul W., Karaikovic EE, Savage JW, Markovic A (2010) Volumetirc analysis of thoracic and lumbar vertebral bodies
4. Jan Egger, Christoph Kappus, Barbara Carl, Christopher Nimsky (2013) GrowCut Based Vertebral Body Segmentation with 3D Slicer
