# Options & Callbacks - JavaScript

- [Options](#options)
- [Callbacks](#callbacks)

## Options

The options are the second parameter of the `ImgSelect()` function. This must be an object.

```javascript
new ImgSelect($('#imgselect_container'), { 
    url : 'server/upload.php',
    // more options...
});
```

### url

URL to which the request is sent. Default: `server/upload.php`

### crop

Object of options for the [Jcrop](http://deepliquid.com/content/Jcrop_Manual.html#Setting_Options). If set to `null` the crop will be disabled.

- `aspectRatio` -  Aspect ratio of width/height (e.g. _1_ for square). Default: `null`
- `minSize` - Minimum width/height (e.g. _[100, 100]_). Default: `null`
- `maxSize` - Maximum width/height (e.g. _[500, 500]_). Default: `null`
- `setSelect` - Set an initial selection area (_[ x1, y1, x2, y2 ]_). Default: `null`

### ​data

Object or Function of custom data to be sent to the server.

__Example:__

```javascript
// Object
data: {
    id: 12,
    val: 'hello',
},

// Or function
data: function () {
    return {
        id: 12,
        val: $('#my-input').val(),
    };
},
```

On the server side, inside the [callbacks](optionsphp.md#callbacks), the data can be retrieved  using ` $_POST['data']`.

```php
new ImgSelect(array(
    // ...
    'before_before' => function ($crop) {
        $id = $_POST['data']['id'];
        $val = $_POST['data']['val'];
    },
));
```

### messages

Object of messages.

- _invalidJson_: 'Invalid JSON response.'
- _uploadError_: 'Ajax upload error.'
- _webcam_: 'Webcam Error: '
- _flashwebcam_: 'Webcam Error. Please try again.'
- _uploading_: 'Uploading...'
- _saving_: 'Saving...'
- _jcrop_: 'jQuery Jcrop not loaded'
- _minCropWidth_: 'Crop selection requires a minimum width of '
- _maxCropWidth_: 'Crop selection exceeds maximum width of '
- _minCropHeight_: 'Crop selection requires a height of '
- _maxCropHeight_: 'Crop selection exceeds maximum height of '

## Callbacks

The callbacks are functions that are executed when an action is completed.

### uploadComplete(image)

Called when the upload is completed. The `image` parameter has the following properties:

- `name` - Uploaded file name (including the file extension).
- `type` - File extension.
- `url` - The URL to the uploaded file.
- `size` - Uploaded file size in bytes.
- `width` - Image width.
- `height` - Image height.

Example:

```javascript
new ImgSelect($('#imgselect_container'), {
    uploadComplete: function(image) {
        alert(image.name);
    },
});
```

### cropComplete(image)

Called after the image was cropped. Is the same as `uploadComplete` (but does not have `size` property).

### alert(message, type) 

Called whenever an error occurs, or when the file is uploading. If you use this the default one will be override. 

The `type` is a numeric value: `0` - hide message, `1` - success message, `2` - warning/loading message and `3` - error message.
