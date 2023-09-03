# Android Glossary https://developer.android.com/design/ui/mobile
## 1. Activities
In Android, an activity includes an app's UI and the actions it makes available to users. An app is a collection of activities that are created and reused from other apps. 
## 2. CTA
Call to action, the primary goal you want your user to achieve. For example, Subscribe could be a CTA for letting a user to sign into a service.
## 3. Canonical layout
Commonly used design compositions that help layouts adapt for common use cases and screen sizes.
## 4. Chroma
The colorfulness of a color, ranging from neutral gray to full vibrancy.
## 5. Containment
The concept of visual grouping to create boundaries with use of white space or visible elements.
## 6. Density-independent pixels (dp)
Flexible units that scale to have uniform dimensions on any screen. They are based on the physical density of the screen. These units are relative to a 160 dpi (dots per inch) screen, on which 1 dp is roughly equal to 1 px.
## 7. Display cutout
An area on some devices that extends into the display surface to provide space for front-facing sensors.
## 8. Hue
The perception of color, or how you would describe the color.
## 9. Intents
An intent allows an app to signal it needs another app's assistance in performing an action; for example, a messaging app can use the Share intent to share a photo from the Photos app with a contact. Apps can indicate which intents to respond to through activities. Android provides flows and UI for a number of intents. 
## 10. Navigation bar
An Android system bar displayed at the bottom of the screen. It allows the user to navigate a device through either a gesture or tapping a button.
## 11. Scalable pixels (sp)
Scalable pixels serve the same function as dp, but for fonts. The default value of an sp is the same as the default value for a dp. The Android system calculates the actual font size to use based on the device and the user's preference set in the Settings app of their Android-powered device.
## 12. Status bar
An Android system bar displayed at the top of the screen. It contains notification icons and system icons.
## 13. Tasks
A sequence of activities a user follows to accomplish a goal. These activities are arranged in a stack, known as the back stack, in the order in which each activity is opened. Learn more about the back stack lifecycle.
## 14. Tone
The luminance, or brightness, of a color. Describes the level of light that a digital color value represents.

# Basic guidelines:
## 1. System font - Roboto
## 2. Units 
Density independent pixels (dp) and scalable pixels (sp) are essential for building layouts and presenting fonts that respond uniformly to the wide range of screen densities, size classes, form factors, and aspect ratios that make up Android devices.
+ If using a baseline grid, stick to measurements of 4 and 8.
+ Notate specs in dp and sp, instead of pixels.
+ Export bitmap/raster graphics for all buckets.
+ Design with a responsive mindset with different size classes, resolutions, and aspect ratios in mind.
+ Density-independent pixels (dp): density-independent pixels are flexible units that scale to have uniform dimensions on any screen. They are based on the physical density of the screen. These units are relative to a 160 dpi (dots per inch) screen, on which 1 dp is roughly equal to 1 px.
+ Scalable pixels (sp): Scalable pixels serve the same function as dp, but for fonts. The default value of an sp is the same as the default value for a dp. The Android system calculates the actual font size to use based on the device and the user's preference set in the Settings app of their Android device.

![dp](https://github.com/MariaDash/Mobile_Testing/blob/main/grids-and-units-2-density-buckets.png)

To calculate dp:

dp = (width in pixels * 160) / screen density

## 3. Screen resolution (most popular)
360 px x 640 px

## 4. Shadows in the interface
Used from 0 dp to 24 dp. Elements got their volume because of the shadows.
Material is a metafor in a "Material Design". 
All in this design-system is inspired by the physical? i mean real world with its textures and surfaces includind the fact that light has reflections and objects have shadows. "Material" rethinks the idea of paper and inks. 
## 5. Navigation 
### Bottom Navigation:
+ Navigation bar

Android lets users control navigation using `back`, `home`, and `overview` controls:

+ Back returns directly back to the previous view.
+ Home transitions out of the app and to the device's home screen.
+ Overview shows the apps are open and have recently been opened.
Users can choose from various navigation bar configurations including gesture navigation (recommended) and three-button navigation.

### Top-level Navigation:
+ Bottom Navigation Bar
+ Tabs
### Additional navigation
+ "Hamburger" button opens side menu "Navigation Drawer"
### Top Navigation
+ Top App Bar
Title is aligned to the left, located near "hamburger" menu or near "back" button. It is not changed in size while scrolling the screen.
## 6. Search
+ To cancel search you need to tap "Back" button.
+ Search can be an icon. Icon can be opened in Top App Bar.
+ When search is essential component it is displayed firstly.

## 7. CTA button
+ Button is usually located in the bottom right corner.

## More about Navigation:
### System bars
Together, the status bar and the navigation bar are called the system bars. They display important information such as battery level, the time, and notification alerts, and provide direct device interaction from anywhere. Keep system bars at the top of most layers to ensure they're accounted for.
System bars should be included in app designs and be or transparent or simular color towards the app.
### Status bar
On Android, the status bar contains notification icons and system icons. The user interacts with the status bar by pulling it down to access the notification shade. The status bar can appear differently depending on the context, time of day, user-set preferences or themes, and other parameters. You can also set the status bar style, as in the following examples.
### Set the status bar style
Style the status bar background as a part of your app theme, with a custom color or style, along with setting transparency and opacity.
### Navigation bar
Android lets users control navigation using back, home, and overview controls:

+ Back returns directly back to the previous view.
+ Home transitions out of the app and to the device's home screen.
+ Overview shows the apps are open and have recently been opened.
Users can choose from various navigation bar configurations including gesture navigation (recommended) and three-button navigation.
### Gesture navigation
Introduced in Android 10 (API level 29), gesture navigation is the recommended type of navigation, although you can't override the user's preference. Gesture navigation doesn't use buttons for back, home, and overview, instead showing a single gesture handle for affordance. Users interact by swiping from the left or right edge of the screen to go back and forward and up from the bottom to go home. Swiping up and holding opens the overview.

Gesture navigation is a more scalable navigation pattern for designing across mobile and larger screens. To provide the best user experience, account for gesture navigation by:

+ Supporting edge-to-edge content.
+  Avoid adding interactions or touch targets under gesture navigation insets.



## 8. Colors
+ To ensure accessibility:
    + Check color contrast and avoid pairing colors with similar tones.
    + Consider that red and green are common patterns, but also that they're not accessible to users with certain kinds of color blindness.
+ Practice using colors meaningfully: Apps can be vibrant and expressive, but stick to a palette of colors. Extending your scheme with too many semantic colors can be confusing, while having too many decorative colors can be overwhelming.
+ Colors can have patterns, so repeat established color patterns. If using semantic colors in your app, use consistent colors.
+ To allow your app to work well in different contexts, build a light and dark color scheme (and ideally contrast themes).
+ Assign colors with tokens to indicate the element's color role, instead of using a hardcoded value.
+ Colors can come from various dynamic and static sources, but avoid mixing too many within the same view.
+ When using dynamic content color, try to avoid pulling colors from multiple content pieces.

### UI color consists of accent, semantic, and surface colors.

+ Accent colors refer to core colors that are typically part of the Android brand color palette.
+ Semantic colors (or custom colors within Material 3), are colors with specific meaning.
+ Surface colors refer to any neutral derived colors used for background colors.

## 9. Themes
A theme is a set of styles or attributes such as color, type, and shape, which can affect the look and feel of a user's mobile or large-screen device and in-app experience.

### Types of themes
+ Themes are system-based or app-based. System themes can affect the user's entire device UI and provide corresponding controls in device settings, while an app theme affects only the app in which it's implemented.

+ Your app must implement either type of theme to display it, but app themes apply only within the app and not elsewhere on the device. You can also override some system theme settings with in-app settings.

### System themes
System themes apply across an entire Android device, including individual apps depending on user settings. System themes include light and dark themes, user-generated themes, and manufacturer themes.

### Light and dark themes
+ Light theme, or Day mode, consists of a bright display mode with higher luminance and surfaces built from high tonal values. Conversely, the dark theme, or Night mode, shifts the UI to reduce luminance. Surfaces are built from dark grays or low tonal values.

+ Dark theme has multiple benefits: helping with screen legibility in sunny or low light conditions, reducing eye strain due to lower brightness, and conserving battery. Also, it's often the most requested app feature amongst users.
### User-generated themes

User-generated themes are supported by dynamic color, which we made available with Material You starting in Android 12. When enabled, dynamic color derives custom colors from a user's wallpaper to be applied to their apps and system UI. This color palette is used as the starting point to generate light and dark color schemes.

Font settings can also be updated within device settings to meet the user's preferences and accessibility needs. These settings can and should carry into apps, so make sure to utilize scalable pixel values for fonts.

### Manufacturer themes

Device manufacturers may provide additional proprietary theming capabilities that can affect system UI and display settings.

## App themes
### Baseline
The Material components in the Material library provide a baseline theme that uses a purple color scheme and Roboto font. Any app that doesn't define theme attributes reverts to these baseline attributes.

### Custom (brand)
Using custom themes gives you a greater range of expression for your app's look and feel, or to act as a fallback when certain system themes are not available. This is useful whether you're working with a full custom design system, a small brand guide, or a few of your favorite colors.

Your app can also have multiple custom schemes, whether full schemes a user can choose from, content inspired, or sub-branded elements.

## 10. Layout
A layout defines the visual structure for a user to interface with your app, such as in an activity. Android provides a range of libraries, canonical starting points, and techniques to display and position content.
+ Keep essential interactions, like primary navigation, in a reachable screen area.
+ Use containment to group related content to guide the user through content and actions.
+ Provide consistent alignment between similar content and UI elements.
### Parts of a typical Android app screen
+ System bars
The status bar and navigation bar collectively known as the system bars display important information such as battery level, the time, and notification alerts, and provide direct device interaction from anywhere. Read more about system bars.

System bars are an integral part of the device interface. Add them as a top layer of your designs to ensure they're accounted for within the screen layout. Otherwise, users might mistakenly assume the intent is to hide them, you miss out on styling them, and spacing can end up being off.

Add the bars as a top layer. 
+ Navigation region
Navigation represents the different affordances that allow a user to navigate within your app, access important actions, or across the Android platform.
+ Body region
The body region holds the screen content. Body content is composed of additional groupings and layout parameters. It must continue under navigation and system bar regions.
## 11. Grids
+ Baseline grid

Building with an underlying grid helps create consistent spacing and alignment across your UI. Android UI utilizes an 8 dp grid for layout, components, and spacing.
+ Column grid
Columns build a grid structure to provide vertical definition to a layout by dividing content within the body area. Content is placed in the areas of the screen that contain columns. Align with an underlying grid to align content, but should keep flexible sizing. 
+ Size classes
Window size classes are a set of opinionated viewport breakpoints that help you design, develop, and test responsive and adaptive application layouts. Android breaks window size classes into 3: Compact, Medium, and Expanded.
+ Aspect ratios
An aspect ratio is the proportion of an element's width to its height. Aspect ratios are written as width:height.
1. To maintain consistency in your layout, use a consistent aspect ratio on elements like images, surfaces, and screen size.
2. The following aspect ratios are recommended for use across your UI:

+ 16:9
+ 3:2
+ 4:3
+ 1:1
+ 3:4
+ 2:3
## 12. Immersive content
You can use immersive mode to hide the system bars for a full-screen experience. This is useful for enabling users to enjoy a fully immersive experience for video, games, images, and books, and to avoid accidental exits during a game.
+ Provide an intuitive way for users to display UI–for example, tapping on the screen during video playback displays video playback controls and system bars.

+ Never permanently hide system bars on personal devices. You cannot permanently hide system bars in your app unless for an Android Enterprise deployment, so your designs should account for them to provide the optimal experience. Read more about designing for system bars.

+ Provide an overlay or scrim for overlaying text and controls.

+ Combine immersive mode with other features, such as picture-in-picture (PiP) and Chromecast, to continue the experience.

+ Immersive mode causes users to lose easy access to system navigation, so use it only when the benefit to the user experience goes beyond simply using extra screen space.

+ Fullscreen experiences aren't appropriate for all content. Consider when to help a user avoid accidental exits from frequent taps, like a game, or have an uninterrupted view to enjoy videos or books.
## 13. Components
### Action components
+ Action components help people achieve an aim.
+ Material has multiple types of buttons to help define priority of actions and interaction in different contexts. From FABs or extended FABs for primary actions to supporting icon buttons to selecting options with segmented buttons.
### Communcation components
Communication components provide helpful information, by alerting users with badges, informing of status through progress indicators, and providing brief process messages with snackbars.
### Containment components
Containment components hold information and actions – including other components like buttons, menus, or chips. Most Material components use explicit containment, grouping together related content and actions with visual objects: cards, dialogs, bottom sheets, side sheets, carousels, and tooltips. Lists can be provided with implicit containment or explicit by showing visible dividers. These components provide common patterns for displaying groups of content.
### Navigation components
Navigation components help people move through the UI. For mobile, the navigation bar or navigation drawer contain your primary navigation destinations. Tabs, the bottom app bar, and the top app bar provide different ways to navigate supporting information and actions. 
### Selection components
Selection components let people specify choices. Whether building out a form with checkboxes and radio buttons, filtering using chips, or toggling settings with switches and sliders, selection components allow users to control and input their decisions.
### Text input components
Text input components let people enter and edit text. Text fields allow users to enter text into a UI.
## 14. Predictive back design
redictive back is the result of a gesture navigation operation in which a user has swiped back to preview their destination of the back gesture before fully completing it. This lets the user decide whether to continue—in other words, to "commit" to the back gesture or stay in the current view.

Predictive back provides a smoother, more intuitive navigation experience while using gesture navigation. It leverages built-in animations to inform users where their actions will take them to reduce unexpected outcomes.

Use the design guidance on this page if your app design calls for providing back navigation for custom transitions and animations for key moments. For most apps, you don't need to implement custom back navigation because built-in predictive back animations show the user where they will go.
## 15. User authentication with passkeys
Passkeys are a safer and more convenient replacement for passwords. With passkeys, users can sign in to apps and websites using biometrics (such as a fingerprint or facial recognition), PIN, or pattern. This provides a seamless sign-in experience, freeing your users from having to remember usernames or passwords.

+ Introduce passkeys at the right moment to help users stay engaged and adopt this new sign-in method.
+ Make passkeys the default option to help users adopt the simplest and safest sign-in method.
+ Keep information about passkeys consistent throughout the product to help users learn about passkeys.
+ Use the passkey icon to create a consistent understanding and login experience.
+ Use the Credential Manager API to implement passkeys in your app.
+ Use Credential Manager API to consolidate sign in options (passkeys, passwords and federated sign-in solutions). There is no need to list out all sign in options up front.
+ Give your users an opportunity to create a passkey after sign-in with a password or other options.
## 16. Notifications
Notifications provide brief, timely, and relevant information related to your app when it's not in use.

The Android OS controls many aspects of notifications, but you have control over other aspects. Follow these steps when implementing notifications:
+ Understand the anatomy of a notification.
+ Choose the type of notification for your use case.
+ Set the notification category that aligns with the type of notification you've chosen
## 17. Picture-in-picture (PiP)
 is a type of multi-window mode intended for activities that play full-screen video. It lets the user watch a video in a small window pinned to a corner of the screen while navigating between apps or browsing content on the main screen.
 ## 18. Split screen mode
 Working with two applications at a time on divided screen.
