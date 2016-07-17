---
layout: post
title: Transitioning to AVPlayerViewController from MPMoviePlayerViewController
published: false
---

MPMoviePlayerViewController was deprecated in iOS 9. With iOS10 looming, in the near distant future, now seems a good time to tackle this deprecation head on.

It's recommended to replace it with something from AVKit or AVFoundation. There is two obvious options: 

1. AVPlayerViewController - This comes bundled with  controls for seeking backward, forward, & pausing. It is adequate for most needs and it encapsulates an AVPlayer.

```swift
let playerViewController = AVPlayerViewController()

playerViewController.player = AVPlayer(playerItem:AVPlayerItem(itemWithURL:NSURL(string: "https://www.youtube.com/never-gonna-give-you-up.mp4")!))

presentViewController(playerViewController, animated: true)

playerViewController.play()
```

2. AVPlayer - this allows for more freedom, it is your responsibility to setup the controls and customisations. With great power comes great responsibility!


# Dismissing the video player when the video finishes
AVPlayerItemDidPlayToEndTimeNotification is sent when an AVPlayerItem finishes.

By listening for this notification, we can dismiss the video when it has finished.



