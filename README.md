# viewer4Dflow
A simple and fast MATLAB based GUI for visually inspecting 4D flow MRI data. Supports UW Madison's PCVIPR data format. Can be installed as an app to MATLAB with the .mlappinstall file. It can also be called from the command line if you add the .mlapp file to your MATLAB path.

<img width="829" alt="image" src="https://github.com/user-attachments/assets/7e6ff0a9-3688-4416-a82f-a6ff43b00b9d" />

## Input arguments for the command line

viewer4Dflow

viewer4Dflow(data)

data can be either:
* a 3D matrix [X Y Z]
* a 4D matrix [X Y Z t]
* or a MATLAB struct with multiple encodes according to this format (capitalized is time-averaged [X Y Z], lowercase is time-resolved [X Y Z t]):
```
  data
    data.header
        data.header.matrixx
        data.header.matrixy
        data.header.matrixz
        data.header.frames
          .
          .
          .
    data.MAG
    data.CD
    data.VEL1
    data.VEL2
    data.VEL3
    data.mag
    data.cd
    data.vel1
    data.vel2
    data.vel3
```
