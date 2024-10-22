<!-- Filename: J4.x:Media:_Image_Crop_Resize_Rotate / Display title: Image Crop Resize Rotate -->

## Introduction

After upload you may have realised there is a problem with an uploaded
image. Common problems include:

- The image is much too big.
- The interesting part of an image is in a small area.
- The image is rotated through 90 degrees.

These are the problems that the Media component can handle.

As an example, the following image shows a group of animals that is a little
too big for its intended purpose. It could be cropped or it could be resized.

![Picture of animals](../../../en/images/media/media-crop-serengeti.png)

## Crop

The crop tool allows you to drag to define a crop area. This is a little
tricky. First set an aspect ratio or None as you see fit. Then click and drag 
the corners or top or bottom or either side of the selection box which is
outlined in blue.  You can drag the inside of the selection box to move it to
centre your subject. You may also manually adjust the X- and Y-Axis
offsets and the width and height.

Look carefully at the screenshot and you will see a selection box outline of
the area to be included in the proposed crop.

The quality selector indicates how much compression should be applied.
Too much and the image size in bytes will be too big. Too little and the
display quality of the image will be poor. **Bug Warning:** At the moment the 
Quality control is not working. This results in a modified image being larger 
than it needs to be, sometimes much larger than the original!

When satisfied, select the *Save* button in the Toolbar.

The newly cropped image will be saved. **There is no Undo!** In the Crop
view the crop box and values in the crop fields will be wrong (another bug?)
but the crop is done, so move on.

## Resize

To resize an image select a suitable width. The height will change to keep
the aspect ratio of the original image.

## Rotate

If an image is rotated through 90 degrees, select the Rotate tab and the 
appropriate angle.
