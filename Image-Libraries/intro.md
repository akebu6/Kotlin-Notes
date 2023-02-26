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






