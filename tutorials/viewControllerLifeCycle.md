## Summary of the viewController Lifecycle

### Opening the app
1. Instantiated (from the storyboard or elsewhere - many options)
2. awakeFromNib
3. Outlets set
4. viewDidLoad
5. When geometry is determined... viewWillLayoutSubviews & viewDidLayoutSubviews

### Changing (appearing and disappearing) MVC screens
6. viewWillAppear & viewDidAppear
7. When geometry changes... viewWillLayoutSubviews & viewDidLayoutSubviews
8. viewWillDisappear & viewDidDisappear

### If memory gets low
9. didReceiveMemoryWarning