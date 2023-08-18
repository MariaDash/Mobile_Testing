# Basic Guidelines
## 1. System font - San Francisco is of high priority
## 2. Units -Points (pt)
1 point= 1 pixel

![point](https://github.com/MariaDash/Mobile_Testing/blob/main/point.PNG)

## 3. Screen size (most popular)
320 px x 568 px (iPhone 5)

## 4. Shadows and gradients in the interface
Not used. Emphasising only on information
## 5. Navigation:
### Bottom Navigation:

+ iOS has only one button - button "Home" that opens Home Screen
+ Button "Back" usually implemented in applications in the top left corner.

### Top-level  navigation:
+ Tab bar (in the bottom of screen)
### Additional navigation
+ "More" Tab
+ Additional actions in top left or right corners
### Top Navigation
+ Navigation Bar
Left action always do "Back" step.
Title exists and has big font, it becomes smaller when scrolling screen.

## 6. Search
+ To cancel search you need to tap "Cancel" button in the top right corner.
+ Search can be an icon. Icon can spread out into full screen open component.
+ When search is essential component it is displayed firstly.
## 7. CTA button
+ Button is usually located in the top right corner but sometimes it is located in the bottom bar or in the bottom right corner.
## 8. Full screen usage without any frames.
## 9. If you have any transparent parts in the application you should make somewhat visible the area under this transparent part.
## 10. You should have different logical work zones separated with contract  background colors for better usability.
## 11. Interactive elements (icons, controls, etc.) should be standalone , separated by a unique color.
## 12. Icons should be without frames, vector pictures.
## 13. You should avoid "Start" button or simular on launch. Application should start  all by itself with no  actions from user's side.
## 14. You should avoid registration in the application.
## 15. You should not implement onboarding in the application. Instead ypu should create more understandable intuitive UI. 
+ If it is not possible to delete onboarding you should  enable onboarding skipping.
+ If onboarding exists it shoud show only basics.
## 16. Portrait or landscape orientation ( for smartfons or iPads respectively) by default.
## 17. Do not include User Agreement or sumulsr stuff in the application. Instead include it to app store and open it in downloading flow.
## 18. If user relaunching the application from recents apps it should save all the user previous data in cache and not miss it.
## 19. Application shouldn't have "Close" button. It should be closed by tapping 'home' button, or 'back' button, or when opening another application.
## 20. Application should not be closed automatically. It should provide appropriate message to the user describing the error occured and also propose user to do some actions to fix the problem (for example restart internet connection) or to close the application by himself.