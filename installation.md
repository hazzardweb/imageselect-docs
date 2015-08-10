# Image Select 

_Uploader - Webcam - Cropper_

## Installation

This script requires PHP5.3+ and [GD](http://www.php.net/manual/en/book.image.php) extension.

- Extract and copy the files from the archive you have downloaded from CodeCanyon to your server or local server.
- Make sure the `files` directory has `777` permission.
- Run the script in your browser. See the included examples.

## Usage

First make sure you have included the CSS (`buttons.css` is optional) & JavaScript files:

```markup
<link rel="stylesheet" href="assets/css/buttons.css">
<link rel="stylesheet" href="assets/css/imgSelect.css">
 
<script src="assets/js/jquery-1.11.0.min.js"></script>
<script src="assets/js/jquery.Jcrop.min.js"></script>
<script src="assets/js/imgSelect.js"></script> 
<!-- For production use imgSelect.min.js -->
```

Then you'll have to include the HTML:

```markup
<!-- imgSelect Container -->
<div id="imgselect_container">
    <!-- Upload & Webcam buttons -->
    <div class="btn btn-primary imgs-upload">Upload</div>
    <button type="button" class="btn btn-success imgs-webcam">Webcam</button>
 
    <!-- Webcam & Crop containers -->
    <div class="imgs-webcam-container"></div>
    <div class="imgs-crop-container"></div>
 
    <!-- Action buttons -->
    <button type="button" class="btn btn-primary imgs-save">Save Image</button
    <button type="button" class="btn btn-primary imgs-newsnap">New Snapshot</button>
    <button type="button" class="btn btn-primary imgs-capture">Capture</button>
    <button type="button" class="btn btn-default imgs-cancel">Cancel</button>
    
    <div class="imgs-alert alert"></div>
</div>
```
