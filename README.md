# HANDWRITING RECOGNITION AND REPLICATION
## Team Members

* Chandan Kumar
* Sannuta

## Mentors

* Adithya Jayan
* A Shrikant
* Alabhya
* Anirudh Athresh
* Naman

## Objectives

This project aims at recognizing a handwritten text and replicating the same in a different handwriting. The work was then devided into three parts:
* Segmentation of the text into individual characters.
* Design and train a machine learning model to recognize the handwritten characters.
* Design a system to recreate the text in a different handwriting.

Each of the objectives were specifically handled by both of the team members.

## Methodology

### Segmentation of the text to letters


<img src="https://user-images.githubusercontent.com/50314485/86254896-210a3780-bbd4-11ea-88b0-04eac9e9dba6.PNG"
	title="Cascade" width="350" height="250" />

<img src="https://user-images.githubusercontent.com/50314485/86254915-27001880-bbd4-11ea-9a8a-d00e7007a087.PNG"
	title="Cascade" width="350" height="250" />

The handwritten text is captured by a camera and made available for digital processing. The image obtained is then processed to obtain a 
low-noise binary thresholded image of the same text. The program ensured that all the characters are correctly segmented even if some lines are tilted.

<img src="https://user-images.githubusercontent.com/50314485/86254919-2798af00-bbd4-11ea-8457-1f914301257b.PNG"
	title="Cascade" width="350" height="250" />
	
<img src="https://user-images.githubusercontent.com/50314485/86254934-2b2c3600-bbd4-11ea-82bd-2847bdb3d5d1.PNG"
	title="Cascade" width="350" height="250" />

<img src="https://user-images.githubusercontent.com/50314485/86254935-2c5d6300-bbd4-11ea-984c-49e02995453d.PNG"
	title="Cascade" width="350" height="250" />

<img src="https://user-images.githubusercontent.com/50314485/86254939-2d8e9000-bbd4-11ea-896e-e739cc796d96.PNG"
	title="Cascade" width="350" height="250" />

The algorithm used for segmentation is called a 'Projection  Profile'. The whole image is converted to a column vector by taking its sum of values
along each row. The resultant array is then plotted and using suitable thresholds, each line in the text is segmented out to give an array of images containing one line each.
The same pocedure along the columns of each image in the array, gave a final array of characters. This array of letters can then be passed to the machine learning model for further training.

### Designing and training of the Machine Learning Model

The segmented characters now, have to be classified into their classes of alphabets and digits. Identifying this classification problem, a deep learning model was 
proposed for efficient training and to get accurate results. A Convolutional Neural Network (CNN) model was designed and used as the model.

<img src="https://user-images.githubusercontent.com/50314485/86254951-31221700-bbd4-11ea-97fd-00d6946615d8.PNG"
	title="Cascade" width="800" height="700" />

The dataset used for training the model is the [EMNIST](https://www.nist.gov/itl/products-and-services/emnist-dataset)
dataset of handwritten letters and digits. 

The CNN was trained on the dataset and the model was saved as a json file for further importing.

### Replacing each letter with a different handwriting

The set of letters for the second handwriting is read as a single image. The set is again segmented into a set of reference characters
using the same algorithm as above. The set is then labelled and stored. These can now be used to construct text in this handwriting.

The recognized labels of the handwritten letters are matched with the new letters and the letters are concatenated to from a new image
of the new handwriting.

<img src="https://user-images.githubusercontent.com/50314485/86254981-38e1bb80-bbd4-11ea-9147-b457c68129fb.PNG"
	title="Cascade" width="350" height="250" />


 
 ## Results
 ![Capture7](https://user-images.githubusercontent.com/50314485/86254967-34b59e00-bbd4-11ea-9e4f-75c20dff9909.PNG)
 
 * The segmentaion using projection profle was carried out with a fairly high accuracy.
 * The CNN model presented a validation accuracy of about 88%.
 * The image with new handwriting was generated with few feeble errors and a fair accuracy.
 
 ### Application
 
 The project results can be used to discretize and recognize various aspects of recognition of handwritten text and proves to be of great work to study
 for further improvements to the project like a mechanical arm or a setup for copying the output onto a paper. The study in this field still remains quite interesting and open.

### Acknowledgements

We acknowledge and specially thank for the support and technical guidance given by our seniors Alabhya, Anirudh Athresh and Naman. We also thank IEEE-NITK for supporting
this project.

### References

Projection Profile [here](https://pdfs.semanticscholar.org/a7e7/7f540e1dfa21287e37c66d9becacb87b38f6.pdf)
