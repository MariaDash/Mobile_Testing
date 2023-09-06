# Event
Event is a signal from the app that something has happened. 
Here is a list of the most commonly used DOM events, just for reference:

## Mouse events:

+ `click` - occurs when an element is clicked with the left mouse button (on devices with touch screens, it occurs on touch).
+ `contextmenu` - occurs when an element is right-clicked.
+ `mouseover / mouseout` - when the mouse moves over / leaves the element.
+ `mousedown / mouseup` - when the mouse button was pressed / released on the element.
+ `mousemove` - when moving the mouse.
## Events on controls:

+ `submit` - The user has submitted the form <form>.
+ `focus` - The user focuses on the element, such as clicking on an <input>.
## Keyboard events:

+ `keydown and keyup` - when the user presses/releases a key.
## Document events:

`DOMContentLoaded` - When the HTML is loaded and rendered, the DOM of the document is fully built and available.
## CSS events:

`transitionend` - when the CSS animation is complete.

## Event handlers
An event can be assigned a handler, that is, a function that will work as soon as the event occurs.

# Action





A user only provides actions (pressing on buttons, making selections in dialogs etc.)

These actions get [sometimes] converted into events by the underlying framework. Events can be understood, conceptually, as [notification] "messages" sent to methods which have, implicitly or explicitly, "registered" with the underlying framework to be notified [for a specific type of event]. In reality the framework merely invoke these methods with the appropriate arguments, and such an invocation is effectively an event.

The word event is also used to designate a particular type of events. For example one speaks of the "Change" event or "Submit" event of a given edit box or other UI element. In this sense the event is not a particular instance of an opportunity for the underlying method to be called, but rather the generic set of conditions which warrant the method to be invoked.

The user therefore doesn't really "submit a message" as phrased in the question, he/she takes some actions upon various UI elements, and these action [may] result in the fact that the framework detects a particular event type (or several). The framework then looks-up which methods are currently registered to receive the corresponding notifications, and the framework then invokes these methods, passing the proper arguments (which constitute a "message" of sorts for use by the method).

The main idea behind this model is for the application-level to provide the specific logic to handle events but not worry about following the system and user's every "move". The framework does this, and can be trusted to notify the relevant event handlers would a particular user action (or system condition such as a timer reaching its set time, a network packet being received etc. etc.) warrant such notification.
