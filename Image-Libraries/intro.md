 # Intro
 
- Digital image processing is the technique of using computers to process (view, edit, and transform) digital images. 
- The benefit of using computers to process images is the ease of applying various edits or transformations to the image compared with analog processing.

- Digital image processing has a wide range of applications spread across various industries – for example, processing satellite data and transforming it into maps, transforming real-life photographs into textures that can be used in video games, modifying your favourite profile picture using image filters, and many others.

# What are images?
- An image is a two-dimensional collection of points of color encoding a visual – for example, a photograph or a piece of digital art. 
- We distinguish between two types of image encodings: raster graphics and vector graphics.
- A raster image is a dot matrix data structure containing a grid of pixels. Pixels are points of color (optionally, with a transparency value) in the two-dimensional (X, Y) screen space.
- As they are maps of bits (hence the name bitmap), raster images cannot be scaled up or down to different resolutions without distortion (aliasing).
- Vector images are points on a two-dimensional plane that are connected by lines and curves to form polygons and other geometric shapes. 
- As such, they can easily be redrawn at any scale without aliasing.

# Images in Kotlin
- mages are represented by the `java.awt.Image class`.
- This is the class at the top of the hierarchy for all graphical images. 
- For the purpose of this lesson, we will focus on an image subclass, `BufferedImage`.
- A `BufferedImage` exposes the buffer of image data that can be read or modified.

# Creating Images
- Creating an image from scratch is as simple as creating an instance of BufferedImage.
```js
import java.awt.image.BufferedImage 

val height: Int = 800
val width: Int = 600
val image = BufferedImage(width, height, BufferedImage.TYPE_INT_RGB)
```
- The last parameter in this particular constructor represents the image type. 
- The TYPE_INT_RGB represents an image with 8 bits (or one byte) per color component, with the colors Red, Green, and Blue stored in 3 bytes.
- Other examples of image types are:
1. TYPE_INT_ARGB, which includes a transparency (sometimes called an alpha) component;
2. TYPE_BYTE_GRAY, which only includes a single byte value to encode a grayscale color.

# Editing Images
- In order to edit images, we could directly access the pixel matrix in the BufferedImage; however, this is very inconvenient, especially if we want to draw more complex geometry, such as lines, polygons, text, or other images.
- ckily, there is a more convenient way to do this. From a BufferedImage, we can create a `Graphics2D` by using the `createGraphics()` method.
```js
val graphics = image.createGraphics()
```
- This class offers a lot of convenient methods for two-dimensional drawing, such as:

| function | use |
| ---- | ---------- |
| drawString(String, Int, Int) | Draws a string at the specified (x, y) coordinates |
| drawString(String, Float, Float) | Draws a string at the specified (x, y) coordinates |
| drawLine(x1: Int, y1: Int, x2: Int, y2: Int) | Draws a line between the given points (x1, y1) and (x2, y2) |
| drawPolygon(IntArray, IntArray, Int) | 	
Draws a polygon between the points with x-coordinates contained in the first IntArray and y-coordinates in the second IntArray. The third parameter is the number of points contained in the arrays |
| drawOval(x: Int, y: Int, width: Int, height: Int) | Draws an oval at (x, y) with the specified width and height |
| drawPolyLine(IntArray, IntArray, Int) | Draws a PolyLine. The parameters are the same as for drawing a polygon | 
| drawRect(x: Int, y: Int, width: Int, height: Int) | Draws the outline of the specified rectangle |

- Building on the newly created image above, drawing a string becomes as simple as:
```js
graphics.drawString("Playing with images", 80, 80)

graphics.color = Color.ORANGE

graphics.drawArc(200, 200, 100, 250, 45, 90)
```
- The code above will draw a white (the default color) string at the position (80, 80). 
- It will then change the drawing color to orange and use it to draw an arc at (200, 200) of width 100 and height 250, with a start angle of 45 and an arc angle of 90.


# Writing and Reading Images
- nstead of programmatically creating an image from scratch, the j`avax.imageio.ImageIO` class offers many convenient methods for encoding (writing) and decoding (reading) images from files in the supported formats.
- Format is the binary encoding of an image, and the following formats are supported out of the box: JPEG, PNG, BMP, WBMP, and GIF.
- In order to save this newly created image, we will use the `ImageIO.write(im: BufferedImage, formatName: String, output: File)` method and save the image as a PNG file.
```js
import java.awt.image.BufferedImage
import java.io.File
import javax.imageio.ImageIO

val height: Int = 800
val width: Int = 600

val image = BufferedImage(width, height, BufferedImage.TYPE_INT_RGB)
val imageFile = File("myFirstImage.png")

saveImage(image, imageFile)   

fun saveImage(image: BufferedImage, imageFile: File) {
  ImageIO.write(image, "png", imageFile)
}
```
- With the file saved to disk, we can reuse it later to continue our work. 
- We will continue by adding a red triangle to the image we have created so far.

- The first step to do this is to read the file into a BufferedImage using the `ImageIO.read(File input)` function.
```js import java.awt.Color
import java.awt.image.BufferedImage
import java.io.File
import javax.imageio.ImageIO

val imageFile = File("myFirstImage.png")

val image: BufferedImage = ImageIO.read(imageFile)
```
- Secondly, we need to obtain a Graphics2D instance, and change the color to red.
```js
val graphics = image.createGraphics()

graphics.color = Color.RED
```
- Finally, we will use the `Graphics2D.drawPolygon(IntArray, IntArray, Int)` function to draw our triangle. Remember that the parameters are: an array containing the X-axis coordinates, a second array containing the corresponding Y-axis coordinates, and the size of the arrays.
```js
graphics.drawPolygon(intArrayOf(10, 20, 30), intArrayOf(100, 20, 100), 3)
```
- Defining the form of a triangle is beyond the scope of the current lesson. 
- However, note that the points must form an area greater than zero, and be non-collinear. Finally, in order to save the newly drawn triangle, let’s reuse the saveImage function defined above.
```js
saveImage(image, imageFile)
```







