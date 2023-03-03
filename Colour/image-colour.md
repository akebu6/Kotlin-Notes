# Intro
> A bitmap image consists of a 2-dimensional (2-D) matrix of dots, called pixels, each of which can be assigned a different color. These dots can be used to describe any kind of rectangular image. Common color translation schemes are the 24-bit RGB and 32-bit RGBA color models.

# RGB Color, Alpha channel
- In most cases, the RGB color model is used with 24-bit data for each pixel. 
- Hence, each pixel can have 16,777,216 different colors. 
- This color scheme is called **True Color**.
- An extension to the RGB is the ARGB color mode, which is similar to RGB colors but also contains opacity information. 
- ‘A’ stands for `Alpha` or `Alpha channel` and denotes the transparency of each pixel. 
- An Alpha value of 0 indicates that the pixel is clear, while the maximum value indicates that the pixel is opaque.
- Most commonly, ARGB is used with 32-bit data for each pixel. Each color and alpha channel is 8-bit long.
- The following image illustrates the 32-bit ARGB color scheme for a pixel. Each small rectangle denotes a single bit.

![32bitcolor](https://user-images.githubusercontent.com/74776297/222815356-73fea7c4-4af0-48f0-8112-faa1bb142245.png)

### Example
The following picture is an example for the use of the alpha channel. It shows two images created with a variable alpha channel (different opacity for each pixel). These images are put over a text background (like, e.g., on a web page), so the variable transparency is evident.

![alphaChannel](https://user-images.githubusercontent.com/74776297/222815548-76ec7fb3-4563-4472-a8c9-97096202a5e2.png)

**NOTE:** Note that the actual use of the alpha channel data depends on the program. The data may be ignored, used for transparency or in some other manner in order to create some complex image blending.

# Image coordinate system
- Java and consequently Kotlin use the `BufferedImage` class in order to handle images. It belongs to the `java.awt` package and is a subclass of the Image class. Therefore, it has to be imported into a program:
```js
import java.awt.image.BufferedImage
```
- A BufferedImage instance coordinate system is quite simple. 
- A pixel position is defined by a pair of natural numbers that correspond to the pixel column and row respectively, with columns running from left to right and rows running from top to bottom. The starting row and column position number is zero. - In the `BufferedImage` instance positioning system, the first coordinate is the column number, and the second is the row number. 
- For example, a pixel with the position (4, 7) is located in the 5th column (from left to right) and in the 8th row (from top to bottom).

![coordinates](https://user-images.githubusercontent.com/74776297/222819020-9c46defa-8870-46a3-94c8-180692f2aacd.png)


# Read and Set pixel color
- A pixel’s color can be read as an integer using the `getRGB(x, y)` function, where x and y are the column and row pixel positions respectively. 
- A Kotlin integer has a size of 32 bits, so it can hold the color values for both the 24-bit RGB and 32-bit ARGB color schemes.
- A pixel’s color can be set using the `setRGB(x, y, rgb)` function, where x and y are the column and row pixel positions respectively, and rgb is the pixel color as an integer.
- In order to easily work with the acquired color value and avoid bitwise operations, the Color class should be used. Color belongs to the Java `java.awt` package and has to be imported:
```js
import java.awt.Color
```
- A Color instance can be initiated in many ways:
1. `Color(rgb)`, where `rgb `is the integer value of 24-bit color read by the` getRGB()` function (without alpha channel);
2. `Color(argb, true)`, where `argb` is the integer value of 32-bit color (with alpha channel);
3. `Color(r, g, b)`, where `r, g, and b` are the values for each basic color;
4. `Color(r, g, b, a)` where `r, g, and b` are the values for each basic color, and `a` is the value of the alpha channel.

### Example
In the following code example, an image file is read. Then, for each pixel in the created BufferedImage instance, the red color is set to 255, while the green and the blue colors remain unchanged. The BufferedImage instance is then saved as a new file. Note that a new Color instance has to be created.
```js
import java.io.File                   // Import the File class for file handling
import javax.imageio.ImageIO          // Import the ImageIO class for reading and writing images
import java.awt.image.BufferedImage   // BufferedImage Class
import java.awt.Color                 // Color class

fun main() {
   val inputFile = File("24bit.png")  // Create a file instance in order to read the "24bit.png" image file

   // Create a BufferedImage instance from the 24-bit image file data
   val myImage: BufferedImage = ImageIO.read(inputFile)  

   // myImage.width is the image width
   // myImage.height is the image height
   for (x in 0 until myImage.width) {               // For every column.
       for (y in 0 until myImage.height) {          // For every row
           val color = Color(myImage.getRGB(x, y))  // Read color from the (x, y) position

           val g = color.green              // Access the Green color value
           val b = color.blue               // Access the Blue color value
           // Use color.red in case the Red color is needed

           val colorNew = Color(255, g, b)  // Create a new Color instance with the red value equal to 255
           myImage.setRGB(x, y, colorNew.rgb)  // Set the new color at the (x, y) position
       }
   }
   val outputFileJpg = File("newImageFile.jpg")  // Output the file
   ImageIO.write(myImage, "jpg", outputFileJpg)  // Create an image using the BufferedImage instance data
}
```
- The picture below illustrates the above code applied to the left image in order to produce the image on the right.

![red](https://user-images.githubusercontent.com/74776297/222821329-eeafb807-b4f5-4a95-9821-e1d853c096c5.png)


3. s the integer value of 32-bit color (with alpha channel);
