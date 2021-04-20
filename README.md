# PhysioNetECGLDA

MATLAB live script file that can download or use ECG records from PhysioNet, convert to readable MATLAB files, and then run a LDA. Provided code uses LDA on two statistical features of the ECG data, variance in R-R interval and MSE of detrended signals. Code written for BME3053C Final Project. 

Contributors: Jeffrey Chen, Oriana Molares, and Madison Otero

# Comments

The live script should be able to be run without any external changes. Attention should be noted that all files downloaded should be in the working directory to avoid any issues with pathing. 

If someone wants to download the RAW Atrial Fibrillation and Normal Sinus Rhythm Databases manually, the following steps needs to take place:

(1) Unzip the database and put it in the AFRAW and NSRAW folders respectively

(2) Ignore lines 28-38 

---

If you want to ignore the signal processing steps and just directly view the LDA associated with our data:

(1) Download the signal.dat file. Contains a table of all relevant variables after parsing through the ECG data.

(2) Run lines 238-316, ignore all previous lines of code.

# File Description 

- ConfusionMatrix.fig - Confusion Matrix/Chart of the LDA Classifier
- LDA Scatter.fig - G Scatter generated from LDA, includes boundary and misclassified points
- LDAclassifier.mat - Generated classification determinant from our data
- MainCode.mlx - The main code
- signal.dat - Table of variables found after iterating through the AF and NS files
