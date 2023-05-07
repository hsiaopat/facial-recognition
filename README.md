# facial-recognition Grace Bezold and Patrick Hsiao
Project for Neural Networks - CSE 40868

//Part 4//

1. The test dataset we obtained for this part was by collecting face images from ourselves and our friends from images in our camera rolls. Therefore, the images were more varied in facial expression, environment and lighting than the training and validation subsets which were more controlled facial expression, environment and lighting. Also, this meant that the other data was more similar to both the Patrick and Grace datasets in the test, because in the training and validation subsets, the other data is from the FRGC dataset which uses a higher quality camera, more controlled pose and distinct lighting. The FRGC dataset also includes images of older people, whereas the new data collected was limited to ND undergraduates. 

For example, here is some data from the training and validation:

[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/pattySerious.jpeg" title="patty" height="300">](https://github.com/hsiaopat)&nbsp;
[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/graceSerious.jpeg" title="grace" height="300">](https://github.com/hsiaopat)&nbsp;
[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/boyer.png" title="boyer" height="300">](https://github.com/hsiaopat)&nbsp;

Here is data from the test:

[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/pattypic.jpeg" title="patty" height="300">](https://github.com/hsiaopat)&nbsp;
[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/gracePic.jpeg" title="grace" height="300">](https://github.com/hsiaopat)&nbsp;
[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/mia.jpeg" title="mia" height="300">](https://github.com/hsiaopat)&nbsp;



2. The classification accuracy achieved on the test set was 59.38% which was previously 91.67% when the test was from the same subset of data as training and validation

3. One reason why our solution performed worse was definitely due to the other data being more similar to our other classes than in the first round of datasets. Before, the network could have been learning to differentiate between classes based on features that are not facial, such as quality of image and lighting. It seems like a lot of the FRGC images have a specific yellow tinge. Improvements we would make fall into two categories, architecture improvements and dataset improvements. With data, we would increase the size of the training dataset, and make it more diverse in terms of pose, image quality, lighting condition and facial expression. Some of this diversity could also be achieved by data augmentation. With more varied training data, the model will generalize better on test data it has not seen. Also, we could potentially use a pre-trained model and then fine tune the model on our dataset to account for the small amount of data. In terms of architecture, there is a function in RetinaFace which will realign the face after cropping. This could lower error rates because with the introduction of different poses, sometimes the faces were not upright, which was something the model did not see in training. 

[<img src="https://github.com/hsiaopat/facial-recognition/blob/main/imgForREADME/cropPic.png" title="jolie" height="400">](https://github.com/hsiaopat)&nbsp;

Also, we did add dropout to try and increase generalizability of the model but did not see a huge improvement. 

4. Detailed description of team work
Grace:
- Collected ~100 images of Grace, >100 images of 'other' from camera roll for new test dataset
- In terms of architecture tweaks, tested effect of adding dropout before FC1, tested effects of changing network size (dropped to only 4 convolutional layers, reduced number of features)
- Ran new test dataset experiment
- Worked with Patrick on the writeup
- Worked with Patrick on the presentation (specifically the architecture and obstacles sections) and presented

Patrick:
- Collected ~100 images of Patrick, ~50 images of 'other' from camera roll for new test dataset
- In terms of architecture tweaks, tested effect of using different activation functions like LeakyReLU, tested using Transfer Learning instead.
- Ran new test dataset experiment
- Combined different tweaks from both Grace and my experiments
- Worked with Grace on the writeup
- Worked with Grace on the presentation (specifically the data and use case sections) and presented

5. Presentation
// add link to recording

//Part 3//
Separately, we each took 300 photos of ourselves. However, our images are too similar because our network has 100% accuracy on the test data. For our next solution we will be updating our datasets to include more different photos. 

We met several times to write the facial cropping cell, the dataset/ dataloader cell and to train/ evaluate and troubleshoot the CNN. All code was done together while meeting. 
