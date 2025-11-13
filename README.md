# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages


### Step2:
Give the input text using cv2.putText()

### Step3:
Perform opening operation and display the result

### Step4:
Similarly, perform closing operation and display the result


 
## Program:

``` Python
import numpy as np
import cv2
import matplotlib.pyplot as plt
blank=np.zeros((600,600))
import numpy as np
import matplotlib.pyplot as plt

image = np.zeros((600, 600, 3), dtype=np.uint8)

plt.imshow(image)
plt.axis('on')
plt.show()

def load_image():
    blank_image = np.zeros((600,600))
    font = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_image,text='SANJU',org=(50,300),fontFace=font,fontScale = 5,color=(255,255,255),thickness=25,lineType=cv2.LINE_AA)
    return blank_image
def display_img(img):
    fig = plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()
img=load_image()
kernel=np.ones((5,5),dtype=np.uint8)
white_noise=np.random.randint(low=0,high=2,size=(600,600))
white_noise = white_noise*255
noise_img = white_noise+img
display_img(noise_img)
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)
display_img(opening)
black_noise = np.random.randint(low=0,high=2,size=(600,600))
black_noise= black_noise * -255
black_noise_img = img + black_noise
black_noise_img[black_noise_img==-255] = 0
display_img(black_noise_img)
closing = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing)
display_img(img)
gradient = cv2.morphologyEx(img,cv2.MORPH_GRADIENT,kernel)
display_img(gradient)

```
## Output:

### Display the input Image
<img width="581" height="550" alt="image" src="https://github.com/user-attachments/assets/9083a033-32c0-4309-86c4-072e4681acdd" />

### Noise img:
<img width="575" height="539" alt="image" src="https://github.com/user-attachments/assets/aca4e562-5d18-4bd8-9277-9632bd2bf3b9" />

### Display the result of Opening
<img width="557" height="557" alt="image" src="https://github.com/user-attachments/assets/30aca8a0-8af7-497c-91ad-b4ac109a0046" />

### Black noise img:
<img width="603" height="572" alt="image" src="https://github.com/user-attachments/assets/cf7faf3b-cbae-4628-a50c-0d9795fb5f8a" />

### Display the result of Closing
<img width="583" height="562" alt="image" src="https://github.com/user-attachments/assets/793c9149-2b08-400b-af70-62bb2bf4d004" />

### Gradient img:
<img width="582" height="562" alt="image" src="https://github.com/user-attachments/assets/6843e8e2-a9c2-40a7-9260-0672283f2194" />


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
