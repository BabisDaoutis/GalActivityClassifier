# GalActivityClassifier
Random Forest mid-IR-optical broad-band galaxy activity classifier

Repository for galaxy activity clasifier from the paper "A versatile classification tool for galactic activity using optical and infrared colors"\
Astronomy & Astrophysics\
ArXiv: https://arxiv.org/abs/2310.02888 \
ADS: https://ui.adsabs.harvard.edu/abs/2023A%26A...679A..76D/abstract \
Publisher (A&A): https://www.aanda.org/articles/aa/full_html/2023/11/aa47016-23/aa47016-23.html

**Authors:**\
Charalampos Daoutis, Elias Kyritsis, Konstantinos Kouroumpatzakis, and Andreas Zezas

### Abstract 
**Context.**  The overwhelming majority of diagnostic tools for galactic activity are focused mainly on the classes of active galaxies.
Passive or dormant galaxies are often excluded from these diagnostics which usually employ emission line features (e.g., forbidden
emission lines). Thus, most of them focus on specific types of activity or only on one activity class (e.g., active galactic nuclei or
AGN). \
**Aims.** In this work, we use infrared and optical colors in order to build an all-inclusive galactic activity diagnostic tool that can
discriminate between star-forming, AGN, LINER, composite, and passive galaxies, and which can be used in local and low-redshift
galaxies. \
**Methods.** We use the random forest algorithm in order to define a new activity diagnostic tool. As ground truth for the training of the
algorithm, we consider galaxies that have been classified based on their optical spectral lines. We explore classification criteria based
on infrared colors from the first 3 WISE bands (bands 1, 2, and 3) supplemented with optical colors from the u, g, and r SDSS bands.
From these we seek the combination with the minimum number of colors that provides optimal results. Furthermore, to mitigate
biases related to aperture effects, we introduce a new WISE photometric scheme combing different sized apertures. \
**Results.** We develop a diagnostic tool using machine learning methods that accommodate both active and passive galaxies under
one unified classification scheme using just 3 colors. We find that the combination of W1-W2, W2-W3, and g-r colors offers good
performance while the broad availability of these colors for a large number of galaxies ensures wide applicability on large galaxy
samples. The overall accuracy is ∼81% while the achieved completeness for each class is ∼81% for star-forming, ∼56% for AGN,
∼68% for LINER, ∼65% for composite, and ∼85% for passive galaxies. \
**Conclusions.** Our diagnostic provides a significant improvement over existing IR diagnostics by including all types of active,
as well as passive galaxies, and extending them to the local Universe. The inclusion of the optical colours improves their
performance in identifying low-luminosity AGN which are generally confused with star-forming galaxies, and helps to identify
cases of starbursts with extreme mid-IR colors which mimic obscured AGN galaxies, a well-known problem for most IR
diagnostics.

### Application of the model
This repository contains all the needed jupyter notebooks and the pre-trained random forest model for the implementation of algorithm presented in the paper mentioned above. We provide a file that has a test sample of galaxies *(sample_activity_classifier)* to test that your code works correctly. When you want the activity classifications for your own catalog of galaxies change this file with your catalog. The supported formats for your catalog is either 'fits' or 'csv'. The programming language used is Python3 and the sklearn verion is 1.1.2. 
- **Output of RF model**\
After the succesful application of the model on your catalog of galaxies, a column named 'Classification' contains the label of the activity class of each galaxy. Along with the classification labels we also provide the RF-predicted probabilities for each object to belong to each activity class. For convinience we code the classification output using numbers each one represanting a different activity class. Below we provide a legend with the meaning of the classification output. \
**Classification legend** \
0 - star forming \
1 - AGN \
2 - LINER \
3 - composite \
4 - passive 

Due to strong dependency on the specific versions of the Python packages, we recommend that the user creates a conda environment where all the necessary packages are installed based on the version of packages that this code has been tested to run successfully. Below we provide detailed instructions for the creation of the appropriate coda environment:
```
conda create --name GalActivityClassifier python==3.10.9
conda activate GalActivityClassifier
conda install scikit-learn==1.2.2
conda install astropy
conda install matplotlib==3.7.1
conda install pandas==1.4.4
conda install jupyter notebook
```
For the successful installation, these commands have to be executed in succession as they appear above.
