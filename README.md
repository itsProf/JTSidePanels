# JTSidePanels
Reveal side view controllers with pure Swift code on iOS. JTSidePanels is a UIViewController container designed for presenting a center panel with revealable side panels - one to the left and one to the right. This is a Swift port of the amazing JASidePanels project found at https://github.com/gotosleep/JASidePanels/.

Usage
---

The only file required to use JTSidePanels: ` JTSidePanelController.swift `

The easiest way to use JTSidePanels is to copy the files into your Xcode project.

Alternatively, you can setup a git submodule and reference the files in your Xcode project. I prefer this method as it enables you to receive bug fixes/updates for the project.
` git submodule add https://github.com/itsProf/JTSidePanels.git JTSidePanels `

I'm also working on making this available through CocoaPods.

Example using Storyboards
---

1. Create a subclass of `JTSidePanelController`. In this example we call it `BaseViewController`.
2. In the Storyboard designate the root view's owner as `BaseViewController`.
3. Add more view controllers to your Storyboard, and give them identifiers `leftViewController`, `centerViewController` and `rightViewController`. Note that in Xcode the identifier is called "Storyboard ID" and can be found in the Identity inspector.
5. Add the `awakeFromNib` method to `BaseViewController.swift` with the following code:

```swift
override func awakeFromNib() {
    super.awakeFromNib()
    
    leftPanel = storyboard?.instantiateViewControllerWithIdentifier("leftViewController")
    centerPanel = storyboard?.instantiateViewControllerWithIdentifier("centerViewController")
    rightPanel = storyboard?.instantiateViewControllerWithIdentifier("rightViewController")
}
```

If you only need a left or a right panel, you can set only the one you need.

License
---

``` 
The MIT License (MIT)

Copyright (c) 2015 Jorge Tapia

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
