# ImgSelect 

_Upload/Webcam Snapshot & Crop_

## Overview

Simple script to upload images for users avatars, as well with the option to take a picture with your webcam and upload it directly to the server. Also you have the option to crop the uploaded image. 

The script supports the following image file formats: jpg, jpeg, png, gif and bmp.

## Installation 

To install this script upload it on your webhosting, or copy to your localhost server. Then acces the script in your browser.

## Configuration 

The configuration options can be found in `inc/imgSelect.php` and `assets/imgSelect.js`.

__inc/imgSelect.php__:

- `IMG_MAX_WIDTH` - Image max width (in pixels)
- `IMG_MAX_HEIGHT` - Image max height (in pixels)
- `IMG_MIN_WIDTH` - Image min width (in pixels)
- `IMG_MIN_HEIGHT` - Image min height (in pixels)
- `IMG_CROP_WIDTH` - Image crop width (in pixels)
- `ALLOWED_IMAGES` - The allowed image extensions that can be uploaded
- `UPLOAD_PATH` - The path where you want to upload images

__assets/imgSelect.js__:

- `php` - Ajax url
- `alert` - Selector for the alert message
- `setImg` - After the image is saved this selector will be used to update the image from the page (optional)
- `crop` - Settings for crop
    - `width` - Default selection width (in pixels)
    - `height` - Default selection height (in pixels)
    - `aspectRatio` - A string of the form "width:height" which represents the aspect ratio to maintain ([see](http://andrew.hedges.name/experiments/aspect_ratio/))
    - `maxHeight` - Maximum selection height (in pixels) (optional)
    - `maxWidth` - Maximum selection width (in pixels) (optional)
    - `minHeight` - Minimum selection height (in pixels) (optional)
    - `minWidth` - Minimum selection width (in pixels) (optional)

## Save to Database

If you want to save the images to a database open `inc/imgSelect.php` and look for function `save_image_cb($image) {...}`. 

Use `$image` variable to get the image then save it to your database. 

Also if you want a custom name for the image edit `$filename` variable. You may set it to a user id from a session.

## Customization

The script has just few files that you might want to edit. The code has comments so you'll know what it does.

- `index.php` - HTML structure.
- `assets/imgSelect.css` - Few lines (but very important) of css.
- `assets/imgSelect.js` - All javascripts for uploading image, webcam and cropping option.
- `inc/imgSelect.php` - Here are processed all AJAX requests.

## Credits 

The script uses the following libraries and assets:

- [Bootstrap](http://getbootstrap.com/2.3.2)
- [jQuery](http://jquery.com)
- [AjaxUpload](http://valums.com) by Andris Valums
- [jQuery imgAreaSelect](http://odyniec.net/projects/imgareaselect)
- [PHP SimpleImage Class](http://www.white-hat-web-design.co.uk/articles/php-image-resizing.php) by Simon Jarvis with modifications for BMP images by [dev77](http://de77.com)
