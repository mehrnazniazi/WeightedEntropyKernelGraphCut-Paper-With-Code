# WeightedEntropyKernelGraphCut-Paper-with-Code
Entropy-based Kernel Graph Cut with Weighted K-Means for Textural Image Region Segmentation

This repository presents an improved version of the unsupervised kernel graph cut algorithm, which aims to enhance the accuracy and stability of segmentation results by refining the clustering algorithm based on weighted image information.

In the entropy-based kernel graph cut algorithm, the image centers play a crucial role as they determine the data mapping to the new space through the RBF kernel. In the weighted entropy-based kernel graph cut algorithm, the centers for the background and foreground regions are determined using a weighted k-means algorithm. Subsequently, the RBF kernel is applied to these centers to implicitly map the data to a higher-dimensional space. The selection of suitable centers significantly impacts the segmentation quality. It is hypothesized that optimal centers are located in homogeneous areas with low frequency, away from the main edges of the image. To achieve this, the image edges are determined based on pixel values. Weak edges are eliminated using a Gaussian blur filter, and strong edges are extracted using a high-pass filter. The weighted image is then calculated by performing the Euclidean distance transformation based on the pixel distance to the nearest non-edge pixel. In the weighted image, pixels inside and outside the borders carry more weight, while pixels on the border have less weight. After obtaining the pixel weights, they are utilized to extract the centers using the weighted k-means algorithm. Each data point is assigned to the closest cluster center based on its membership degree. Subsequently, the cluster centers are recalculated for each cluster based on the membership degree and pixel weights. The data points influence the centers proportionally to their importance. Optimal center selection enhances the output of the kernel as closer feature vectors to the center receive higher coefficients.


If you find this work useful in your research, please consider citing the following paper:

M. Niazi, K. Rahbar, M. Sheikhan, and M. Khademi, "Textural Image Segmentation based on Entropy and VGG16 Deep Neural Network Kernel Graph Cut," Adv. Signal Process., May 2023.

You can access the paper at https://spre.stb.iau.ir/article_700768.html

