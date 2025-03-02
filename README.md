# Video Player

## Meta Introduction to iOS Development Course

### Overview
This project is a simple iOS application that demonstrates how to implement video playback functionality in iOS using AVKit and AVFoundation frameworks. The app automatically plays a video titled "Introducing Meta" when launched.

### Features
- Automatic video playback on app launch
- Implementation of AVKit for video playback
- Integration with AVPlayerViewController for a native video player experience

### Technical Implementation
The application uses the following key components:
- **AVKit**: Framework for presenting and managing media playback
- **AVFoundation**: Framework for working with audio-visual media
- **AVPlayer**: Core class for managing the playback of a media asset
- **AVPlayerViewController**: View controller that presents the playback controls for an AVPlayer object

### Project Structure
- `ViewController.swift`: Contains the main implementation of the video player functionality
- `Introducing Meta.mp4`: Video resource file that is played by the application

### Code Explanation
The main functionality is implemented in the `ViewController` class:
1. The `viewDidAppear(_:)` method triggers the video playback when the view appears
2. The `playVideo()` method:
   - Locates the video file in the app bundle
   - Creates an AVPlayer instance with the video URL
   - Configures an AVPlayerViewController with the player
   - Presents the player view controller
   - Starts the video playback

```swift
private func playVideo() {
    guard let path = Bundle.main.path(forResource: "Introducing Meta", ofType: "mp4") else {
        debugPrint("Could not find video")
        return
    }
    let player = AVPlayer(url: URL(fileURLWithPath: path))
    let playerController = AVPlayerViewController()
    playerController.player = player
    present(playerController, animated: true) {
        player.play()
    }
}
```

### Requirements
- iOS 15.0+
- Xcode 13.0+
- Swift 5.5+

### Setup Instructions
1. Clone or download the repository
2. Open the `video_player.xcodeproj` file in Xcode
3. Ensure the "Introducing Meta.mp4" video file is included in the project resources
4. Build and run the application on a simulator or physical device

### Learning Objectives
This project demonstrates:
- How to integrate video playback in an iOS application
- Using AVKit and AVFoundation frameworks
- Implementing a native video player experience
- Working with media resources in an iOS app bundle

### Troubleshooting
- If the video doesn't play, ensure the "Introducing Meta.mp4" file is properly added to the project and included in the app bundle
- Check that the resource name and extension in the code match the actual file name and extension

### Additional Resources
- [AVKit Documentation](https://developer.apple.com/documentation/avkit)
- [AVFoundation Documentation](https://developer.apple.com/documentation/avfoundation)
- [AVPlayer Documentation](https://developer.apple.com/documentation/avfoundation/avplayer)
- [AVPlayerViewController Documentation](https://developer.apple.com/documentation/avkit/avplayerviewcontroller)

### License
This project is part of the Meta Introduction to iOS Development Course. 
