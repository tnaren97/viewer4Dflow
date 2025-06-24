# viewer4Dflow
A simple and fast MATLAB based GUI for visually inspecting 4D flow MRI data. Can be installed as an app to MATLAB with the .mlappinstall file. It can also be called from the command line if you add the .mlapp file in a folder to your MATLAB path.

Input arguments for the command line:

viewer4Dflow()
viewer4Dflow(<data>)

<data> can be either:
a 3D matrix
a 4D matrix
or a MATLAB struct with multiple encodes according to this format (capitalized is time-averaged, lowercase is time-resolved):
data
  data.header
    data.header.matrixx
    data.header.matrixy
    data.header.matrixz
    sdata.header.frames
    ...
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

<img width="829" alt="image" src="https://github.com/user-attachments/assets/7e6ff0a9-3688-4416-a82f-a6ff43b00b9d" />

