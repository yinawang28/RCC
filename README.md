## Redundant cross-correlation drift correction for super-resolution localization microscopy

This source code is distributed as accompanying codes for the article “ [Localization events-based sample drift correction for localization microscopy with redundant cross-correlation algorithm](https://www.osapublishing.org/oe/abstract.cfm?uri=oe-22-13-15982)” in Optics Express by B. Huang, et al.

The functions in the code are independent of any additional Matlab toolbox. Script “RCC.m” is the main function of redundant cross-correlation drift correction algorithm, which calls the other six functions for spatial bins of localizations, cross-correlation map calculation and shifts tracking. 

The input and output information for the RCC function are listed below:
**Input**: 
  - *coords*: localization coordinates     [x(in pixel), y(in pixel), frame number], 
  - *segpara*:      	segmentation parameters (time window, frame)	      
  - *imsize*:       	width or height of an squared image	(pixel)
  - *pixelsize*:      	camera pixel size 		(nm)
  - *binsize*:        spatial bin pixel size		(nm)	
  - *rmax*:         	residual error threshold 	(pixel)
  
**Output**:   	
  - *coordscorr*:    	localization coordinates after correction  [xc(in pixel) yc(in pixel)] 
  - *finaldrift*:      	drift curve 
(save A and b matrix of the over-determined linear equations for other analysis)

Call example in Matlab command window:
[coordscorr, finaldrift, Asave,bsave] = RCC(coords, 200, 256,150, 30, 0.2);