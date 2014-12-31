# SlidingUpPanel Issue

Source: https://github.com/umano/AndroidSlidingUpPanel

This sample highlights an issue when using an EditText within the main content view (second child) of SlidingUpPanel layout. The EditText is expected to be repositioned above the soft keyboard when the keyboard appears. The behavior works as expected when the MainActivity is first launched. However, once interaction with the draggable view has occurred, the EditText's position will never be updated.

Notes:
* The activity's `windowSoftInputMode` is set to `stateHidden|adjustResize`. `adjustResize` is desired as to not hide the draggable view and toolbar when the keyboard is shown (as `adjustPan` would do).
* `adjustPan` behaves as expected both before and after interacting with the draggable view.
* An unrelated issue that was discovered in this sample is that only the EditText at the bottom of the activity fades when the draggable view is pulled down. Version 2.0.2 does not have this issue.