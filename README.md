
# Image Manipulation

This project is an application that is able to modify images as well as create new images using 2D arrays! The first section covers stretching the image horizontally, shrinking the image vertically, negating the color, applying a color filter, and inverting the image. The second section covers creating an image consisting of random pixels, placing a rectangle in the image, and using the method to randomly place rectangles in the image.

&nbsp;

Here is an overview about how images work in Java:

Images consist of pixels which are the individual points in the image containing some color. Each pixel has some red, green, blue, and alpha value which represents the amount of each of those colors in the pixel. The red, green, and blue values can be mixed to create all of the visible colors on your screen. The alpha value represents the transparency of the pixel (or how close the color of the pixel is to the background color of the image). A higher resolution image means that there are more pixels contained within it.

&nbsp;

In Java, a loaded image is stored into a `BufferedImage` object. From this object, we can extract each pixel value and store it into a 2D array which we can manipulate. The pixel values are stored as `int`s because each pixel value in the `BufferedImage` object is represented by a hexadecimal value which contains the red, green, blue, and alpha components. The maximum value of any of the RGBA values is 255 and the minimum is 0. 

&nbsp;

### Utility Methods

* `imgToTwoD()` accepts a `String` that can be a file path or image URL. It returns a 2D array of integers that contains every pixel from the image stored as `int` hexadecimal values containing the RGBA values for the pixel.

* `twoDToImage()` accepts a 2D array of integers and a `String` for the file name. It converts the 2D array of `int` pixel data into an image and saves it.

* `getRGBAFromPixel()` accepts an `int` value representing the pixel hexadecimal value and returns a 4 element `int` array consisting of the R, G, B, and A values (between 0 and 255).

* `getColorIntValFromRGBA()` accepts an array of integers that represent the RGBA values and convert it into a single `int` value representing the pixel hexadecimal value. 


In addition to these utility methods, there is a method used for extracting a 3x3 section from the top left of the image called `viewImageData`. This method is used to view the structure of the image data in both the raw pixel form and the extracted RGBA form.

&nbsp;

### Image Processing Methods 

* `trimBorders()` accepts a 2D array of `int` pixel data and the number of pixels to trim off of the borders of the image. It returns the modified image 2D array.

* `negativeColor()` replaces the color of each pixel in the image with the negative version of the pixel. This means that each color component of the pixel (R, G, and B) will be replaced with 255 minus the current value.

* `stretchHorizontally()` doubles the width of the provided image data.

* `shrinkVertically()` halfs the height of the image and select every other pixel down each column to place in the modified image. 

* `invertImage()` flips the image vertically and horizontally.

* `colorFilter()` modifies every pixel in the image by providing R, G, and B values as input parameters (color value must be 0-255). For example, the filter -75, 30, -30 means that the red values were decreased by 75, the green values were increased by 30, and the blue values were decreased by 30.

&nbsp;

### Painting Methods 

* `paintRandomImage()` modifies the image passed in by replacing every pixel with a randomly colored pixel.

* `paintRectangle()` draws a rectangle on an image using a provided `width`, `height`, `rowPosition`, `columnPosition`, and `color`.

* `generateRectangles()` uses the `paintRectangles()` method in order to paint a piece of art. It will generate randomly positioned, sized, and colored rectangles based on the provided number. The input parameter, `numRectangles` will determine how many randomly generated rectangles will be placed in the image.
