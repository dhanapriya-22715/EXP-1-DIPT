# EXP-1-Image Handling and Pixel Transformation Using Opencv
## NAME : Dhanappriya S
## REG NO :212224230056
## DATE : 23/10/2026
# AIM:
To perform image handling and pixel transformations using OpenCV by loading, displaying, converting, and manipulating images through pixel-level operations.
# PROCEDURE:
Step1:

Load an image from your local directory and display it.
Step2:

o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.

Step3:

o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.

Step4:

o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.

Step5:

o Resize the original image to half its size and display it.

Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

Step7:
o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.

Step8:
o Save the final modified image to your local directory.
# CODE:
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('photo.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
# Load the image
image = cv2.imread('photo.jpg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(200,150),150,(255,0,5),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (490, 480), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "DHANAPPRIYA S", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 15)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[100:250, 100:250] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('photo.jpg')
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('photo.jpg')
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('photo.jpg')
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
# OUTPUT :
<img width="1422" height="407" alt="image" src="https://github.com/user-attachments/assets/523c135d-3318-4672-b43b-fca636b816ed" />
<img width="952" height="548" alt="image" src="https://github.com/user-attachments/assets/c871c926-7d1b-4205-a4bc-47c13c1524eb" />
<img width="901" height="512" alt="image" src="https://github.com/user-attachments/assets/e6d2b46f-13b4-4221-a39e-aaf329b781e7" />
<img width="820" height="541" alt="image" src="https://github.com/user-attachments/assets/299910e6-4153-4137-9d71-0b3228b14526" />
<img width="860" height="527" alt="image" src="https://github.com/user-attachments/assets/d0c50edb-0374-493e-a90e-cd89173c3ff9" />
<img width="948" height="560" alt="image" src="https://github.com/user-attachments/assets/8a604793-e97f-4f78-b5e0-319c9b12173f" />
<img width="868" height="562" alt="image" src="https://github.com/user-attachments/assets/1e194295-929a-408a-bce6-8ee7469f65c7" />
<img width="905" height="560" alt="image" src="https://github.com/user-attachments/assets/c1fc379b-1f87-413d-a11f-a276c407b9c4" />
<img width="892" height="557" alt="image" src="https://github.com/user-attachments/assets/74fb3b3c-ecf1-4aa3-b283-242d781e10e9" />
<img width="903" height="557" alt="image" src="https://github.com/user-attachments/assets/c34e4b8a-22e2-4d29-90a1-e07790757421" />
<img width="891" height="500" alt="image" src="https://github.com/user-attachments/assets/34021f03-1204-4328-bfc0-cca5f58a0309" />
<img width="912" height="515" alt="image" src="https://github.com/user-attachments/assets/1147e899-1d1d-4c2f-a627-f8e4d73d3944" />
<img width="910" height="521" alt="image" src="https://github.com/user-attachments/assets/ffabe891-9681-462a-b9b0-1b2e35cd5f77" />
<img width="882" height="570" alt="image" src="https://github.com/user-attachments/assets/135a7cfa-d79b-4b7d-b355-ba7ec0f985f6" />
<img width="912" height="576" alt="image" src="https://github.com/user-attachments/assets/d193f1f6-ce2c-4261-b0d5-e71741742fb1" />

# RESULT :
Thus  the Image Handling and Pixel Transformation Using Opencv was verified successfully.
         







