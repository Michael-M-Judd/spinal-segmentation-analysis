cmake_minimum_required(VERSION 2.8.9)

project(spinal-segmentation-analysis)

#-----------------------------------------------------------------------------
# Extension meta-information
set(EXTENSION_HOMEPAGE "http://slicer.org/slicerWiki/index.php/Documentation/Nightly/Extensions/spinal-segmentation-analysis")
set(EXTENSION_CATEGORY "Segmentation")
set(EXTENSION_CONTRIBUTORS "Michael Reid (AnyWare Corp.), Michael Judd")
set(EXTENSION_DESCRIPTION "Python Module, segmenting spinal column. CISC 472 Final Project.")
set(EXTENSION_ICONURL "http://www.example.com/Slicer/Extensions/spinal-segmentation-analysis.png")
set(EXTENSION_SCREENSHOTURLS "http://www.example.com/Slicer/Extensions/spinal-segmentation-analysis/Screenshots/1.png")
set(EXTENSION_DEPENDS "NA") # Specified as a space separated string, a list or 'NA' if any

#-----------------------------------------------------------------------------
# Extension dependencies
find_package(Slicer REQUIRED)
include(${Slicer_USE_FILE})

#-----------------------------------------------------------------------------
# Extension modules
add_subdirectory(spinal-segmentation)
add_subdirectory(test)
add_subdirectory(SpineSeg)
## NEXT_MODULE

#-----------------------------------------------------------------------------
include(${Slicer_EXTENSION_CPACK})
