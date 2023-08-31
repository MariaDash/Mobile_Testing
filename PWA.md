# PWA
PWA architecture

PWA is a web application created using certain technologies to achieve given targets.
Target indicators are deciphered as follows:

Reliable - the application is loaded and displayed immediately, regardless of the status and quality of the network connection.
Speed (Fast) - the exchange of data over the network is fast, the UI is smooth and responsive.
Attractiveness (Engaging) - makes the experience of working with the application comfortable and enjoyable for the user, encouraging him to want to experience it again, and again, and again ...

From Google's point of view, this is what now separates the look and feel (look and feel) of websites from native applications.

In other words, the developer is offered tools (Service Worker, Push Notifications, etc.) and goals are indicated (the site / application must be fast to load, work on a weak connection, not “lag”, work offline if necessary). How far the developer will advance along this path depends only on him.

PWA and native apps

The fact that PWAs are similar in appearance to native applications is rather a cosmetic decision (although it is important for the user from a psychological point of view). But the fact that they are similar internally (all the main resources of the application can be stored on the client, only changing content will be transmitted over the network) is a huge achievement.

One might even call it a hidden revolution. In fact, the browser is used as a kind of virtual machine that stores and launches the PWA application in itself. Just like Android is a virtual machine for android apps, the browser becomes a virtual machine for PWA. As a native application accesses its resources through the file system, PWA also accesses its resources - albeit via HTTP, but stored locally.

And for once, it all works the same on all major browsers and on all major platforms.

Google attacks iOS

Of course, there are differences between PWA and native applications - mainly in access rights to system resources, but work in this direction is going on even in the field of pure HTML5, and for PWA additional privileges will not be a problem.

APK vs PWA


Technologies

Let's take a quick look at the main drivers of PWA.

Service Worker

The heart of PWA is the Service Worker. This is a proxy layer between the frontend and backend, located in the browser. All browser requests go through it. This division into two independent layers made it possible to make the transition of a regular website to PWA as simple as possible.

From storage, Service Worker has access to Cache Storage for web resources, and IndexDB for data. But, most importantly, complete freedom to implement business logic.

You can, for example, accept a request from the browser, check the network status, take data from the storage, perform operations with them and return some result back to the browser - which will think that the answer came from the server. Or it won’t be - as the developer wants, he will do it. Two browser layers (client frontend and Service Worker) allow you to write full-fledged applications.

At the same time, for most sites, the caching functionality of the Service Worker will be enough to turn into a PWA.

PWA does not depend on any frameworks, it is pure javascript, although even Google experts on Habré for some reason advise using library code generators. Service Worker is beautifully written by hand, and this is necessary in order to understand and control the logic of your application well.

From a programmer's point of view, Service Worker is a javascript file that is included in the html code of the page. In it, the developer defines the logic for working with requests coming from the frontend and other functionality.

HTTPS

PWA requires all site resources to be transferred over HTTPS. You can get an SSL certificate for free, some hosts do it for you. But it is critical that the site does not contain links to insecure resources - some browsers simply will not display the site in this case.

The main problem encountered in such cases is pictures. Often editors or commentators put links to pictures from the Internet in the material, sometimes they automatically get there (into the material). You need to save the pictures either to yourself or to a service with access via HTTPS.

Application Shell

App shell is just a GUI skeleton, a template. For example, let's take an average site with a header, two columns and more. Roughly speaking, we cut out the content of the current page and all dynamic information from it, the remaining static is the app shell.

The bottom line is that the app shell is stored on the client and loaded when the application starts, and then dynamic information is loaded into it from the network. And while it is loading, the app shell should look nice ("loaders" in place, etc.)

This site architecture - loading content and other dynamic information through ajax calls - can be thought out and implemented on the site in advance, then the transition to PWA will be quite simple.

App shell is like a native program shell.
An app shell is like a shell for a native program. Think of your PWA as a native program and things will become easier.

web app manifest

JSON file that declaratively defines the name of the application for the browser, the icon, how the PWA will look (fullscreen, standalone, etc.) and some other parameters. Allows you to "install" PWA as a standalone application on your smartphone's home screen.

Push Notifications

If you surf the web with Chrome DevTools open in the Application tab, you can see how few sites use PWA technology. And 90% of those who use it do it just for the sake of Push Notifications.

So far, this is the most popular and most abused PWA technology - over the past few months, the number of sites where you first look for the “Block” button with the mouse on an offer to receive the latest news has grown, such a feeling, many times over, and the very desire to impose your own Push is similar to Spam.

But you can also offer a subscription to the second or third visit of the user to the site, when it is already clear that he is not here by chance.
Thanks for the content to https://habr.com/ru/articles/418923/
