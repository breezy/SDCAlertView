# CHANGELOG

# 2.3.0

**What's New:**
- Improved semantics for alert action styles. See the discussion in #81 for more information.

**Bug Fixes:**
- Fixes an animation issue in `SDCAlertView` on iOS 7 (#79)
- The warning introduced in 2.2 is removed

# 2.2.0

**Bug Fixes:**
- Fixes an incompatibility issue that would not correctly fetch text fields on iOS 7 (#67)

# 2.1.1

**Bug Fixes:**
- Fixes an off-by-one error that breaks compatibility with iOS 7 (#70)

# 2.1

**What's New:**
- The `usesLegacyAlert` property is now made public

**Bug Fixes:**
- Updates the import in SDCAlertController.h to not depend on any precompiled headers
- Fixes several issues with the legacy alert (#62, #63, #64, #68)
- Improves upon `UIAlertController` so that when an alert button is quickly tapped, it will highlight (`UIAlertController` does not do this)
- Fixes Auto Layout warnings for multi-line labels (#60)
- Returns the correct text when accessing `titleLabel.text`

# 2.0.1

**Bug Fixes:**
- Raises an exception when presenting SDCAlertView 1.0 from a `UIAlertView` or `UIActionSheet` (#56 - thanks @nschum)
- Prevents a crash when creating an alert with a `nil` title or message

# 2.0

**What's New:**
- All new API that matches and extends `UIAlertController`
- Ability to always show buttons horizontally or vertically
- Backwards compatible with `SDCAlertView` (1.0)
- More stylistic elements you can style (alert width, button separators, text fields, etc.)

## 1.4.3

**Bug Fixes:**
- Fixes an issue that would not enforce `contentPadding` on the title and message labels properly (#58)

## 1.4.2

**What's New:**
- Extra properties to specify padding and spacing in the alert (#55 - thanks @bcherry)

## 1.4.1

**Bug Fixes:**
- Show the button top separator in an alert without title or message text (#40)
- Initialization is written a little differently to be more subclass-friendly
- Ready for use in iOS 8

Though the alert can still be used in iOS 8, keep in mind that the actual iOS 8 alert looks slightly different. The plan is to eventually have support for both, but that's currently not the case.

## 1.4

**What's New:**
- Added the ability to position a two-button alert vertically as opposed to horizontally (#29)
- Added `attributedTitle` and `attributedMessage` properties (#30)

**Bug Fixes:**
- Auto-layout doesn't complain anymore when using `[[SDCAlertView alloc] init]`
- Fixes a bug that would not show correct button titles in certain alert configurations (#32)
- Instead of clipping button text, it now reduces the size of text on buttons appropriately (#33)

## 1.3

**What's New:**
- The `SDCAlertViewTransitioning` protocol allows users to customize alert transitions and behavior
- `SDCAlertView` now supports `tintColor` for buttons and `contentView`

**Bug Fixes:**
- Fixes an issue where the status bar style would not be preserved if it was set to `UIStatusBarStyleLightContent` (#26 & #27)
- Fixes a bug that causes the app to lock up due to a race condition (#28)
- Adding subviews to `contentView` won't have any animation-related side effects anymore (see #25)

## 1.2.1

**Bug Fixes:**
- Resolves an issue that could put an app in a bad state when transitioning to and from multiple alerts in rapid succession.

## 1.2

**What's New:**
- New convenience methods for showing alerts more easily
- The `SDCAlertViewWidth` constant is made public (#24)
- The `contentView` does not require vertical constraints anymore, though they can be used to size the `contentView` other than "hug its subviews" (#23)

**Bug Fixes:**
- Resolves an issue that would show the status bar if it was previously hidden (#21)
- Resolves an issue that would sometimes return the wrong button index when using `addButtonWithTitle:` (c4af94542253e211bebcb17e9a9dc898a284a209)
- Transitions between alerts flow more logically if you call several show or dismiss methods right after each other (#25)
- The `animated` argument in `dismissWithClickedButtonIndex:animated:` is honored again (1bfa04903ffae880a377b3d97ddfed72ad7ff413)

## 1.1

**What's New:**
Support for styling an alert. A number of properties have been exposed so that alerts can be easily given a different style. Styling all alerts in an app using `UIAppearance` is also supported.

**Bug Fixes:**
- The alert's background is no longer using the toolbar hack (#16 & #17—thanks @clstroud!)
- Accessing a text field before calling `show` does not cause a crash anymore (#14)
- The color of text on a button color did not match `UIAlertView`'s text color 100%
- A disabled button will have its label's `enabled` property set to `NO`, which is also where it gets its gray color from
- A 1px hairline at the bottom of the right button in a two-button alert was removed

## 1.0

This release marks the first official release of SDCAlertView.

SDCAlertView's behavior should now match UIAlertView's. Any behavior that's different from UIAlertView and is not documented as a "won't fix" or known bug is considered a bug that needs to be solved.

## 0.9

Initial release