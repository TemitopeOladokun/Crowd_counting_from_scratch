# Crowd_counting_from_scratch
This is a tutorial about crowd counting. In this repository, you can learn how to estimate number of pedestrians in crowd scenes through computer vision and deep leaning.
## How to do crowd counting?
&emsp;&emsp;Crowd counting has a long research history. About twenty years ago or even earlier, researchers have been interested in developing the method to count the number of pedestrians in the image automatically.  
&emsp;&emsp;There are mainly three categories of methods to count pedestrians in crowd. 1)Pedestrian detector. You can use traditional HOG-based detector or deeplearning-based detector like YOLOs or RCNNs. But effect of this category of methods are seriously affected by occlusion in crowd scenes. 2)Number regression. This category of methods just capture some features from original images and use machine-learning models to map the relation between features and numbers. An improved version via deep-learning directly map the relation between original image and its numbers. Before deep-learning, regression-based methods were SOTA and researchers are focus on finding more effective features to estimate more accuracy results. But when deep-learning get popular and achieve better results, regression-based methods get less attention because it is hard to capture effective hand-crafted features. 3)Density-map. This category of methods are the mainstream methods in crowd counting nowadays. Compared with detector-based methods and regression-based methods, density-map can not only give the information of pedestrian numbers, but also can reflect the distribution of pedestrians, which can make the models to fit original images with opposite density better.
## What is density-map?
&emsp;&emsp;Simply speaking, we use a gaussian kernel to simulate a head in corresponding position of the original image. After do this action for all heads in the image, we then perform normalization in matrix which is composed by all these gaussian kernels. The sample picture is as follows: 
![density-map sample](https://github.com/CommissarMa/Crowd_counting_from_scratch/blob/master/imgs/density-map-sample.png "density-map sample")