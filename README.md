# Image-Watermarking

Digital watermarking is the method of embedding data into digital multimedia 
content. This is used to verify the credibility of the content or to recognize the 
identity of the digital content's owner.
Image watermarking is embedded text or logos over a digital image. This watermark 
graphic or text indicates ownership or copyright of the image. It makes it difficult for 
someone to use the image without permission or claim ownership of the original. It’s 
typically in the corner of the image but can be anywhere across the photo.


<h3>Algorithm</h3>

**Embedding:**

1. Input CoverImage and WaterMarkImage  
2. Retrieve any 1 channel from 3 channels of cover image and store in a 
matrix called test .  
3. Put all the pixel values of WaterMarkImage to a 1D array wm_array  
4. Repeat following steps until wm_array is traversed or test array is fully 
traversed  
  I. take next 8X8 matrix from test array  
  II. apply DCT function to get the DCT coefficients  
  III. Choose a index from 8X8 matrix as per key scheduling algorithm and 
  put the next pixel value from wm_array to that index  
  IV. Apply inverse DCT function to that 8X8 matrix  
5. Create a new array embed_img of size equal to test but with 3 channels.  
6. Copy the value of test to one channel of embed_img , fill the values of 
other 2 channels with CoverImage values.  
7. Return embed_img, It is the new watermarked image  

**Extraction:**

1. Input Image: water_marked  
2. Retrieve the required channel from 3 channels of water_marked image 
and store in a matrix called test_1 .  
3. Create a list ext_wm  
4. Repeat following steps until all watermark pixels are retrieved  
  I. take next 8X8 matrix from test_1 array  
  II. apply DCT function to get the DCT coefficients  
  III. Choose the specific index from 8X8 matrix as per key scheduling
  algorithm and retrieve the pixel , append that pixel to ext_wm  
5. Reshape the ext_wm according to the size of watermark image size  
6. Return ext_wm, It is the extracted watermark  


<h3>Steps to Execute the Code</h3>

1. Upload the cover images and watermark images in Colab, whenever a new 
session starts upload the images again.  
2. Name the Images as following:  
Cover images  
 Color Image : <b>cover.jpg</b>  
 Greyscale image : <b>lena.png</b>  
Watermark Images:  
  Color watermark : <b>iitbbs_logo.jpeg</b>  
  Greyscale watermark : <b>logo.png</b>  
3. Run the code in colab, It will ask for input to choose cover image and watermark
image as per user choice.  
Choose 1 for choosing Colored cover image, 2 for greyscale covered image  
Choose 1 for choosing colored watermark and 2 for greyscale watermark  
4. Enter the secret key  
5. After the execution finishes, watermarked images will be produced.
Later you can run the extraction code and attack codes.  
