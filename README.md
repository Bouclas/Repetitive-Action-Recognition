# Repetitive-Action-Recognition
This is the official repository housing the material that are exploited in the journal article "Exploiting the Nature of Repetitive Actions for their Effective and Efficient Recognition". We provide guidelines regarding the steps that were followed to generate the datasets that are used in this work, as well as any important documentation on the aspects of the proposed Human Activity Recognition (HAR) pipeline.

We provide the .csv train/test split files for the following datasets:

## _CountixHAR_

This dataset is a subset of the dataset _Countix_  [[1]](#1), consisting of only the samples that have a repetition count in the range between 2 to 10, and are sourced from public YouTube videos. The purpose of this dataset is to evaluate the contribution of repetition-oriented sequence spliting as an input sequence pre-processing step for Human Activity Recognition (HAR) methods. The dataset specifications are:

- 28 action classes, repetition count range 2-10, on average 4.6 repetitions per sample
- 718 training samples, 262 test samples
- After repetition-centered segmentation: 3284 training samples, if we consider each repetition as a distinct sample


The original _Countix_ dataset can be found [here](https://sites.google.com/view/repnet).

## _CountixEffects_

This is another subset of _Countix_, whose generation is oriented on the evaluation (a) the impact of the number of repetitions and (b) the contribution of repetition-based segmentation in repetitive actions that impose gradual effects in the environment. The dataset specifications are:

- 5 actions, where 2 produce an effect on object/scene/actor, and, 3 do not.
- 323 training and 100 test videos
- After repetition-centered segmentation: 3124 training samples, if we consider each repetition as a distinct sample


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
