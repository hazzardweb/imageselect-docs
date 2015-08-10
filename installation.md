# Avatar Upload & Webcam with Crop


## Overview

Simple script to upload images for users avatars, as well with the option to take a picture with your webcam and upload it directly to the server. Also you have the option to crop the uploaded image. 

The script supports the following image file formats: jpg, jpeg, png, gif and bmp.

## Installation 

To install this script upload it on your webhosting, or copy to your localhost server. Then acces the script in your browser.

## Configuration 

The configuration is located in the script root folder in `config.php`. The default configuration should be ok for you but If you want to edit something here's what you can edit:

- `UPLOAD_PATH` - The path where you want to upload images.
- `ALLOWED_EXTENSIONS` - The allowed file extensions that users can upload to your server.
- `IMAGE_MAX_WIDTH` - When someone uploads a image this image will be resized so you won't store too large images on your server.
- `IMAGE_MAX_HEIGHT` - Same as above, only here is the image maximum height.
- `IMAGE_CROP_SIZE` - When someone crop their uploaded image this will be the size that the image will be resized.
- `FILE_SIZE_LIMIT` - The maximum file size accepted for upload (in Megabytes)

## Customization

The script has just few files that you might want to edit. The code has comments so you'll know what it does.

- `index.php` - Here you can edit the html structure.
- `assets/css/slyle.css` - Here are you can add more css.
- `assets/js/script.js` - All javascripts for uploading image, webcam and cropping option.
- `includes/ajax.php` - The Ajax requests from script.js will be sent here, and the image will be uploaded or cropped.
- `includes/functions.php` - The functions for the script.

The rest of the files contains PHP image classes and other functions as well as javascript libraries and [Bootstrap](http://getbootstrap.com/2.3.2) assets. 

## Credits 

The script uses the following libraries and assets:

- [Bootstrap](http://getbootstrap.com/2.3.2)
- [jQuery](http://jquery.com)
- [AjaxUpload](http://valums.com) by Andris Valums
- [jQuery imgAreaSelect](http://odyniec.net/projects/imgareaselect)
- [PHP SimpleImage Class](http://www.white-hat-web-design.co.uk/articles/php-image-resizing.php) by Simon Jarvis with modifications for BMP images by [dev77](http://de77.com)
