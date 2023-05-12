# Facial-Recognition-for-transactions-or-OTP

Develop a system that balances the need for security with the user's convenience and privacy while ensuring the technology's accuracy and reliability.

# Problem Statement
Authenticating a customer in an online credit card transaction has been a challenge, as there is no foolproof method to do so. Authentication involves verifying the credit card owner during a purchase. In the physical world, this is accomplished through a signature, which is manually checked at the point of sale. However, without an effective way to authenticate customers in online transactions, several issues may arise, including fraudulent transactions, a lengthy transaction process, reduced customer confidence, and higher transaction costs.

# Existing Systems
A basic multi-factor authentication system typically involves requesting a user's username and password, which are something they know, as well as verifying their identity through a second factor, such as a text message sent to their phone, which is something they have. While this covers two factors of authentication, incorporating image recognition technology can add an additional layer of security to the login process without causing undue frustration or complexity for authorized users.

# Proposed Solution
The standard implementation techniques for face recognition are employed in this project using the Local Binary Pattern Histogram (LBPH) algorithm, which has been implemented using OpenCV Python.

LBP is a texture operator that assigns binary labels to the pixels of an image by thresholding the neighborhood of each pixel and then considering the result as a binary number.
When combined with histograms of oriented gradients (HOG) descriptor, it significantly improves the detection performance on some datasets.

The LBPH algorithm employs four parameters, including radius, neighbors, grid X, and grid Y.
Radius represents the radius around the central pixel, while neighbors represent the number of sample points used to build the circular local binary pattern.

Grid X and Grid Y represent the number of cells in the horizontal and vertical directions, respectively.

The higher the number of cells, the finer the grid, and the higher the dimensionality of the resulting feature vector.

To train the algorithm, a dataset with facial images of people to be recognized is needed, along with an ID for each image.

It is necessary to ensure that images of the same person have the same ID.
The LBPH computational steps involve creating an intermediate image that highlights facial characteristics.

A sliding window based on the radius and neighbors parameters is used to achieve this intermediate image.

![image](https://github.com/TanishaGiri/Facial-Recognition-for-transactions-or-OTP/assets/108277015/4a5f4dbb-64be-4a8c-9e1b-b60ea0401935)

Extracting the Histograms: Now, using the image generated in the last step, we can use the Grid X and Grid Y parameters to divide the image into multiple grids.

![image](https://github.com/TanishaGiri/Facial-Recognition-for-transactions-or-OTP/assets/108277015/908bb837-2ae4-479e-9554-2e1a20d62da5)


Approaches for Histogram Comparison: There are various approaches we can use to compare histograms and calculate the distance between two histograms. Some examples of these approaches include the euclidean distance, chi-square, absolute value, and more.

OpenCV Python: OpenCV Python is the Python API of OpenCV. It combines the best features of OpenCV C++ API and Python language. Python is a widely-used programming language, known for its simplicity and readability. Although Python is slower than other languages like C/C++, it can be easily extended with C/C++. This allows us to write computationally intensive code in C/C++ and create a Python wrapper for it, which we can use as a Python module. OpenCV-Python works in this way, as a Python wrapper around the original C++ implementation. Numpy is another library that supports OpenCV-Python and is highly optimized for numerical operations. It provides a MATLAB-style syntax and can convert all OpenCV array structures to and from Numpy arrays. Using Numpy with OpenCV-Python can increase the number of weapons in your arsenal. Additionally, other libraries like Matplotlib that support Numpy can be used with OpenCV-Python, making it an appropriate tool for fast prototyping of computer vision problems.

# Data flow Diagram
A data flow diagram (DFD) is a graphical representation of the flow of data through an information system. A DFD gives the preliminary overview of the system without going into great detail. Fig.4.2.1 represents the DFD of our proposed system. The flow of the system is as follows:

![image](https://github.com/TanishaGiri/Facial-Recognition-for-transactions-or-OTP/assets/108277015/c6a7d178-4a45-4d66-8b85-f733d9ba1d1d)

1.User enters amount and confirms.
2.Face verification is done by comparing input image with datasets.
3.If face is successfully verified, payment is successful.
4.If face verification fails, pin code is asked.
5.If pin code is verified, face image is stored for investigation if concerned is raised and      payment is successful.
6. If not verified, payment is declined.
# Experiments and Results
The prediction percentage and the accuracy of the bounding boxes in the results depends on the:

1.Batch size

2.Learning rate

3.Number of training iterations

Batch size: is the number of images that are trained per batch in one iteration of training.

Learning Rate: is the training parameter that controls the size of weight and bias changes during learning.

Number of Iterations: is the number of training iterations after which the network is optimally trained.
