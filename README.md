# Swift and macOS tips

## About CoreMediaIO and ScreenCaptureKit

CoreMediaIO Camera Extensions are a great addition to macOS.
In addition, ScreenCaptureKit allows capturing several windows at 60 FPS without overloading the CPU.
These 2 technologies are made for Screegle! https://www.appblit.com/screegle

Here I'll post macOS and Swift tips I've learned while developing my side-project Screegle.

I published a free sample app showing how to use a sink and source streams [cameraextension](https://github.com/ldenoue/cameraextension)
The sink is then fed CMSampleBuffers from the app, allowing you to show arbitrary content from your app to your camera.

Screegle, published on the App Store, uses this technique now and the CPU usage is ~10% while sharing several windows simultaneously.

### Contact

Find me on [Twitter](https://twitter.com/ldenoue) and I’ll help you.
