# Wibci.Xamarin.Images
Some handy xamarin cross platform (Android / iOS / UWP) commands for image manipulation

- Available on NuGet: [![NuGet](https://img.shields.io/nuget/v/Wibci.Xamarin.Images.svg?label=NuGet)](https://www.nuget.org/packages/Wibci.Xamarin.Images/)

- ResizeImageCommand

Sample code:

```C#
var resizeImage = DependencyService.Get<IResizeImageCommand>();

var resizeResult = await resizeImage.ExecuteAsync(new ResizeImageContext { Height = 130, Width = 280, OriginalImage = pictureResult.Image });

if (resizeResult.TaskResult == TaskResult.Success)
{
  Model.Logo = resizeResult.ResizedImage;
}
```

Platform implementations:

Android:
`DependencyService.Register<IResizeImageCommand, AndroidResizeImageCommand>();`

iOS
`DependencyService.Register<IResizeImageCommand, iOSImageResizeCommand>();`

UWP:
`DependencyService.Register<IResizeImageCommand, UWPResizeImageCommand>();`

NOTE: For resizing images that come from the device or camera - check out James Montemagno's Xamarin Media Plugin
https://github.com/jamesmontemagno/MediaPlugin

Also - for a more comprehensive set of image features - check out https://github.com/humbertojaimes/DevKit.Xamarin.ImageKit
