# <p align="center">![icon_transparent.png](OpenParsec/Assets.xcassets/IconTransparent.imageset/icon_transparent.png) ![OpenParsec](OpenParsec/Assets.xcassets/LogoShadow.imageset/logo_shadow.png)</p>

OpenParsec is a simple, open-source Parsec client for iOS/iPadOS written in Swift using the SwiftUI framework and the Parsec SDK.

This project is still a major WIP, so apologies for the currently lackluster documentation. I'm also very new to both Swift and SwiftUI so I'm sure there are many places for improvement.

Before building, make sure you have the Parsec SDK framework symlinked or copied to the `Frameworks` folder. Builds were tested on Xcode Version 12.5.

## Downloads
<a href="https://stikstore.app/altdirect/?url=https://github.com/hugeBlack/OpenParsec/releases/download/nightly/altstore.json" target="_blank">
   <img src="https://raw.githubusercontent.com/StikStore/altdirect/refs/heads/main/assets/png/AltSource_Blue.png" alt="Add AltSource" width="200">
</a>
<a href="https://github.com/hugeBlack/OpenParsec/releases/download/nightly/OpenParsec.ipa" target="_blank">
   <img src="https://raw.githubusercontent.com/StikStore/altdirect/refs/heads/main/assets/png/Download_Blue.png" alt="Download .ipa" width="200">
</a>

## Touch Control
You can set the touch mode you want to use in settings. Touchpad mode and direct touch mode are supported.

When streaming, you can tap with 3 fingers to bring up the on-screen keyboard.

You can toggle if you want to use 2 fingers to scroll or zoom in the overlay menu.

## Mouse & keyboard
USB mouse & keyboard are supported. 

## Apple Vision Pro compatibility preview

The existing iPad target includes a headset input path for visionOS 26.1 or later. Pair a physical Vision Pro with Xcode, enable Developer Mode, and choose the Vision Pro **Designed for iPad** destination for the `OpenParsec` scheme. Use automatic development signing and your own bundle identifier. Xcode 27.2 requires an iOS deployment target of at least 15.0. [Apple’s pairing instructions](https://developer.apple.com/documentation/xcode/pairing-your-devices-with-your-mac)

During a stream, use **Show Controls** to open the keyboard, switch between fit and zoom, send a shortcut, or disconnect. **Click** uses the tap location, **Right Click** applies to one tap, and **Drag**, **Scroll**, and **Precision** change how a pinch-drag behaves. Select **Click** to exit a mode. Precision uses the current remote cursor as its starting point. Software keyboard text is limited to characters supported by the existing remote key mapping.

The signed iPad build has been installed on physical iPad hardware. The Vision Pro simulator rejected the x86_64 build and the bundled SDK has no arm64 simulator slice. Physical headset testing is pending. Use a dedicated test account and a host you control to verify both hands-only and Bluetooth input, window resizing, a 30-minute stream, and recovery after sleep or network loss. Record the headset OS, host OS, accessories, and any shortcuts intercepted by the system.

## Game Controllers
When streaming, press any trigger button in your controller and parsec will recognize it. Make sure to configure the host properly (install virtual USB driver etc.) before using game controllers.

## Lag / Low Bitrate Issue
If you encounter lags from nowhere or your bitrate hardly goes over 10 Mbps, download Steam Link and do a network test. If you see constant lag spike in the graph, then it's a problem with Apple and there's little we can do to solve this problem. See [here](https://github.com/moonlight-stream/moonlight-ios/issues/627) for more disscussion. 

If you can't change your wireless router's channel to 149 like me, my personal experience is that you can try to power off the device you are using to stream as well as any nearby Apple devices, especially Mac, then only power on the device you are using to stream and do the aforementioned network test again. You can turn on other devices if the lag spike is gone and it may sustain for couple hours or days.
