 Partial mimicry
---
 Code and dataset used in: reference...


## Description of the data and file structure

The code for processing data, training the neural network, and producing the results shown in this paper is stored in Mathematica notebooks. These notebooks, ending with ".nb" are stored in the main directory. The data files are stored in the "Data" directory, where large files are compressed.

Mathematica notebooks can be run using the Wolfram Player (free, but you can't edit code) (verify, add link) or Wolfram Mathematica (paid, but can freely edit code) (add link). The code used in these notebooks doesn't have any external code dependencies. Note that the selection and cropping of images for training was done with software not included in this repository, although a link to a particular software used to select and crop images (Labelme) is given in the paper.


## Sharing/Access information

  * Spider occurrence records: GBIF.org (05 January 2022) GBIF Occurrence Download  https://doi.org/10.15468/dl.af78fw
  * NonSpider occurence records: GBIF.org (28 October 2022) GBIF Occurrence Download  https://doi.org/10.15468/dl.s5nxft
  * INaturalist search with query: "has[]=photos&quality_grade=research&identifications=any&geoprivacy=open&taxon_geoprivacy=open&taxon_id=47120&without_taxon_id=85493&rank=species&verifiable=true&d1=2022.06.27&d2=2022.07.03&spam=false"

Attributions for the images used for training the neural network can be found in the tab delimited file *TrainingImageAttributions.tsv*. The first line is the header, with the following columns names:
  * ImagesID: The ID used to name a set of images from an observation.
  * rightsHolder: The username of the rights holder, as specified in the INaturalist observation.
  * license: The license associated with the images.
  * references: The url to the INaturalist observation containing the images associated to the attribution data.

## Code/Software

The data processing, neural network training, and testing and investigating the neural network are in separate mathematica notebook in the directory "Code". Each notebook contains instructions and explanations on how to run the code and what the code does. After downloading the raw images, they were cropped to remove background by creating bounding boxes using labelme (https://github.com/wkentaro/labelme). The resulting files were processed in DataProcessing.nb to programatically extract the image contained within the bounding box.

* DataProcessing.nb

  This notebook contains the code used to process the raw data containing observation data from INaturalist to download the images used for training the neural network.

* NeuralNetTraining.nb

  This notebook contains the code used to train the neural network to classify images into the categories "Spider" or "NonSpider",  as well as generating images using Google's DeepDream algorithm which maximize the classification of an image either to "Spider" or "NonSpider".

* PM-analysis