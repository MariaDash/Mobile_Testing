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



According to the MVC paradigm, the data model and the views must be decoupled: this philosophy has been respected on the whole product. Between model and view, a controller should be included, in order to manage operations to apply on the views and to listen to events coming from the views. Actions in 4WS.Platform represent the controller: they are invoked by events fired by views (a grid, a form, a tree, a column, a control, a filter control, a tree node, a button) and they perform a presentation logic on the GUI or a business logic on the server side. Actions have a format:
JavaScript– in this case the code will be executed on the GUI
SQL – in this case the code will be run on the server side; it can include more than one SQL statement, separated by ";"
Web service – the web service is expressed as an URL which can include variables (:VARNAME); this web service will be always called on the server layer, so there will not be any limit related the host to invoke.
By means of actions, it is possible to enhance and customize the standard behavior of grids, forms, trees and the other components, by injecting custom code invoked by specific events.
Events and actions work closely: an event provides inputs that an action can use and evaluate; output from actions can represent a feedback for events and can influence the way the component behaves after the event completion. So, for example, it is possible to prevent the data saving when pressing the save button in a grid, using an action linked to a "before saving on insert" event.
It is also possible to create a chain of actions to execute in sequence, starting from a single event: through the action detail form, it is possible to define an optional action to perform at the end of the current one. In case of server-side javascript actions, it is also possible to define an action to concatenate before the current action: in this way, a unique action composed of these two is execute on the server side. This feature allows to reuse code defined on the server by multiple actions, in a similar way to classes linked to a inheritance relationship: a base action can contain reusable code, expressed as declaration of functions, whereas other classes can invoke that code, if they inherit the base action, by declaring it as the class to execute before.
