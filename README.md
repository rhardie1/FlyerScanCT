# FlyerScanCT
Computer aided detection (CAD) of lung nodules in CT scans [1-3]. This is a traditional handcrafted-feature-based CAD system. This release uses the system described in [1] with updated support vector machine classifier as described in [3]. The system is trained as described in [1] using 2.5 mm thickness CT scans. The system takes as input a folder of .dcm files from a CT exam and produces a JSON text file of all detections ordered from most suspicious to least suspicious. The coordinates of the center of each detection are given as well as the bounding box dimensions. The coordinates are in units of mm with respect to 'ImagePositionPatient' in CT scan from DICOM headers. The output format provided here is similar to that used by the MONAI detection system [4-5]. 

# License
FlyersScan is released under Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International Public License (CC BY-NC-ND 4.0)

# Installation and Use
This implementation has been created in MATLAB and deployed using the MATLAB compiler. 

Explain the installation and use here...

# Test Data
Test cases may be found on The Cancer Imaging Archive (TCIA) here:
https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=1966254

We tested and verified case LIDC-IDRI-0003. Download the folder of .dcm files for this case.

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
