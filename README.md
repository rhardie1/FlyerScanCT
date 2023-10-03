# FlyerScanCT
Computer aided detection (CAD) of lung nodules in CT scans [1-3]. This is a traditional handcrafted-feature-based CAD system. This release uses the system described in [1] with updated support vector machine classifier as described in [3]. The system is trained as described in [1] using 2.5 mm thickness CT scans. The system takes as input a folder of .dcm files from a CT exam and produces a .json text file of all detections ordered from most suspicious to least suspicious. The coordinates of the center of each detection are given as well as the bounding box dimensions. The coordinates are in units of mm with respect to 'ImagePositionPatient' in CT scan from DICOM headers. The output format provided here is similar to that used by the MONAI detection system [4-5]. 

# License
FlyersScan is released under Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International Public License (CC BY-NC-ND 4.0).

Copyright © 2023 University of Dayton

# Installation and Use
This implementation has been created in MATLAB and deployed using the MATLAB compiler for Windows. 

1. Install MATLAB Runtime and the FlyerScan CT executable by double clicking on **MyAppInstaller.exe**.
2. The FlyerScan CT app my be executed by double clicking the **flyerscan.exe** executable file, or calling the function from the DOS command window, or by using a batch file (see **main.bat**).
3. Calling the executable file with no input arguments will bring up a user interface to chose a folder of .dcm files to process. In this case, the output will automatically be called "flyerscan_output.json".
4. The file "main.bat" shows how to run the executable in batch form where you can specify the input folder and output file name. Simply edit the .bat file and then double click the .bat file. Or execute a similar command as that illustrated in "main.bat" from the command window.
5. Make sure that you have write permission where the output is defined. By default the output goes where the executable is.

An example of a command line execution (or batch file) is shown below with the first input being the .json output name and the second being the input folder path:

flyerscan "flyerscan_output_0003" ".\LIDC-IDRI-0003\01-01-2000-NA-NA-94866\3000611.000000-NA-03264". 

The input folder is assumed to contain a series of .dcm files making up a full thoracic CT exam. The output will be in a file named "flyerscan_output_0003.json" in this case.

The "box" field of the outputs detection coordinates relative to 'ImagePositionPatient' in the CT scan from DICOM headers using the Left, Posterior, Superior (LPS) coordinate system. Each detection has a "box" output as follows: <br>
[ <br>
central x position in mm <br>
central y position in mm <br>
central z position in mm <br>
bounding box size in x in mm <br>
bounding box size in y in mm <br>
bounding box size in z in mm <br>
] <br>
The "score" field lists the support vector machine output for each detection in the same order as "box" and ordered from most suspicious to least suspicious.

# Test Data
Test cases may be found on The Cancer Imaging Archive (TCIA) here:
https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=1966254

We tested and verified case LIDC-IDRI-0003 and included the output for reference here (**flyerscan_output_0003.json**). Download the folder of .dcm files for this case and verify the output matches the one provided here.

## References
1. Messay T, Hardie RC, Rogers SK. A new computationally efficient CAD system for pulmonary nodule detection in CT imagery. Med Image Anal. 2010;14(3):390-406. doi:10.1016/j.media.2010.02.004 (https://doi.org/10.1016/j.media.2010.02.004)

2. Narayanan BN, Hardie RC, Kebede TM. Performance analysis of a computer-aided detection system for lung nodules in CT at different slice thicknesses. J Med Imaging (Bellingham). 2018;5(1):014504. doi:10.1117/1.JMI.5.1.014504 (https://doi.org/10.1117/1.JMI.5.1.014504)
   
3. B. N. Narayanan, R. C. Hardie and T. M. Kebede, "Performance Analysis of Feature Selection Techniques for Support Vector Machine and its Application for Lung Nodule Detection," NAECON 2018 - IEEE National Aerospace and Electronics Conference, Dayton, OH, USA, 2018, pp. 262-266, doi: 10.1109/NAECON.2018.8556669. (https://ieeexplore.ieee.org/document/8556669)

4. https://catalog.ngc.nvidia.com/orgs/nvidia/teams/monaitoolkit/models/monai_lung_nodule_ct_detection
   
5. https://github.com/Project-MONAI/tutorials/tree/main/detection


## BibTeX

  @article{Messay2010,
  title={A new computationally efficient CAD system for pulmonary nodule detection in CT imagery},
  author={Temesguen Messay and Russell C. Hardie and Steven K. Rogers},
  journal={Medical image analysis},
  year={2010},
  volume={14 3},
  pages={390-406},
  url={ https://doi.org/10.1016/j.media.2010.02.004 }
}

@article{Narayanan2018A,
author = {Barath Narayanan Narayanan and Russell Craig Hardie and Temesguen Messay Kebede},
title = {{Performance analysis of a computer-aided detection system for lung nodules in CT at different slice thicknesses}},
volume = {5},
journal = {Journal of Medical Imaging},
number = {1},
publisher = {SPIE},
pages = {014504},
keywords = {computer-aided detection, computed tomography, lung nodules, slice thickness, downsampling, Lung, Computed tomography, Computer aided diagnosis and therapy, CAD systems, Computer aided design, Computing systems, Computer simulations, Sensors, Lung cancer},
year = {2018},
doi = {10.1117/1.JMI.5.1.014504},
url = { https://doi.org/10.1117/1.JMI.5.1.014504 }
}

@INPROCEEDINGS{Narayanan2018B,
  author={Narayanan, Barath Narayanan and Hardie, Russell C. and Kebede, Temesguen M.},
  booktitle={NAECON 2018 - IEEE National Aerospace and Electronics Conference}, 
  title={Performance Analysis of Feature Selection Techniques for Support Vector Machine and its Application for Lung Nodule Detection}, 
  year={2018},
  volume={},
  number={},
  pages={262-266},
  doi={10.1109/NAECON.2018.8556669},
  url = { https://ieeexplore.ieee.org/document/8556669 }
  }
