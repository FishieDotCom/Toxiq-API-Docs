# Media
![image](/Images/media.jpg)  
Media is an important part of any platform


## MediaDto
the following [Media Types](/Enums/PostEnum.md#media-type) are supported on Toxiq

| Property    | Type           | Description                          | Is Required |
|-------------|----------------|--------------------------------------|-------------|
| MediaType   | [Media Types](/Enums/PostEnum.md#media-type)     | The type of media (e.g., image, video). | Yes         |
| MediaId     | Guid?         | Ref previously uploaded media. | No          |
| MediaPath   | string?       |  media.   | No          |



## Best pactices 
- when submiting a post or comment its best to set ```MediaType``` to ```Non or 0``` 
- when a user selects an image the client must prompt a crop screen where the user has to crop the image to **1:1 aspect ratio**
- All images uploaded to toxiq must be **1:1 aspect ratio**
- Post images cant be larger then **512px**
- Comment Images must be cropped and compressed to **1:1 128px**
- client must compress any images larger then **1MB** before sending to API

### Reuse Media
Toxiq has updated to ```MediaId``` system where every file uploaded would have a Id. Clients must reuse ```MediaId``` whenever possible to reduce load on server. 

### Uploading Media
to upload media simply select the correct [Media Type](/Enums/PostEnum.md#media-type) and convert your media to bas64 and assign it to `MediaPath`

