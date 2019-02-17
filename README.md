# [HistopathologicCancerDetection](https://www.kaggle.com/c/histopathologic-cancer-detection)
In this challenge I tried 3 things:
## [Standard deep learning techniques](https://www.kaggle.com/guntherthepenguin/fastai-v1-densenet169)
I used the as per literature best architecture Densenet169 
with Dihedral image augmentations.
## [Optimizing Augmentations](https://www.kaggle.com/guntherthepenguin/fast-ai-optimizing-augmentations)
I used [hyperopt](https://github.com/hyperopt/hyperopt) to find the optimal image augmentations for this dataset
There is a weird bug happening when I reload the dataset to run the optimizations tha kills my kernel. I'm not sure yet how to debug it, for nwo I can only run a small subset on 32x32 sized images.
## [group equivariat Convolutional Neural Networks (gCNN)](https://www.kaggle.com/guntherthepenguin/fastai-v1-group-equivariate-cnns)
Based on the paper Veeling et al "Rotation Equivariant CNNs for Digital Pathology"
I tried to implement it (mainly made it useable with the fastai library since it was already implemented and available).
 <img src="https://raw.githubusercontent.com/basveeling/keras-gcnn/master/model.png" >
Microscopy pictures are usually rotation and flip invariant. So a CNN that uses the image and all rotations by 90° as well as flipped left right and upside down, should be better suited than standard CNN.
I largely used the code by [Adam Bielsky](https://github.com/adambielski) and [Taco Cohen's groupy](https://github.com/tscohen/GrouPy) but changed the batchnorm from 2D to 3D (this might be wrong but otherwise I couldnt get it to work). 
