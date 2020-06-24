# AcknowList

Acknowledgements screen displaying a list of licences, for example from [CocoaPods](https://cocoapods.org) dependencies.

![Platform iOS](https://img.shields.io/cocoapods/p/AcknowList.svg)
![Swift 5](https://img.shields.io/badge/Swift-5-blue.svg)
[![Build Status](https://travis-ci.org/vtourraine/AcknowList.svg?branch=master)](https://travis-ci.org/vtourraine/AcknowList)
![Swift Package Manager](https://img.shields.io/badge/support-Swift_Package_Manager-orange.svg)
[![CocoaPods compatible](https://img.shields.io/cocoapods/v/AcknowList.svg)](https://cocoapods.org/pods/AcknowList)
[![MIT license](http://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/vtourraine/AcknowList/raw/master/LICENSE)

_Also available in Objective-C with [VTAcknowledgementsViewController](https://github.com/vtourraine/VTAcknowledgementsViewController)._

<img alt="iPhone screenshot 1" src="https://vtourraine.github.io/VTAcknowledgementsViewController/screenshots/iPhone-X-01.png" width="300px"> <img alt="iPhone screenshot 2" src="https://vtourraine.github.io/VTAcknowledgementsViewController/screenshots/iPhone-X-02.png" width="300px">

## Features

- Automatically load acknowledgments from CocoaPods-generated file
- Remove unnecessary line breaks from licences for better text wrapping
- Optional list header and footer
- Tappable links in header, footer, and acknowledgment text
- Storyboard support
- Dark Mode support
- Dynamic Type support, with automatic font adjustment
- Localized in 13 languages
- Swift Package Manager support

## How to Install

CocoaPods is the most common solution to install this library.

1. Add `pod 'AcknowList'` to your `Podfile`.
2. Run `pod install`.
3. Add the `Pods-#target#-acknowledgements.plist` file generated by CocoaPods in `Pods/Target Support Files/Pods-#target#/` to your main target (drag and drop the file in your Xcode project). Don’t copy the file, leave `Copy items if needed` unchecked.

## Initialization

The `AcknowListViewController` instance is usually pushed to an existing `UINavigationController`.

``` swift
let viewController = AcknowListViewController()
navigationController.pushViewController(viewController, animated: true)
```

By default, the controller will try to guess the name of your `.plist` file, based on the bundle name (`Pods-#bundle-name#-acknowledgements.plist`). If that doesn’t match the file you’re looking for, you can initialize the view controller with a custom file name or path.

``` swift
let viewController = AcknowListViewController(fileNamed: "Pods-AcknowExample-acknowledgements")
```

``` swift
let path = Bundle.main.path(forResource: "Pods-AcknowExample-acknowledgements", ofType: "plist")
let viewController = AcknowListViewController(acknowledgementsPlistPath: path)
```

## Customization

If you need to include licenses that are not part of the generated `plist` file, or if you don’t want to use the generated `plist` at all, you can easily create new `Acknow` instances, and set them as the acknowledgements array of the controller.

``` swift
let customLicense = Acknow(title: "...", text: "...")
viewController.acknowledgements = [customLicense]
```

The controller can also display a header and a footer. By default, they are loaded from the generated `plist` file, but you can also directly change the properties values.

``` swift
viewController.headerText = "We love open source software."
viewController.footerText = "Powered by CocoaPods.org"
```

The controller title is a localized value for “acknowledgements”. You might want to use this localized value for the button presenting the controller.

``` swift
button.setTitle(AcknowLocalization.localizedTitle(), for: .normal)
```

If you need to further customize the appearance or behavior of this pod, feel free to subclass its classes.

## Apple TV

AcknowList is also compatible with tvOS for Apple TV apps.

<img alt="Apple TV screenshot 1" src="https://user-images.githubusercontent.com/886053/37403710-07901b2e-2790-11e8-975f-b779fcfc3fbe.png" width="300px"> <img alt="Apple TV screenshot 2" src="https://user-images.githubusercontent.com/886053/37403711-07c83d38-2790-11e8-9f2e-84fe2d5f6bad.png" width="300px">

## Requirements

AcknowList is written in Swift 5, requires iOS 8.0 or tvOS 9.0 and above, Xcode 11 and above.

## Credits

AcknowList was created by [Vincent Tourraine](http://www.vtourraine.net), and improved by a growing [list of contributors](https://github.com/vtourraine/AcknowList/contributors).

## License

AcknowList is available under the MIT license. See the `LICENSE.txt` file for more info.
