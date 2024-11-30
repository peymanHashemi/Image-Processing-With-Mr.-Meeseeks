# Image-Processing-With-Mr.-Meeseeks
## Description
In this project, we assist Rick in addressing a peculiar problem with blue humanoid creatures known as Mr. Meeseeks. The goal is to apply several computer vision techniques using OpenCV to identify, separate, and process images of these creatures effectively. The project focuses on tasks such as color space conversion, object detection, color image reconstruction, edge detection, and histogram equalization.

## Project Objectives
### 1. Gray-scale Conversion:

Load a color image of Mr. Meeseeks (MeeseeksHQ).
Convert it to grayscale using OpenCV’s cvtColor function.
Display both the original color image and the grayscale version in the report.

### 2. Object Detection and Isolation:

Load a color image of Mr. Meeseeks.
Develop a program to isolate Mr. Meeseeks from the rest of the environment based on their unique color.
Output an image where only Mr. Meeseeks is highlighted (e.g., by blacking out the rest of the image).

### 3. Color Image Reconstruction:

Use historical techniques inspired by early Russian engineers, where separate grayscale images for each color channel (Red, Green, Blue) were stacked to create a color image.
Implement a function to split an image into its three grayscale channels.
Write a second function to combine the three channels into a color image, ensuring correct channel order and alignment.
Address any blurriness caused by misalignment by developing an optimization function that minimizes alignment errors. Analyze the time complexity of your solution and suggest methods to improve efficiency.

### 4. Edge Detection:

Load an image (Edge) and apply the Canny edge detection algorithm using OpenCV.
Propose and implement a solution to eliminate unnecessary edges, such as those affecting wheat in the image. Provide a detailed explanation and analysis in the report.

### 5. Histogram Equalization on Color Images:

Explore methods for applying histogram equalization to color images.
Select a color image and implement your proposed solution.
Analyze the impact of this technique on the image and provide a detailed report with your findings.

# implementation
  * [Q1](#Question-1) [Gray-scale Conversion]
  * [Q2](#Question-2) [Object Detection and Isolation]
  * [Q3](#Question-3) [Color Image Reconstruction]
  * [Q4](#Question-4) [Edge Detection]
  * [Q5](#Question-5) [Histogram Equalization on Color Images]



# Question 1

Loaded a color image of Mr. Meeseeks HQ and converted it to grayscale using OpenCV’s cvtColor function.


<img style="width:200px" src="https://github.com/user-attachments/assets/a3d5c573-9290-4a14-a52c-f01b6a89bfbf" >
<img style="width:200px" src="https://github.com/user-attachments/assets/4ec827b6-647a-46b5-af16-f84c395f1f39" >

# Question 2

Created a mask based on color thresholds to isolate Mr. Meeseeks from the background and used a bitwise operation to highlight the detected regions.

<img style="width:500px" src="https://github.com/user-attachments/assets/e111cff7-b2fc-4afd-85e3-654bfe3c3818" > <br>
<img style="width:500px" src="https://github.com/user-attachments/assets/a8b06ea4-7960-4971-8e85-4b1bf8a25159" >

# Question 3

The code follows a historical method for colorization:

### Image Splitting:
A grayscale image was divided into three equal vertical sections, each representing a different color channel.
The split images were assigned as Red, Green, and Blue channels.
###  Channel Stacking:
The sections were stacked using np.dstack to form a composite color image.
Misalignment issues were addressed by aligning channels using a rolling mechanism, adjusting horizontally and vertically until similarity was maximized based on correlation coefficients.
This method simulates early color photography techniques where grayscale images were manually aligned and combined to form color images.

<img style="width:200px" src="https://github.com/user-attachments/assets/5027db50-981d-45c9-8cda-0d1693b7bd1a" > <br>
<img style="width:300px" src="https://github.com/user-attachments/assets/bd4749c9-51b2-430d-bf38-78d108d08e1e" >
<img style="width:300px" src="https://github.com/user-attachments/assets/3824cade-254f-40ae-b308-e84417f9e833" >
<img style="width:300px" src="https://github.com/user-attachments/assets/1e53eaf5-9f01-420a-ab35-e4b6a934dbcb" > <br>
<img style="width:500px" src="https://github.com/user-attachments/assets/6982473a-192a-43de-9e63-691cb0fe578d" >

# Question 4

## The edge detection process involved:

### Canny Edge Detection:
Applied to a grayscale version of the image.
### Noise Reduction with Bilateral Filtering:
Two different bilateral filters were applied to smooth the image while preserving edges.
The Canny edge detector was then reapplied to these filtered images, effectively reducing unnecessary edges.
The results were displayed in a subplot, showing the original, grayscale, and edge-detected images for comparison.

<img style="width:500px" src="https://github.com/user-attachments/assets/f2893593-1525-4357-b8d8-ae85182c2138" >

# Question 5

The histogram equalization function performs the following:

Cumulative Distribution Function (CDF) Calculation:
Calculated the CDF of the original image.
### Interpolation:
Mapped the original intensity values to new values using linear interpolation against a target CDF.
### Resulting Image:
Adjusted the image using the interpolated values and displayed before-and-after comparisons.
### Visualization:
Plotted the CDF of the original and equalized images along with the target CDF, showing how pixel intensity distributions were adjusted for better contrast.

<img style="width:700px" src="https://github.com/user-attachments/assets/e45d4ac3-535e-41b5-b917-036b0445741f" > <br>
<img style="width:700px" src="https://github.com/user-attachments/assets/3cf15a2d-9364-4d85-b4dc-e90e760f9cbe" >
