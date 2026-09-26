# Repository Guide

- This Swift package exports the `Model3DView` library from `Sources/Model3DView/`; tests are in `Tests/Model3DViewTests/`.
- `Package.swift` declares Swift tools 5.5 and macOS 11/iOS 14/tvOS 14 minimums. Use `swift test` for package changes.
- Test success does not establish rendering quality for a glTF asset; inspect affected models in a supported SwiftUI host when visual behavior changes.

Run commands at the root on macOS with an Apple Swift/Xcode SDK toolchain supporting the manifest; this package imports SwiftUI and SceneKit and is not a portable Linux Swift library. Swift Package Manager resolves GLTFSceneKit and DisplayLink using `Package.resolved`; preserve those dependency choices unless the task changes them.

The current test file contains only an empty `testExample`, so `swift test` is presently compile/load evidence, not rendering or behavior coverage. Add focused assertions for changed testable logic, then inspect the affected asset/camera/loading behavior in a supported host when applicable. Preserve the public SwiftUI API and unrelated work, and report actual checks plus any unavailable host/rendering validation.
