# PhysioNetECGLDA

MATLAB live script file that can download or use ECG records from PhysioNet, convert to readable MATLAB files, and then run a LDA. Provided code uses LDA on two statistical features of the ECG data, variance in R-R interval and MSE of detrended signals. Code written for BME3053C Final Project. 

Contributors: Jeffrey Chen, Oriana Molares, and Madison Otero

# Comments

The live script should be able to be run without any external changes. Attention should be noted that all files downloaded should be in the working directory to avoid any issues with pathing. If someone downlaods the RAW Atrial Fibrillation and Normal Sinus Rhythm Databases, the following steps needs to take place:

(1) Unzip the database and put it in the AFRAW and NSRAW folders respectively
(2) Ignore lines 28-38 

