#Adding SimpleCam to Your Project

###1. Add SimpleCam Folder to Xcode

- Unzip SimpleCam
- Drag SimpleCam Folder into your Xcode project
- Make sure "Copy items into destination group's folder (if needed)" is selected

###2. Your ViewController.h File

- Import SimpleCam
- Set up your view controller as a simpleCam delegate

```Obj-C
#import <UIKit/UIKit.h>
#import "SimpleCam.h"

@interface ViewController : UIViewController <SimpleCamDelegate>

@end
```

<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/ViewControllerHeader.gif?raw=true"><img />
</p>

###3. Set Up Delegate

- Add SimpleCam's Delegate method to your ViewController.m file

```Obj-C
#pragma mark SIMPLE CAM DELEGATE

- (void) closeSimpleCamWithImage:(UIImage *)image {
    if (image) {
        // closed with image
    }
    else {
        // user backed out w/o image
    }
}
```

This is how SimpleCam will notify your ViewController that the user is finished with it.  If there is an image, then the user took a picture.  If there is not, then the user backed out of the camera without taking a photograph.

<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SetUpDelegate.gif?raw=true" width=750></img> 
</p>

###4. Launch SimpleCam

- Add this code wherever you'd like SimpleCam to launch

```Obj-C
SimpleCam * simpleCam = [[SimpleCam alloc]init];
simpleCam.delegate = self;    
[self presentViewController:simpleCam animated:YES completion:nil];
```
If you'd like to launch simple cam when the user presses a button, you could add the above code to the IBAction method, like so:

```Obj-C
-(IBAction)buttonPress:(id)sender
{        
  SimpleCam * simpleCam = [[SimpleCam alloc]init];
  simpleCam.delegate = self;    
  [self presentViewController:simpleCam animated:YES completion:nil];
}
```
That's it, it's as  simple as that.  SimpleCam will take care of everything else.

#Screen Shots

###Portrait

<h5 align="center">Camera (About To Capture)</h5>
<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SimpleCamScreenShots/portrait_Camera.png?raw=true" width=320></img> 
</p>

<h5 align="center">Preview (Shows Captured Image)</h5>
<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SimpleCamScreenShots/portrait_Preview.png?raw=true" width=320></img> 
</p>

<h5 align="center">Preview - Rotated (Maintains Captured Image Ratio)</h5>
<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SimpleCamScreenShots/portrait_RotatedPreview.png?raw=true" width=568></img> 
</p>


###Landscape

<h5 align="center">Camera (About To Capture)</h5>
<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SimpleCamScreenShots/landscape_Camera.png?raw=true" width=568></img> 
</p>

<h5 align="center">Preview (Shows Captured Image)</h5>
<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SimpleCamScreenShots/landscape_Preview.png?raw=true" width=568></img> 
</p>

<h5 align="center">Preview - Rotated (Maintains Captured Image Ratio)</h5>
<p align="center">
  <img src="https://github.com/LoganWright/SimpleCamDemo/blob/master/SimpleCamDemo/SimpleCamScreenShots/landscape_RotatedPreview.png?raw=true" width=320></img> 
</p>
