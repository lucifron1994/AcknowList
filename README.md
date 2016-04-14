# AcknowList

_Ready to use “Acknowledgements”/“Licenses”/“Credits” view controller for [CocoaPods](http://cocoapods.org/)._

_Written in Swift 2.2 (for Objective-C, you can use [VTAcknowledgementsViewController](https://github.com/vtourraine/VTAcknowledgementsViewController))._


![Platform iOS](https://img.shields.io/badge/platform-iOS-blue.svg)
[![Build Status](https://travis-ci.org/vtourraine/AcknowList.svg?branch=master)](https://travis-ci.org/vtourraine/AcknowList)
[![CocoaPods compatible](https://img.shields.io/cocoapods/v/AcknowList.svg)](https://cocoapods.org/pods/AcknowList)
[![MIT license](http://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/vtourraine/AcknowList/raw/master/LICENSE)

![iPhone screenshot 1](http://vtourraine.github.io/VTAcknowledgementsViewController/screenshots/iPhone-300-01.png)
![iPhone screenshot 2](http://vtourraine.github.io/VTAcknowledgementsViewController/screenshots/iPhone-300-02.png)


## How to Install

This project is only useful if you use CocoaPods, so let’s assume that you’re indeed using CocoaPods.

1. Add `pod 'AcknowList'` in your `Podfile`.
2. Import the `Pods-acknowledgements.plist` file from the generated `Pods/Target Support Files` folder to your main app project (so you need to run `pod install` at least once before using this pod; don’t copy the file itself, just add a reference).  
This file is generated at `Pods/Target Support Files/Pods-{project}/Pods-{project}-acknowledgements.plist`.  


## How to Use

The `AcknowListViewController` instance is usually pushed to an existing `UINavigationController`.

``` swift
let viewController = AcknowListViewController()
if let navigationController = self.navigationController {
  navigationController.pushViewController(viewController, animated: true)
}
```


## Customization

If your `.plist` file is named something other than `Pods-acknowledgements.plist` (_e.g._ if you’re using fancy build targets), you can initialize the view controller with a custom path.

``` swift
let path = NSBundle.mainBundle().pathForResource("Pods-AcknowExample-acknowledgements", ofType: "plist")
let viewController = AcknowListViewController(acknowledgementsPlistPath: path)
```


## Requirements

AcknowList is written in Swift 2.2, requires iOS 8.0 and above, Xcode 7.3 and above, and uses ARC.


## Credits

AcknowList was created by [Vincent Tourraine](http://www.vtourraine.net), and improved by a growing [list of contributors](https://github.com/vtourraine/AcknowList/contributors).


## License

AcknowList is available under the MIT license. See the LICENSE file for more info.
