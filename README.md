# Experiment-2 : Numerical Python

##NORMALIZATION PROBLEM : Create a random 5 x 5 ndarray

Objective : Normalize a 5 x 5 randomly generated ndarray and save the normalized array. Normalization is a common technique in data analysis in which the goal is to center and scale the data.

Expected Behavior: The program should generate a 5 x 5 random array, normalize it, and save the result to a file named X_normalized.npy. The resulting array will have values centered around 0 and scaled based on the standard deviation of the original array.

start of code

import numpy as np

#function to create a random 5x5 ndarray
X = np.random.rand(5,5)

#original array
print ("Original Array (X):\n", X)

#.mean and .std calls
mean_X = X.mean()
std_X = X.std()

#normalization expression
X_normalized = (X- mean_X) / std_X

#normalize the array
print("\nNormalized Array (X_normalized):\n", X_normalized)

#save noramlized ndarray as npy
np.save('X_normalized.npy', X_normalized)

Output Produced:

Original Array (X):
 [[0.37252386 0.9675348  0.85464024 0.19704774 0.91259269]
 [0.9931292  0.25666968 0.28256865 0.08095919 0.86448128]
 [0.91698484 0.86511433 0.7820863  0.88383854 0.83474994]
 [0.02398719 0.35866846 0.27378221 0.338432   0.89368058]
 [0.22581523 0.87043113 0.25909891 0.23742994 0.71529224]]

Normalized Array (X_normalized):
 [[-0.60598586  1.21563884  0.87001239 -1.14320561  1.04743368]
 [ 1.29399603 -0.96067317 -0.88138353 -1.49861045  0.9001407 ]
 [ 1.06088024  0.90207878  0.64788865  0.9594029   0.80911826]
 [-1.6730301  -0.64840413 -0.90828318 -0.710358    0.9895343 ]
 [-1.05513399  0.91835615 -0.95323608 -1.01957561  0.44339878]]

 
##DIVISIBLE BY 3 PROBLEM : Create a 10x10 ndarray

Objective : Create a 10 x 10 ndarray where each element is the square of the first 100 positive integers. After creating the array, the goal is to extract all elements that are  divisble by 3. 

Expected Behavior : The program should generate a 10 x 10 ndarray A where each element is the square of a positive integer from 1 to 100. Afterward, it will identify and extract all elements divisible by 3 and save these elements to a file names div_by_3.npy

start of code

import numpy as np

#creating a 10x10 ndarray with squares of first 100 positive integers
A = np.arange (1, 101)**2

#reshaping array into 10x10
A = A.reshape ((10,10))

#original 10x10 array
print ("10 x 10 Array (A):\n", A)

#finding elements divisible by 3
div_by_3 = A[A % 3 == 0]

#elements divisible by 3
print ("\nElements divisible by 3 (div_by_3):\n", div_by_3)

#saving elements into npy file
np.save('div_by_3.npy', div_by_3)

Output Produced: 
10 x 10 Array (A):
 [[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

Elements divisible by 3 (div_by_3):
 [   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
