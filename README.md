# dissect-contracking_cem

### Breakdown steps
(1) setup options and scene
> - opt=readConOptions('config/default3d.ini');
> - load `config/default3d.ini` by default
> - config sections
>   - [Parameters]
>   - [General]
>   - [Initialization]
>   - [Detections]
>   - [Appearance]
>   - [Miscellaneous]

(2) fill scene info by `sceneInfo=getSceneInfoConDemo;`
> - required field
>   -   detfile         detections file (.idl or .xml)
>   -   frameNums       frame numbers (eg. frameNums=1:107)
>   -   imgFolder       image folder
>   -   imgFileFormat   format for images (eg. frame_%04d.jpg)
>   -   targetSize      approx. size of targets (default: 5 on image, 350 in 3d)
> - Required for 3D Tracking only
>   -   trackingArea    tracking area
>   -   camFile         camera calibration file (.xml PETS format)
> - Optional:
>   -   gtFile          file with ground truth bounding boxes (.xml CVML)
>   -   initSolFile     initial solution (.xml or .mat)
>   -   targetAR        aspect ratio of targets on image
>   -   bgMask          mask to bleach out the background

(3) detections are computed already. Should be using DPM and in the same format 
