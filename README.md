# Facial-Recognition-for-transactions-or-OTP

Develop a system that balances the need for security with the user's convenience and privacy while ensuring the technology's accuracy and reliability.

# Problem Statement
Authenticating a customer in an online credit card transaction has been a challenge, as there is no foolproof method to do so. Authentication involves verifying the credit card owner during a purchase. In the physical world, this is accomplished through a signature, which is manually checked at the point of sale. However, without an effective way to authenticate customers in online transactions, several issues may arise, including fraudulent transactions, a lengthy transaction process, reduced customer confidence, and higher transaction costs.

# Existing Systems
A basic multi-factor authentication system typically involves requesting a user's username and password, which are something they know, as well as verifying their identity through a second factor, such as a text message sent to their phone, which is something they have. While this covers two factors of authentication, incorporating image recognition technology can add an additional layer of security to the login process without causing undue frustration or complexity for authorized users.

# Proposed Solution
In this project, we use standard implementation techniques, face recognition using Local Binary Pattern Histogram algorithm, which has been implemented using OpenCV Python.

LBPH: (Local Binary Pattern Histogram)
Local Binary Pattern (LBP) is a simple yet very efficient texture operator which labels the pixels of an image by thresholding the neighborhood of each pixel and considers the result as a binary number. LBP is combined with histograms of oriented gradients (HOG) descriptor, it improves the detection performance considerably on some datasets. Parameters: the LBPH uses 4 parameters:

Radius

Neighbors

Grid X

Grid Y

Radius: the radius is used to build the circular local binary pattern and represents the radius around the central pixel. It is usually set to 1.

Neighbors: the number of sample points to build the circular local binary pattern. Keep in mind: the more sample points you include, the higher the computational cost. It is usually set to 8.

Grid X: the number of cells in the horizontal direction. The more cells, the finer the grid, the higher the dimensionality of the resulting feature vector. It is usually set to 8.

Grid Y: the number of cells in the vertical direction. The more cells, the finer the grid, the higher the dimensionality of the resulting feature vector. It is usually set to 8.

Training the Algorithm: First, we need to train the algorithm. To do so, we need to use a dataset with the facial images of the people we want to recognize. We need to also set an ID (it may be a number or the name of the person) for each image, so the algorithm will use this information to recognize an input image and give you an output. Images of the same person must have the same ID. With the training set already constructed, let’s see the LBPH computational steps.

Applying the LBP operation: The first computational step of the LBPH is to create an intermediate image that describes the original image in a better way, by highlighting the facial characteristics. To do so, the algorithm uses a concept of a sliding window, based on the parameters radius and neighbors.
![image](https://github.com/TanishaGiri/Facial-Recognition-for-transactions-or-OTP/assets/108277015/4a5f4dbb-64be-4a8c-9e1b-b60ea0401935)

Extracting the Histograms: Now, using the image generated in the last step, we can use the Grid X and Grid Y parameters to divide the image into multiple grids.

![image](https://github.com/TanishaGiri/Facial-Recognition-for-transactions-or-OTP/assets/108277015/908bb837-2ae4-479e-9554-2e1a20d62da5)

We can use various approaches to compare the histograms (calculate the distance between two histograms), for example: euclidean distance, chi-square, absolute value, etc.

OpenCV Python
OpenCV-Python is the Python API of OpenCV. It combines the best qualities of OpenCV C++ API and Python language. Python is a general purpose programming language started by Guido van Rossum, which became very popular in short time mainly because of its simplicity and code readability. It enables the programmer to express his ideas in fewer lines of code without reducing any readability. Compared to other languages like C/C++, Python is slower. But another important feature of Python is that it can be easily extended with C/C++. This feature helps us to write computationally intensive codes in C/C++ and create a Python wrapper for it so that we can use these wrappers as Python modules. This gives us two advantages: first, our code is as fast as original C/C++ code (since it is the actual C++ code working in background) and second, it is very easy to code in Python. This is how OpenCV-Python works, it is a Python wrapper around original C++ implementation. And the support of Numpy makes the task more easier. Numpy is a highly optimized library for numerical operations. It gives a MATLAB-style syntax. All the OpenCV array structures are converted to-and-from Numpy arrays. So whatever operations you can do in Numpy, you can combine it with OpenCV, which increases number of weapons in your arsenal. Besides that, several other libraries like Matplotlib which supports Numpy can be used with this. So OpenCV-Python is an appropriate tool for fast prototyping of computer vision problems.

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
