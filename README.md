## Eye tracker

An eye-tracking application written in Python. This program uses a modern ensemble learning method [reference below] to locate and track pupils in real time webcam images of the user's eyes. This project allowed me to practice methods of image analysis, machine learning, recursive algorithms, and intermediate features of Python. 

For usage information please type: `python etrack.py --help`. 

Features:

* Training procedure for the algorithm using landmarked image data from the [BioID face database](http://www.bioid.com/index.php?q=downloads/software/bioid-face-database.html). This method uses the [OpenCV](http://opencv.org) library to identify eyes on faces and prepare these sub-images with previously-landmarked pupil information. These are then clustered into groups of similar eye images using randomly-generated, statically-useful features as described by Markuš *et al*. This training procedure identifies good parameters for pupil location inference for new data (i.e., the webcam stream from the user). Before training, users may specify the depth of the tree and number of trees in the ensemble.
* Saving and loading of pre-trained parameter sets in XML files.
* Saving trained tree parameter information in Graphviz format for easy visualization of regression trees in image files.
* Various other tuning parameter specifications.
* Includes pre-trained parameters for a large training set -- 100 trees of depth d=10, constructed from subsamples of 14060 images. (Note that this training set is still smaller than the original paper's and the tracker has fewer features, so the tracker is somewhat less robust).


To do:

* Finish statistical cross validation test, so that parameter choices can be assessed for statistical accuracy.
* Add mouse control using pupils.
* Implement boosting ensemble method.


Reference:

Markuš N, Frljak M, Pandžic IS, Ahlberg J, Forchheimer R. "Eye pupil localization with an ensemble of randomized trees," *Pattern Recognition* (2014). [doi: 10.1016/j.patcog.2013.08.008](http://dx.doi.org/10.1016/j.patcog.2013.08.008)



<p align="center">
  <img src="https://raw.githubusercontent.com/christopherjamesryan/Eye-Tracker/master/me.png"  width=300/>
</p>