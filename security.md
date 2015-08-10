# Security

Allowing users to upload files to the server can be dangerous. But if you don't allow to upload anything else than images everything is fine.

One other thing will be the crop option. After the image is uploaded and the user makes the crop selection a request is ent back to the server with the image name and crop information.

The image name can be easily changed to someone's else image so the resize will be applied on that one. 
To fix this in the [before_crop](optionsphp.md#before_crop) callback described you can check if that image belongs to the current user.
