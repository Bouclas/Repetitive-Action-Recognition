# Repetitive-Action-Recognition
This is the official repository housing the material that are exploited in the journal article "Exploiting the Nature of Repetitive Actions for their Effective and Efficient Recognition". We provide guidelines regarding the steps that were followed to generate the datasets that are used in this work, as well as any important documentation on the aspects of the proposed Human Activity Recognition (HAR) pipeline.

We provide the .csv train/test split files for the following datasets:

## _CountixHAR_

This dataset is a subset of the dataset _Countix_  [[1]](#1), consisting of only the samples that have a repetition count in the range between 2 to 10, and are sourced from public YouTube videos. The resulting dataset comprises 28 action classes and consists of 718 training and 262 test videos. The training set was based on the original _Countix_ train set, whereas the test set is based on the validation set of _Countix_. The purpose of this dataset is to evaluate the contribution of repetition-oriented sequence spliting as an input sequence pre-processing step for Human Activity Recognition (HAR) methods. The application of a repetition segment-centered input sequence splitting approach, such as RepNet  [[1]](#1), increases the training sample number to 3284 training sequences, if we consider each repetition segment as a distinct training sample. The increase in the dataset size indicating that we get on average 4.6 repetitions per sample.

## _CountixEffects_

This is another subset of _Countix_, whose generation is oriented on the evaluation (a) the impact of the number of repetitions and (b) the contribution of repetition-based segmentation in repetitive actions that impose gradual effects in the environment. _CountixEffects_ expands the repetition count range to actions that exhibit up to 20 repetitions, and consists of 5 action classes. Two of them (sawing wood, slicing onion) produce gradual effects. The rest 3 actions (headbanging, doing aerobics, running on treadmill) do not produce gradual effects on an object/scene/actor. The resulting CountixEffects dataset consists of 323 training and 100 test videos. Based on the ground-truth repetition counts provided in the original Countix dataset, CountixEffects exhibits an average of 9.67 repetitions per sample (regarding the training subset) and an augmented set of 3124 training samples, after the application of a repetition-centered sequence spliting approach.

##
## _Repetition segment detection_

To detect the repetition segments we relied on RepNet[[1]](#1), using the available [implementation](https://colab.research.google.com/github/google-research/google-research/blob/master/repnet/repnet_colab.ipynb). RepNet does not generate the start/ending frame indices of each repetition segment, however, we can indirectly produce them by setting the starting frame of a repetition segment at the frame index where the repetition count number increases.

##  _Repetition temporal encoding/summarization_
For this work we exploited the temporal summarization approach of Dynamic Images (DIs)[[2]](#2), to encode the temporal information within each repetition segment into a single RGB-like image. An interested reader that wishes to exploit the same direction can find the opensource code for this approach [here](https://colab.research.google.com/github/google-research/google-research/blob/master/repnet/repnet_colab.ipynb).


## References
<a id="1">[1]</a> 
Dwibedi D, Aytar Y, Tompson J, Sermanet P, Zisserman A. Counting out time: Class agnostic video repetition counting in the wild. IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) (2020)

<a id="2">[2]</a> 
Fernando B, Gavves E, Oramas JM, Ghodrati A, Tuytelaars T. Modeling video evolution for action recognition. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (2015), 5378–5387.
