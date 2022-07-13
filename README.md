# Development notes for my iOS and macOS apps

Hi! I make iPhone and macOS apps at [www.appblit.com](https://www.appblit.com) and am writing here about the technologies used to make them happen.
Some are for work, some for education (kids, K12 like PopMath and PopSpell).

## Screegle with CoreMediaIO Camera Extensions and ScreenCaptureKit

CoreMediaIO Camera Extensions are a great addition to macOS.
In addition, ScreenCaptureKit allows capturing several windows at 60 FPS without overloading the CPU.
These 2 technologies are made for Screegle! https://www.appblit.com/screegle

Here I'll post macOS and Swift tips I've learned while developing my side-project Screegle.

I published a free sample app showing how to use a sink and source streams [cameraextension](https://github.com/ldenoue/cameraextension)
The sink is then fed CMSampleBuffers from the app, allowing you to show arbitrary content from your app to your camera.

Screegle, published on the App Store, uses this technique now and the CPU usage is ~10% while sharing several windows simultaneously.

## PDFReflow: Reading PDFs on a small screen

This is perhaps the most advanced tech I developed for my apps (along with Screegle).
PDFReflow images PDF images and cuts them out into pieces to visually reflow them to fit your iPhone's screen.
It lets you read any PDF (well, when it works!) without having to zoom or pan around.
Of course, because it's using good-old heuristics, it doesn't always work.
Page segmentation is still an active research area: not surprisingly, modern approaches use deep learning to identify areas on each page (text, figures, captions, etc.).
For now, PDFReflow uses heuristics: it looks at text bounding boxes (if found in the PDF), binarizes the images to compute the connected components, applies a famous page layout algorithm called XYCut.
It then reflows the page by cutting each identified word into a tiny image, or leaves images as is (as one block).


## ReaderView: a reader mode for Safari that works on many web sites

I really like the "Reader Mode" that comes with Mobile Safari, but it doesn't work on all web sites, and you can't personalize the articles with highlights, or save them for later.
So ReaderView was born! I uses heuristics to identify articles and lets you swipe or select paragraphs to highlight them. It also saves images locally, so when you open the main app, you have access to your articles along with images.

## PopSpell and SpriteKit

SpriteKit is an awesome framework to build 2D games, so I had to try it.
My previous kids apps (PopMath, PopGeo, etc.) used UIKit to move sprites (UIButtons, really!) on the screen.
But PopSpell uses SpriteKit, along with special effect like particles when you swipe through the letters.
Check it out [PopSpell](https://www.appblit.com/popspell)

### Contact

Find me on [Twitter](https://twitter.com/ldenoue) and I’ll help you.
