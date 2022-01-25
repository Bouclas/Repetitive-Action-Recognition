# Repetitive-Action-Recognition
This is the official repository housing the material that are exploited in the journal article "Exploiting the Nature of Repetitive Actions fortheir Effective and Efficient Recognition". We provide guidelines regarding the steps that were followed to generate the datasets that are used in this work, as well as any important documentation on the aspects of the proposed Human Activity Recognition (HAR) pipeline.

We provide the .csv train/test split files for the following datasets:

## CountixHAR

This dataset is a subset of _Countix_  [[1]](#1), consisting of only the samples that have a repetition count in the range between 2 to 10, and are sourced from public YouTube videos. The resulting dataset comprises 28 action classes and consists of 718 training and 262 test videos. The training set was based on the original _Countix_ train set, whereas the test set is based on the validation set of _Countix_. The purpose of this dataset is to evaluate the contribution of repetition-oriented sequence spliting as an input sequence pre-processing step for Human Activity Recognition (HAR) methods.

## CountixEffects



## References
<a id="1">[1]</a> 
Dwibedi D, Aytar Y, Tompson J, Sermanet P, Zisserman A. Counting out time: Class agnostic video repetition counting in the wild. IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR) (2020)
