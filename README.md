

**Clustering Resting-State Functional MRI**
----------------------------------------

1. Overview
-----------
- [Scikit-learn](http://scikit-learn.org/stable/), a standard machine learning libary, provides handy tools for fMRI analysis. [Nilearn](http://nilearn.github.io/index.html), a machine learning library seeks to simplify the use of Scikit-learn for neuroimaging. It provides an easier way to load, preprocess, mask, and visualize neuroimaging data.

- Ward's method ([Ward's method in Wikipedia](https://en.wikipedia.org/wiki/Ward%27s_method)) was used to cluster  functional MRI images. . Three different number of clusters (n = 50, n = 500, n = 5000) were compared.

- A public dataset from [NYU](http://www.nitrc.org/frs/?group_id=274) was used for this analysis analysis. The dataset includes 3 sessions of 26 subjects (male: female = 11: 15). Three sets of images are available for each session. For each subjects, 3 resting-state fMRI scans with 197 echo-planar-imaging (EPI) 3D volumes (matrix = 60*64*29, spatial resolution = 3 mm isotropic) 


2. Results
-----------
An example subject with subject ID = 10 was selected for analysis . 

***3.1 Original fMRI Image***
The original fMRI image include 48320 voxels in a 3D volume.

![alt tag](https://cloud.githubusercontent.com/assets/17630430/14062321/a89256f8-f368-11e5-9299-054195daedd8.png "Original fMRI Image")

***3.2 Ward Clustering (50 Clusters)***
Ward clustering with cluster number = 50, which is about 1000x compression from the original image.

![alt tag](https://cloud.githubusercontent.com/assets/17630430/14062406/9a1364de-f36b-11e5-966a-e71f9ff9cfb3.png "Ward Clusters 50")

***3.3 Ward Clustering (500 Clusters)***
Ward clustering with cluster number = 500, which is about 100x compression from the original image.

![alt tag](https://cloud.githubusercontent.com/assets/17630430/14062407/ac3afb36-f36b-11e5-88ab-4ad91fb697f9.png "Ward Clusters 500")

***3.4 Ward Clustering (5000 Clusters)***
Ward clustering with cluster number = 5000，which is about 10x compression from the original image.

![alt tag](https://cloud.githubusercontent.com/assets/17630430/14062410/bcfc636a-f36b-11e5-9251-9378e6817386.png "Ward Clusters 5000")

From the above images, we can easily see appreciate the impact of cluster number on clustering. Compared with the original fMRI image (48320 voxels), the clustered image with cluster_number = 500 (i.e. ~100x compression) and cluster_number = 5000 (10x compression) retain most of their features. However, the clustered image with cluster_number = 50 lost substantial information. 

3. References
-----------
[1] http://scikit-learn.org/stable/
[2] http://nilearn.github.io/
[3] http://nilearn.github.io/auto_examples/index.html
[4] http://www.nitrc.org/frs/?group_id=274