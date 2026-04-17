# viewer4Dflow

![image](image.png)

A simple and fast MATLAB based GUI for visually inspecting 4D flow MRI data.
Supports the following data formats:

* PCVIPR binary file format (.dat)
* PCVIPR HDF5 file format (.h5)
* PCVIPR Enhanced DICOMs
* GE 4D Flow DICOMs

## Functionality

viewer4Dflow can

* Visualize time-averaged and time-resolved 3D data with multiple encodes
* Flip and rotate images
* Export time-resolved movies as GIFs or videos

## Installation

Can be installed as an app to MATLAB with the .mltbx file

* In the MATLAB toolbar, click Apps > Install App
* Navigate to the location of this repository and select the viewer4Dflow.mltbx file in the release folder
* App should now be visible in the My Apps section

Alternatively, it can also be called from the command line if you add the .mlapp file to your MATLAB path.

* In the MATLAB toolbar, click Home > Set Path
* Click Add Folder
* Select folder containing viewer4Dflow.mlapp


## Command Line Arguments

```MATLAB
% Load GUI normally
viewer4Dflow

% Load existing 4D flow struct from workspace variable (format described below)
viewer4Dflow(data=imageData)

% Load existing 3D or 4D matrix from workspace variable ([X Y Z] or [X Y Z T])
viewer4Dflow(matrix=imageMatrix)

% Load file from filepath (pass in path to either pcvipr_header.txt, *.h5, or *.dcm)
viewer4Dflow(filepath="<path>/<to>/<file>")

% Load only time-averaged data
viewer4Dflow(..., tavg=True)
```

4D flow data is stored internally as MATLAB struct with this format:

```MATLAB
imageData
    imageData.header
        imageData.header.matrixx
        imageData.header.matrixy
        imageData.header.matrixz
        imageData.header.frames
        imageData.header.VENC  % mm/s
          .
          .
          .
    imageData.MAG    % time-averaged magnitude           [X Y Z]
    imageData.CD     % time-averaged complex difference  [X Y Z]
    imageData.VEL1   % time-averaged velocity 1          [X Y Z]
    imageData.VEL2   % time-averaged velocity 2          [X Y Z]
    imageData.VEL3   % time-averaged velocity 3          [X Y Z]
    imageData.mag    % time-resolved magnitude           [X Y Z T]
    imageData.cd     % time-resolved complex difference  [X Y Z T]
    imageData.vel1   % time-resolved velocity 1          [X Y Z T]
    imageData.vel2   % time-resolved velocity 2          [X Y Z T]
    imageData.vel3   % time-resolved velocity 3          [X Y Z T]
  
```

