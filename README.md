# TwUI 0.1.0

TwUI 是一个具备硬件加速能力的 UI 框架，受到 UIKit 的启发，供 OS X 桌面开发使用。它具备：

* 由 CoreAnimation 提供的 GPU 硬件渲染能力。
* 简易的 MVC 开发模式。

它和 UIKit 的不同

* 简化的 Table View 单元。
* 块桩布局和 drawRect。
* 统一的坐标系 (以左下为原点)。
* 次像素文字渲染。

# 安装

To use the current development version, include all the files in your project and import TUIKit.h. Set your target to link to the ApplicationServices and QuartzCore frameworks.  Be sure to add NS_BUILD_32_LIKE_64 to your preprocessor flags.

# Usage

Your TUIView-based view hierarchy is hosted inside an TUINSView, which is the bridge between AppKit and TwUI.  You may set a TUINSView as the content view of your window, if you'd like to build your whole UI with TwUI.  Or you may opt to have a few smaller TUINSViews, using TwUI just where it makes sense and continue to use AppKit everywhere else.

# Example Project

An included example project shows off the basic construction of a pure TwUI-based app.  A TUINSView is added as the content view of the window, and some TUIView-based views are hosted in that.  It includes a table view, and a tab bar (which is a good example of how you might build your own custom controls).

# Status

TwUI should be considered an alpha project.  It is current shipping in Twitter for Mac, in use 24/7 by many, many users and has proven itself very stable.  The code still has a few Twitter-for-Mac-isms that should be refactored and cleaned up.

This project follows the [SemVer](http://semver.org/) standard. The API may change in backwards-incompatible ways before the 1.0 release.

The goal of TwUI is to build a high-quality UI framework designed specifically for the Mac.  Much inspiration comes from UIKit, but diverging to try new things (i.e. block-based layout and drawRect), and to optimize for Mac-specific interactions is encouraged.

# Known limitations

There are many places where TwUI could be improved:

* Accessibility.  It would be great to bridge the AppKit accessibility APIs to something simpler, again, inspired by UIKit.

* Text editing.  TUITextEditor is a simple text editor (built on TUITextRenderer).  It provides basic editing support and handles a number of standard keybindings.  Fleshing this out to be indistinguishable from NSTextView (read: spellchecking, autocorrect) would be useful.  If the logic around this were self-contained it would even be great as a standalone project, useful for anyone looking to build a custom text editor for the Mac.

* Reverse-hosting.  Right now TUIViews may be hosted inside of an existing NSView hierarchy.  It would be useful if the reverse were possible, adding NSViews inside of TUIViews.  Doing so in a robust way so event routing, the responder chain, and CAAnimations all just work is a challenge.

# Documentation

You can generate documentation with [doxygen](http://www.doxygen.org). Install it, and then run:
> cd docs
> doxygen

Documentation is a work in progress, but the API will be familiar if you have used UIKit.  (TODO: [appledoc](http://www.gentlebytes.com/home/appledocapp/) looks very cool, moving to that might be nice).

TwUI has a mailing list, subscribe by sending an email to <twui@librelist.com>.

# Copyright and License

Copyright 2011 Twitter, Inc.

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this work except in compliance with the License.
   You may obtain a copy of the License in the LICENSE file, or at:

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
