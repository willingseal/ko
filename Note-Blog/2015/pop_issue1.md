# iResign内容


bundle id: `com.hishop.willtestpush`
 
iResign使用流程
####准备工作
1. 企业账号的 `******.mobileprovision` 文件, `In house`类型, (自己在后台创建的, 而不是用xcode自动生成的)

2. 常规dev方式打的`ipa`包

3. 复制`key chain`name, 如 `iPhone Distribution:*** co.ltd`

4. 点击`重新签名!`
 
 
 
 
 
Met the same problem.

And solved with changing to `if(1)` here. 

`iReSignAppDelegate.m`


	if (1)
	// if (identifierOK)
	{
	    NSLog(@"Provisioning completed.");
	    [statusLabel setStringValue:@"Provisioning completed"];
	    [self doEntitlementsFixing];
	} else {
	    [self showAlertOfKind:NSCriticalAlertStyle WithTitle:@"Error" AndMessage:@"Product identifiers don't match"];
	    [self enableControls];
	    [statusLabel setStringValue:@"Ready"];
	}


 

# github 上面的老内容
Here I add one `kPOPScrollViewContentOffset` animation to `UIScrollview` as follows:

    POPBasicAnimation *scaleAnimation = [POPBasicAnimation animationWithPropertyNamed:kPOPScrollViewContentOffset];
    scaleAnimation.timingFunction = [CAMediaTimingFunction functionWithName:kCAMediaTimingFunctionLinear];
    scaleAnimation.fromValue = aFromValue;
    scaleAnimation.toValue = aToValue;
    scaleAnimation.autoreverses = YES;
    scaleAnimation.repeatForever = YES;
    scaleAnimation.duration = timeLength;
    [topScrollView pop_addAnimation:scaleAnimation forKey:@"OffsetAnimation"];
            
But when I scroll this UIScrollview with my finger, there is no response.
In UIView animation, there is a option called: `UIViewAnimationOptionAllowUserInteraction` that allow user action while animating.

So is there a way to allow my scroll action during an POPBasicAnimation?
ps:I have stackoverflowed, nothing useful founded.


    - (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView
	// called on finger up if the user dragged. velocity is in points/millisecond. targetContentOffset may be changed to adjust where the scroll view comes to rest
	{
    	TJScrollView *topScrollView = [self getCurrentScrollView];
    	if (scrollView == topScrollView)
    	{
      	  [topScrollView pop_removeAllAnimations];
    	}
	}
	

Done!

Steps:

### 1: `Clone` and add `WebP.framework`

 clone the repository using `git clone --recursive https://github.com/rs/SDWebImage.git`
 
 add full folder of `SDWebImage` and `WebP.framework` into your project.
 
![image](http://ww1.sinaimg.cn/large/6aa39725gw1er421z43rmj209h0izq54.jpg)




###2: in `Build Settings` -- `Preprocessor Macros` , add `SD_WEBP=1`.

![image](http://ww2.sinaimg.cn/large/6aa39725gw1er421hkyq0j20ld09ujsy.jpg)


ps:If using `CocoaPods`, I don't konw how to add `WebP.framework` into `SDWebImage`, so I choose add files into my project.





	[aActionIV sd_setImageWithURL:tryURL
          	     placeholderImage:holderImg
                          options:SDWebImageRetryFailed | SDWebImageLowPriority
                         progress:^(NSInteger receivedSize, NSInteger expectedSize)
         {
             if (expectedSize > 0)
             {
                 float progress = receivedSize / (float)expectedSize;
                 [loadingIndicator setProgress:MAX(MIN(1, progress), 0) animated:YES];
             }
         }
                            completed:^(UIImage *image, NSError *error, SDImageCacheType cacheType, NSURL *imageURL)
         {
             [loadingIndicator removeFromSuperview];
             
             if (error)
             {
                 NSLog(@"%@", error);
             }
             else
             {
             }
         }];
         
         
I have some UIImageView that using `sd_setImageWithURL` to load images.
But after `pod update` SDWebImage to `3.7.2`, sometimes one UIImageView will show wrong image that belongs to other URL. 
Just like two UIImageView exchange their images.  And when I change SDWebImage to `3.7.1`, everything is OK.
So weird!
Now the question, 
Is there a BUG that sd_setImageWithURL completed with a wrong image? 





How to get multi images like phhhoto?

I am trying to make multi images with AVFoundation.

And facing some questions as follows:

1:To get multi images, which way is better? 

A: use `AVCaptureStillImageOutput` to get one still image, then another.

But I found this way will stuck the main thread(UI thread).

B: Use `AVCaptureVideoDataOutput` to get a short video, then get images from this video.

But when I set `self.device = [AVCaptureDevice defaultDeviceWithMediaType:AVMediaTypeVideo];` , the camera 

seems like viedoing, not imaging.


So, How to get multi images like phhhoto?

Any tip will be useful for me.

Many thanks in advance.










Why `sd_imageWithWebPData:` cost too much time?

In file `UIImage+WebP.h`, 

function: `+ (UIImage *)sd_imageWithWebPData:(NSData *)data`

	if (WebPDecode(data.bytes, data.length, &config) != VP8_STATUS_OK) {
        return nil;
    }

My image size is  600*4000 in `webp`, filesize is about 200k.

But when reading from dis cache, `WebPDecode` cost almost 1.5s-2.0s.

Is this normal?

Thanks for any tips.





       