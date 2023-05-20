# Image Search Using CNN and SIFT

## Introduction ##
In the era of digital imagery, the ability to efficiently search and match specific instances within a vast database of images is a critical task with numerous applications. Instance search, also known as object retrieval or object recognition, involves identifying and retrieving images containing a specific object or instance of interest. This capability finds utility in various domains, including image retrieval, visual search engines, and augmented reality applications.

This project aims to implement an instance search system utilizing two popular and powerful techniques: Convolutional Neural Networks (CNN) and Scale-Invariant Feature Transform (SIFT). By leveraging the strengths of these methods, the project seeks to match 20 query images against a database comprising 5000 images, ultimately providing accurate and efficient retrieval of relevant of the 10 best instances.

## CNN ##


I initially employed a Convolutional Neural Network (CNN), specifically the ResNet18 architecture, renowned for its ability to extract features from images. This pre-trained network, trained on the ImageNet dataset and capable of classifying 1000 object categories, served as the backbone for my implementation.

To begin, I cropped the query images based on the provided bounding box coordinates, saving them in a dedicated folder named "cropped_query". Next, I utilized the 'avgpool' layer to extract feature vectors from both the gallery images and the cropped query images. These feature vectors are essentially dense representations of the input images, consisting of a list of numerical values.

Subsequently, I manually tested the similarity between feature vectors using both Cosine similarity and Euclidean distance measures. After evaluating the results, I found that Cosine similarity yielded superior outcomes. Consequently, I employed Cosine similarity to match the corresponding feature vectors of all 20 query images with the 5000 gallery images.

Here are the matching results obtained from the instance search implementation using CNN (ResNet18) and Cosine similarity:

Query 2714: Matches with images 3268, 2954, 4952, 4256, 2126, 4622, 1959, 3062, 4234, 2001. <br />
Query 316: Matches with images 3399, 4267, 395, 2684, 3113, 2741, 2131, 184, 4360, 418. <br />
Query 27: Matches with images 3035, 810, 2916, 4125, 4216, 2458, 1965, 3575, 3514, 2064. <br />
Query 3557: Matches with images 4325, 2598, 1913, 3166, 3825, 4791, 1994, 975, 4978, 1612. <br />
Query 2040: Matches with images 2666, 1750, 294, 1598, 1270, 4991, 2711, 4303, 1760, 128. <br />
Query 1258: Matches with images 2403, 26, 3065, 3689, 1159, 4805, 2009, 4937, 2368, 3290. <br />
Query 3502: Matches with images 3493, 2100, 2939, 3087, 1377, 3062, 2397, 4504, 2859, 155. <br />
Query 3906: Matches with images 1423, 3035, 82, 3856, 3457, 3019, 1525, 1646, 1775, 1169. <br />
Query 3833: Matches with images 1038, 3048, 1646, 985, 1169, 1482, 2488, 2468, 1411, 3521. <br />
Query 4929: Matches with images 672, 3259, 1482, 2711, 1750, 2715, 3179, 1880, 2468, 3612. <br />
Query 2176: Matches with images 1107, 1157, 4267, 139, 1000, 4429, 3431, 2673, 4185, 1739. <br />
Query 2032: Matches with images 869, 4776, 3797, 1566, 3252, 4616, 2352, 1759, 26, 4484. <br />
Query 776: Matches with images 1566, 4995, 1760, 2621, 296, 3252, 709, 4552, 795, 3120. <br />
Query 35: Matches with images 86, 3090, 4523, 429, 4249, 4978, 1206, 4022, 3543, 4827. <br />
Query 4354: Matches with images 2, 19, 2673, 1485, 3529, 2666, 3850, 613, 1690, 4090. <br />
Query 1656: Matches with images 839, 2490, 1227, 934, 2003, 3875, 1754, 991, 3162, 1270. <br />
Query 1709: Matches with images 2857, 2296, 3385, 2753, 1612, 1236, 1076, 1544, 427, 309. <br />
Query 4716: Matches with images 3588, 2946, 4775, 4207, 2589, 2433, 1487, 2960, 2786, 4498. <br />
Query 2461: Matches with images 4386, 1044, 3362, 2870, 3981, 3791, 4686, 4011, 2589, 511. <br />
Query 4445: Matches with images 4554, 3547, 839, 1544, 3299, 2490, 4289, 1076, 1112, 1929. <br />

For Query 4354.png

<img src="/data/Source_Results/4354.jpg" alt="Query" width="auto" height="auto">

The 10 Best Matches are:

<img src="/data/Source_Results/4354_10Best.png" alt="10_Best" width="auto" height="auto">

