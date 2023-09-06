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

## Events and Actions

## Use
Most UI elements (e.g. the Button UI element) can react to a user's interaction (e.g. clicking on the corresponding pushbutton). This reaction can trigger a handling method to be called within the view controller.

Events are used to communicate between controllers and enable one controller to trigger event handlers in a different controller. Cross-component communication can be implemented using the interface controller's events. Events that were created in the component controller are visible within the component only.

## Action

Actions are runtime objects that associate a client-side event with a server-side response. When you create an action object, the system automatically creates an action handler method. You link the event, the UI element is equipped with, with the appropriate action object.

If a UI element has been inserted several times into a view, you can equip their events with different actions as necessary. The event is then processed by the corresponding event handler depending on the action that is linked.

Actions can also be reused within a view. This means that an action can be linked to the events of several (or even different) UI elements. In this manner, it is possible to write a single, generic action event handler method that can respond to a variety of events raised by multiple UI elements.

## Note
A view controller should be written such that it is only ever a consumer of data, never a generator. This means that view controllers should never contain coding to interact with a back end system.

## Recommended Action Architecture:

+ Once control has been passed to the action event handler method in the view controller, this method should delegate all interaction with the back-end system to a non-visual controller.

+ Hence the call to a method happens to live in the component controller. This method then interacts with the back-end system via the model object.

+ The data returned from the model object is passed from the component controller to the view controller through the technique of context mapping.

## Inbound Plug Events

Inbound plugs in a view also react like an event. Therefore, when a view is called using an inbound plug, the event handler that is optionally available for the inbound plug is always called first. In this case event handling takes place within the current view controller, however.

The same applies for the inbound plugs of an interface view. In the corresponding window controller, an event handler is created. It can then be programmed further, as appropriate.

-----

A user only provides actions (pressing on buttons, making selections in dialogs etc.)

These actions get [sometimes] converted into events by the underlying framework. Events can be understood, conceptually, as [notification] "messages" sent to methods which have, implicitly or explicitly, "registered" with the underlying framework to be notified [for a specific type of event]. In reality the framework merely invoke these methods with the appropriate arguments, and such an invocation is effectively an event.

The word event is also used to designate a particular type of events. For example one speaks of the "Change" event or "Submit" event of a given edit box or other UI element. In this sense the event is not a particular instance of an opportunity for the underlying method to be called, but rather the generic set of conditions which warrant the method to be invoked.

The user therefore doesn't really "submit a message" as phrased in the question, he/she takes some actions upon various UI elements, and these action [may] result in the fact that the framework detects a particular event type (or several). The framework then looks-up which methods are currently registered to receive the corresponding notifications, and the framework then invokes these methods, passing the proper arguments (which constitute a "message" of sorts for use by the method).

The main idea behind this model is for the application-level to provide the specific logic to handle events but not worry about following the system and user's every "move". The framework does this, and can be trusted to notify the relevant event handlers would a particular user action (or system condition such as a timer reaching its set time, a network packet being received etc. etc.) warrant such notification.
