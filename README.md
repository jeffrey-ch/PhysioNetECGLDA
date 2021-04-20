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

# Step by Step Instructions

- Lines 1-16: Downloads the WFDB Toolbox for PhysioNet Database Analysis 

![image](https://user-images.githubusercontent.com/70290263/115423947-3c2e4e00-a1cc-11eb-8c30-f03353217bbf.png)

- Lines 17-27: Makes an empty AF and NS folder in the directory, adds them to the path, and saves the directory.

![image](https://user-images.githubusercontent.com/70290263/115424228-7ef02600-a1cc-11eb-821f-edff8d5cc574.png)

- Lines 28-43: Downloads the database zip files from PhysioNet and then saves the files to the empty folders made before. Makes an empty folder to contain the eventual read files.

![image](https://user-images.githubusercontent.com/70290263/115424448-b78fff80-a1cc-11eb-9a4c-cf72932ed8e7.png)

- Lines 44-73: Converts the first 3 records from the AFRAW folder into .mat files, then reads the file to obtain signal, time, frequency, and labels data. Data is then exported into the empty folder for read files. 

- Lines 74-97: Repeats the same steps with the NSRAW folder

![image](https://user-images.githubusercontent.com/70290263/115424857-13f31f00-a1cd-11eb-9ee8-11a22e1be19a.png)

- Lines 98-114: Example output of a detrended signal 

![image](https://user-images.githubusercontent.com/70290263/115425102-4dc42580-a1cd-11eb-8a98-72cbf7b2d008.png)

- Lines 115-163: An example of the data gathering process using the first 1000 signal data of the first file. Detrend the signals, square the signals to emphasize the peaks, find the peaks using the findpeaks() function, then take the variance of the difference of each peak. MSE is calculated from the detrended data. 

![image](https://user-images.githubusercontent.com/70290263/115425397-97147500-a1cd-11eb-9be4-cf7865b9d2b5.png)

- Lines 164-187: Obtain the list of all read files 

![image](https://user-images.githubusercontent.com/70290263/115425714-d9d64d00-a1cd-11eb-85ca-2bb9f17512cf.png)

- Lines 188-229: Iterates through the 6 files, 400 sets of 1000 signal data points from each file, resulting in 2400 total data for R-R Interval Variance, MSE, and signal type (AF or NS).

- Lines 230-237: Converts the three different variables into a matrix then to a table to be saved. 

![image](https://user-images.githubusercontent.com/70290263/115426102-36396c80-a1ce-11eb-8469-7f06aabd4572.png)

- Lines 238-257: Obtains vector data from the signal.dat table and remove all the NaN values

- Lines 258-354: Application and visualizations of LDA
  - See ConfusionMatrix.fig and LDA Scatter.fig

- Lines 305-316: Example of using the LDA classifier through using some given variables. 

