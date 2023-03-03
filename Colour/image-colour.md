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




