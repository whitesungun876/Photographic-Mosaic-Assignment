This assignment guides you through creating a photographic mosaic—a fascinating concept where a larger background image is composed of smaller replacement images. Below is a detailed explanation of the tasks involved, along with instructions on how to implement the functionality.

Project Overview
A photographic mosaic replaces the pixels or small patches of a base image (background image) with tiny images (replacement images). The result is a large, visually coherent image made up of smaller images, which is both artistic and analytical.

For this assignment:
The background image is kangaroo.jpg.
The replacement images are from the CIFAR-10 dataset.

Example:
Imagine creating a mosaic of a kangaroo using thousands of CIFAR-10 images.

Tasks Overview
The assignment is broken into the following key components:
1. Making Tiles

Ex 1.1: Reading and Shaping the Background Image
Load the kangaroo.jpg image using the skimage library.
Steps involved:
Load the image into a variable (bg_image).
Convert the image to a float representation (color values between [0, 1]).
Rescale the image to 120% of its original size.
Adjust the shape of the image to fit a whole number of tiles (32x32 pixels). Discard excess rows and columns if necessary.

Ex 1.2: Tile Coordinates
Implement the tile_coordinates function to compute row and column ranges for a specific tile (i, j).
Use this function to extract individual tiles from the background image.
Create a low-resolution representation of the background image by replacing each tile with its mean color.

2. Loading Replacement Images
Ex 1.3: Load CIFAR-10 Dataset
Download the CIFAR-10 dataset from this link and extract it.
Use the provided load_cifar10 function to load the dataset.
Select images from data_batch_1 (or all batches) to use as replacement images.
(Optional) Use CIFAR-10 labels to filter images for specific categories.

3. Image Search
Ex 1.4: Average Color Vector
Create a function, average_color, to compute the mean RGB value for each replacement image.
Convert replacement images and tiles into 1D vectors (length 3 for RGB channels).
Use the provided image_distance_query function to compute distances between tile vectors and replacement image vectors.

Ex 1.9: Render Photographic Mosaic
Use the image_distance_query function to find the best replacement image for each tile.
Replace each tile of the background image with its closest replacement image.
Render and save the final mosaic image.

Dataset and File Requirements

Background Image:

File: kangaroo.jpg
Resized and adjusted to fit a whole number of 32x32 tiles.

Replacement Images:
Dataset: CIFAR-10
Location: cifar-10-batches-py/
Load using load_cifar10.

Output:
Final mosaic image rendered and saved.
Functions Overview
tile_coordinates(i, j, tile_size)
Returns the row and column indices for a tile at position (i, j).
low_resolution(bg_image, tile_size)
Creates a low-resolution version of the background image where each tile is replaced by its mean color.
average_color(image)
Computes the mean RGB values of an image, returning a vector of length 3.
image_distance_query(query_images, collection_images, to_vector_fn)
Finds the most similar images in the collection for each query image.
plot_best_matches(query_images, best_matches)
Visualizes query images with their best matches from the replacement pool.

Instructions
Setup
Install required libraries: numpy, matplotlib, skimage.
Download and extract the CIFAR-10 dataset to the working directory.
Place kangaroo.jpg in the working directory.
Steps to Run
Load the kangaroo.jpg image.
Process and divide the image into 32x32 tiles.
Load CIFAR-10 images and compute their average color vectors.
Replace each tile in the background image with the closest matching replacement image.
Save and visualize the final mosaic image.

Example Results
Background Image (kangaroo.jpg):
Low-Resolution Image: (Each tile replaced with its mean color.)
Final Photographic Mosaic: (Each tile replaced with the most similar CIFAR-10 image.)

Additional Notes
Ensure your code is optimized to handle large datasets.
Test the mosaic creation with different tile sizes for creative variations.
Dependencies
Python 3.x
Libraries:
numpy
matplotlib
skimage
CIFAR-10 dataset.
