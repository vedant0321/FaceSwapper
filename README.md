# Face Swapper
This project is a Python-based application that allows you to perform facial swapping between two uploaded images. It uses OpenCV and dlib libraries for face detection, landmark extraction, and image transformation.

## Features
Detects facial landmarks using dlib's pre-trained shape predictor model.
Performs preprocessing and color correction to improve swapping quality.
Supports swapping faces in both directions (Image1 → Image2 and Image2 → Image1).
Displays the results interactively using matplotlib.

## Requirements
Ensure you have the following libraries installed:
- opencv-python
- dlib
- numpy
- matplotlib

To install the necessary libraries, run:
```Copy code
pip install opencv-python dlib numpy matplotlib
```

Additionally, download the pre-trained shape predictor model for facial landmarks:
```Copy code
wget -nc http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2 -O shape_predictor_68_face_landmarks.dat.bz2
bzip2 -dk shape_predictor_68_face_landmarks.dat.bz2
```
### How to Use
1. Setup:
    - Save the script as face_swap.py.
    - Place the downloaded shape_predictor_68_face_landmarks.dat file in the same directory as the script.
Execution:
Launch the script using Python:
```Copy code
python face_swap.py
```
- When prompted, upload two images via the interface.

## Output:

The application will process the uploaded images and display:
Image1 → Image2 face-swapped result.
Image2 → Image1 face-swapped result.

### Functions Overview
#### **Main Functions**
- improved_face_swap(image1, image2):

- Swaps the face from image2 onto image1 with color correction and mask blending.
    imshow(title, image, size):

- Displays an image using matplotlib.
  -Helper Functions
  -get_landmarks(image):

- Detects facial landmarks using dlib.
  transformation_from_points(points1, points2):

- Calculates the affine transformation matrix to align the faces.
  get_face_mask(image, landmarks):

- Generates a mask for facial regions.
  warp_im(image, matrix, dshape):

- Applies a warp transformation to the input image.
  improved_color_correction(im1, im2, landmarks1):

