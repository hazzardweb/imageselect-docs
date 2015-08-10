# Options & Callbacks - PHP

- [Options](#options)
- [Callbacks](#callbacks)

The first argument of the `ImgSelect` class is for options:

```php
new ImgSelect(array(
    'upload_dir' => 'files/',
    'accept_file_types' => 'png|jpg|jpeg|gif',
    // other options...
));
```

## Options

### upload_dir

The upload directory relative to the `server` folder.

- Type: _string_
- Default: `files`

### accept_file_types

The accepted file types.

- Type: _string_
- Default: `png|jpg|jpeg|gif`

### mkdir_mode

The [mkdir](http://php.net/manual/en/function.mkdir.php) mode used when creating the upload directory.

- Type: _int_
- Default: `0755`

### max_file_size

The maximum file size in bytes. 

- Type: _int_
- Default: `null`

### min_file_size

The minimum file size in bytes. 

- Type: _int_
- Default: `1`

### max_width

The maximum image width. 

- Type: _int_
- Default: `null`

### max_height

The maximum image height. 

- Type: _int_
- Defaullt: `null`

### min_width

The minimum image width: 

- Type: _int_
- Default: `1`

### min_height

The minimum image height. 

- Type: _int_
- Default: `1`

### force_crop

If the image size < crop size then force the resize. 

- Type: _boolean_
- Default: `true`

### crop_max_width

The crop maximum width. 

- Type: _int_
- Default: `null`

### crop_max_height

The crop maximum height. 

- Type: _int_
- Default: `null`

## Callbacks

### before_upload

`before_upload($image, $instance)` - Called before uploading the file to the server.

The `$image` object has the following properties:

- `name` - Image name (including the extension).
- `type` - Image extension.
- `size` - Image size in bytes.
- `path` - Image path. 
- `url` - Image url.
- `width` - Image width.
- `height` - image height.

The `$instance` object is the current `ImgSelect` instance.

In this callback you can rename the uploaded file:

```php
new ImgSelect(array(
    // options...
    `before_upload` => function ($image, $instance) {
        $image->name = 'custom_name.'.$image->type;
    },
));
```

### upload_complete

`upload_complete($image, $instance)` - Called when the upload is completed.

The `$image` object has the same properties as [above](#before_upload).

### before_crop

`before_crop($crop, $instance)` - Called before cropping the image.

The `$crop` object has the following properties:

- `file_name` - The image name to be cropped.
- `file_type` - The image type.
- `src_path`, `dst_path`, `src_h`, `src_w`, `src_y`, `src_x`, `dst_w` and `dst_h` are described in `ImgSelect.php` in the `resizeImage` method. 

In this callback you may set the crop destionaton path so the original file will be keept:

```php
new ImgSelect(array(
    // options...
    before_crop => function ($crop, $instance) {
        $crop->dst_path = $instance->getUploadPath('my_image.'.$crop->file_type);
    }
));
```

### crop_complete

`crop_complete($image, $instance)` -  Called when the crop is completed.

The `$image` object has the same properties as [above](#before_upload).

In this callback you may save the image into database using `$image->name` to get the image name.
