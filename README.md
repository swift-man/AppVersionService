# AppVersionService

![Badge](https://img.shields.io/badge/swift-white.svg?style=flat-square&logo=Swift)
![Badge](https://img.shields.io/badge/SwiftUI-001b87.svg?style=flat-square&logo=Swift&logoColor=black)
![Badge - Version](https://img.shields.io/badge/Version-0.5.0-1177AA?style=flat-square)
![Badge - Swift Package Manager](https://img.shields.io/badge/SPM-compatible-orange?style=flat-square)
![Badge - Platform](https://img.shields.io/badge/platform-mac_12|ios_15-yellow?style=flat-square)
![Badge - License](https://img.shields.io/badge/license-MIT-black?style=flat-square)  

---

## Google Firebase
### [FirebaseRemoteConfig](https://github.com/firebase/firebase-ios-sdk) Async/await wrapper.

## API Call
```swift
let appVersionService = AppVersionFetchService(keyStore: AppVersionServiceKeyStore())
let result = try await appVersionInteractor.fetchAppVersion()
```

### API Response
```swift
public enum ResultAppVersion: Equatable {
  case success
  case forcedUpdateRequired(message: String, appstoreURL: URL)
  case optionalUpdateRequired(message: String, appstoreURL: URL)
}
```

### API Error
```swift
public enum AppVersionServiceError: Error {
  case invalidAppStoreURLString
  case notFoundAppStoreURLString
  case notFoundForceAppVersionKey
  case notFoundOptionalUpdateVersionKey
  case notFoundReleaseVersionNumber
  case unknown
}
```

## Default Keys
![Image](https://drive.google.com/uc?export=view&id=1LJdPX5TecGYyOypU5sRXAe6-1O17aYAg)  

```swift
appStoreURLKey = "appStoreURLString"
forceAppVersionKey = "iosForceAppVersion" // (Optional Value)
forceUpdateMessageKey = "forceUpdateMessage" // (Optional Key, Value)
optionalUpdateMessageKey = "optionalUpdateMessage" // (Optional Key, Value)
optionalUpdateVersionKey = "iosOptionalUpdateVersion" // (Optional Value)
```

### Your Custom Keys
```swift
let keyStore = AppVersionServiceKeyStore(appStoreURLKey: #YourCustomKey#, ...)
let service = AppVersionFetchService(keyStore: keyStore))
```


## Installation
### Swift Package Manager

The [Swift Package Manager](https://swift.org/package-manager/) is a tool for automating the distribution of Swift code and is integrated into the `swift` compiler. 

Once you have your Swift package set up, adding Alamofire as a dependency is as easy as adding it to the `dependencies` value of your `Package.swift`.

```swift
dependencies: [
    .package(url: "https://github.com/swift-man/AppVersionService.git", .from: "0.5.0")
]
```

## Example Presentation Layer
[LaunchingView](https://github.com/swift-man/LaunchingView) - SwiftUI
