# Microscopy_Seg_CVProjectFall23
 
\section*{Dataset}
The Electron Microscopy Dataset offers a comprehensive view of a 5x5x5 um section from the CA1 hippocampus region of the brain, translating to a 1065x2048x1536 volume. With a voxel resolution of approximately 5x5x5 nm, the dataset has been graciously provided as structured TIF files for training and validation. Both training and test dataset are one TIF file each consisting of 165 2D slices each. In addition the dataset also has binary ground truth images that shows proper segmentation and act as output value for training and testing. Notably, our focus was drawn to this dataset due to its meticulous annotations of mitochondria in two sub-volumes, making it an instrumental tool in our line of research.

\section*{Objectives}

\textbf{Primary Objective:} Develop a segmentation model capable of effectively working with the dataset, striving to achieve the optimal Intersection over Union (IoU) score.\\
\textbf{Secondary Objective:} Progress to semantic segmentation with the aim to track specific cell bodies throughout the dataset, adding bounding boxes for object detection.

\section{Methodology \& Implementation}

\subsection{Basic Histogram Segmentation} We kick-started our project with a basic histogram segmentation leveraging Otsu's threshold. This approach set the foundational framework upon which subsequent methodologies were implemented. The image was converted to grayscale, threshold value was calculated and a segmented binary image obtained. We added post-processing techniques such as morphological operations, hole filling, skeletonize, etc.
\subsubsection{Description} Otsu’s method is a popular technique employed for image thresholding. It separates an image into two classes, foreground, and background, based on the grayscale intensity values of its pixels. Furthermore, Otsu’s method uses the grayscale histogram of an image to detect an optimal threshold value that separates two regions with maximum inter-class variance.
\subsubsection{Results} We started with a simple pixel level accuracy measure and an IOU score. The table below shows the results from using the thresholding mentod before and before each round of morphological post processing. The image shows the predicted masks before and after the post-processing compared with the ground truth
