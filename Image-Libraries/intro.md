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




