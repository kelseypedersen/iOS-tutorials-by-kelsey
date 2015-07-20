## Swipe Gestures

1. Drag and drop Swipe Gesture Recognizer (from the attributes panel) to the view you want to be able to swipe.
2. Control drag from the Swipe Gesture Recognizer on the drop of the view in the storyboard (two to the right of the yellow viewController button) to the viewController.m file in implementation.
3. Add logic to switch between faceup and not faceup in viewController.m.

```
- (IBAction)swipe:(UISwipeGestureRecognizer *)sender {
    self.playingCardView.faceUp = !self.playingCardView.faceUp;
}
```
