# AI Fundaments 
Function 1: calculate_distance
This function computes the distance between two points (point1 and point2) using a specified distance metric (p):

For p=1 (Manhattan distance): It sums up the absolute differences between the coordinates of the two points. This is like measuring the distance by only moving along grid lines (up-down, left-right).
For p=2 (Euclidean distance): It calculates the straight-line distance between the two points by applying the Pythagorean theorem.
For p=∞ (Chebyshev distance): It takes the largest absolute difference between corresponding coordinates of the two points. This measures the maximum distance along any single axis.
The function raises an error if p is not 1, 2, or infinity, since other norms are not supported in this implementation.

Function 2: find_nearest_neighbors
This function finds the closest point (nearest neighbor) in array2 for each point in array1. The process is as follows:

Iterating through array1: For each point in array1, the function calculates the distance between that point and every point in array2. This is done using the calculate_distance function, which applies the selected distance metric.

Finding the closest point: After calculating all distances between the current point in array1 and every point in array2, the function identifies the point in array2 with the smallest distance (using NumPy’s argmin function to find the index of the minimum distance).

Storing the nearest neighbors: The function stores each pair of points (one from array1 and its nearest point from array2) in a list called nearest_neighbors.

Main Code Logic
Data Initialization: Two 2D arrays (array1 and array2) are created to represent sets of points. Each point is a pair of coordinates (e.g., [1, 2]).

Distance Metric Selection: A variable p is set to 2, meaning the program will use Euclidean distance in this case. You could change this to 1 for Manhattan distance or np.inf for Chebyshev distance.

Finding Nearest Neighbors: The find_nearest_neighbors function is called, which returns a list of nearest neighbor pairs (one from array1 and one from array2). The function finds the point in array2 that is closest to each point in array1.

Output: The result is printed, showing each point from array1 along with its nearest neighbor from array2.

Key Concepts:
Distance Calculation: Depending on the chosen norm (Manhattan, Euclidean, or Chebyshev), the way distance is measured changes. Each norm provides a different way to quantify "closeness" between points.
Nearest Neighbor Search: This is a basic version of finding the nearest neighbors, commonly used in machine learning and pattern recognition tasks. For each point in one set, it identifies the most similar (or closest) point in another set.
NumPy Operations: The code uses NumPy arrays and functions like sum, abs, sqrt, and argmin to handle the mathematical operations and efficiently compute distances between multiple points.
Practical Uses:
This concept of finding nearest neighbors is widely used in various fields, such as:

Classification (e.g., k-nearest neighbors algorithm): Given a new data point, we classify it based on the majority class of its closest points.
Recommendation Systems: Find similar users or products based on their features.
Clustering and Pattern Recognition: Grouping similar points or identifying patterns based on proximity.
