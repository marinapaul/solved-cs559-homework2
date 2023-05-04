Download Link: https://assignmentchef.com/product/solved-cs559-homework2
<br>
<strong>Problem 1: </strong>[Perceptron Algorithm]

In this problem, we learn the linear discriminant function for boolean OR function. Suppose we have two dimensional <em>x </em>= (<em>x</em><sub>1</sub><em>,x</em><sub>2</sub>), <em>x</em><sub>1 </sub>and <em>x</em><sub>2 </sub>can be either 0 (false) or 1 (true). The boolean OR function is defined as: <em>f</em>(<em>x</em><sub>1</sub><em>,x</em><sub>2</sub>) = <em>x</em><sub>1 </sub><strong>OR </strong><em>x</em><sub>2</sub>. Specifically, <em>f</em>(0<em>,</em>0) = <strong>false</strong>, <em>f</em>(1<em>,</em>0) = <strong>true</strong>, <em>f</em>(0<em>,</em>1) = <strong>true</strong>, and <em>f</em>(1<em>,</em>1) = <strong>true </strong>where <strong>true </strong>can be treated as <em>positive class </em>and <strong>false </strong>can be treated as <em>negative class</em>. You can think of this function as having 4 points on the 2D plane (<em>x</em><sub>1 </sub>being the horizontal axis and <em>x</em><sub>2 </sub>being the vertical axis): <em>P</em><sub>1 </sub>= (0<em>,</em>1)<em>,P</em><sub>2 </sub>= (1<em>,</em>1)<em>,P</em><sub>3 </sub>= (1<em>,</em>0)<em>,P</em><sub>4 </sub>= (0<em>,</em>0), <em>P</em><sub>1</sub><em>,P</em><sub>2</sub><em>,P</em><sub>3 </sub>in <em>positive class </em>and <em>P</em><sub>4 </sub>in <em>negative class</em>.

<ul>

 <li>[5pt] For boolean OR function, is the negative class and positive class linearly separable?</li>

 <li>[25pt] Is it possible to apply the <strong>perceptron algorithm </strong>to obtain the linear decision boundary that correctly classify both the positive and negative classes? If so, write down the updation steps and the obtained linear decision boundary. (You may assume the initial decision boundary is, and sweep the 4 points in clockwise order, i.e., (<em>P</em><sub>1</sub><em>,P</em><sub>2</sub><em>,P</em><sub>3</sub><em>,P</em><sub>4</sub><em>,P</em><sub>1</sub><em>,P</em><sub>2</sub><em>,…</em>), note that you <strong>can not </strong>write down the arbitrary linear boundary without updation steps. )</li>

</ul>

<strong>Problem 2 </strong>[Principal Component Analysis, Dimension Reduction, Eigenface]

Face modelling serves as one of the most fundamental problems in modern artificial intelligence and computer vision, and can be useful in various applications like face recognition, identification etc. However, face images are usually of high-dimensional (e.g., a small 100×100 gray-scaled face image has dimension 100 × 100 = 10<em>,</em>000), therefore, find a suitable representation is utterly important. In this problem, we apply the linear model, principal component analysis (PCA), on face images to reduce the dimension and obtain eigenface representations.

<strong>Dataset</strong>: we use the dataset<sup>† </sup>which contains 177 face images. Each image contains 256 × 256 pixels and is gray-scaled (i.e., the value for each pixel is stored as unsigned integer between [0<em>,</em>255], typically, 0 is taken to be black and 255 is taken to be white). You need to split the dataset to be train/test set, e.g., you could use the first 157 images for training, and the rest 20 faces for testing.

<ul>

 <li>[30pt] Write the PCA codes to compute <em>K </em>= 30 eigenfaces and visualize the top 10 eigenfaces.</li>

 <li>[20pt] Use the learned <em>K </em>eigenfaces from (1) to reconstruct testing images, and record the reconstruction error. The reconstruction error can be defined as , where <em>Y</em>ˆ is the reconstructed face using the learned eigenfaces, <em>Y </em>is the testing faces and <em>N </em>is the total number of testing data. Please show 5 testing images and their reconstructed ones.</li>

 <li>[20pt] Try different values of <em>K</em>, e.g., try <em>K </em>= 10<em>,</em>30<em>,</em>50<em>,</em>100<em>,</em>150<em>…</em>, and draw the curve to indicate the corresponding testing reconstruction errors. The x-axis of the curve can be different <em>K </em>values, and the y-axis can be testing reconstruction error defined in (2).</li>

</ul>

†

The dataset is coming from S.C. Zhu’s previous Stats 231: Pattern Recognition and Machine Learning in UCLA.

1

Some useful hints:

<ul>

 <li>To construct the data matrix for PCA, you can reshape each image to a long vector. For example, the original 2D image of size [<em>h,w</em>] becomes 1D vector of size <em>h</em>×<em>w</em>. Each row of the data matrix represents one face image and data matrix has size [<em>N<sub>train</sub>,D</em>] where <em>N<sub>train </sub></em>is the number of training samples and <em>D </em>= <em>h </em>∗ <em>w </em>is the dimension of the reshaped image.</li>

 <li>To compute the PCA, you need to subtract the mean image from each training image. To get the mean image, just sum up all the training images and divide it by <em>N<sub>train</sub></em>.</li>

 <li>You could use <strong>from PIL import Image</strong>, <strong>open </strong>to read the images, and use <strong>matplotlib.pyplot </strong>to show the images. Feel free to use other functions to read and process the images as well.</li>

 <li>For PCA, you could use <em>linalg </em>from <em>numpy </em>for eigendecomposition. Other eigenvalue decomposition/SVD functions can also be used. However, you <strong>can not </strong>directly call the <strong>pca </strong>functions in any languages for this problem.</li>

</ul>

2