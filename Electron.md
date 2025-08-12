You have IPC, which acts as the *websocket* between the *node* based `main.js`
and your *chromium* based `renderer.js` files...

# main vs renderer processes
you can view on the **electron docs** whether it is main, renderer or *shared* (both)

# app (the most important module)
you control App's even lifecycle

*ready()* fires as soon as your app launches.
*before-quit* is another *lifecycle* event that will happen right as you *quit* the application.


You must be careful with *cross-platform* specifc stuff!

# Debugging
Node will make a web socket connection with the *chromium* browser.

1. run any port above 1,023
	> electron --inspect=5858         # app will run as usual
2. go to `chrome://devices` (or 'edge' or 'safari')
3. go to the *devices* tab
4. click on configure and add *localHost* of which you are debugging as *target*

Now you can inspect the app when it pops up and add *break* points





