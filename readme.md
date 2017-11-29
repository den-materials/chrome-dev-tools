<!--
Creator: Ilias Tsangaris
Market: SF
Edited: John Barela 
Market: Den
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

<!--WDI6 2:45 -->

# Chrome Dev Tools

## Why is this important?
*This workshop will enable developers to:*

- Build client-side applications more quickly and with less frustration
- Practice and test out JavaScript in the console
- Affect changes to webpages in real-time, allowing for faster change iterations

## What are the objectives?
*After this workshop, developers will be able to:*

- Open and describe the components of the Chrome developer tools
- Use the developer tools to manipulate page elements (HTML/CSS)

## Where should we be now?
*Before this workshop, developers should already be able to:*

- Use Chrome
- Write basic HTML
- Write basic JavaScript

## Dev Tools Intro 

Most modern browsers include a set of tools that allow developers to monitor and explore what's going on in a web page. The Chrome Developer Tools, which are often called the "Dev Tools", are essential knowledge for every web developer.

We can do a lot of useful things with these tools, but some of the things that are most useful:

- We can view the HTML & CSS as the browser has understood them
- We can watch requests and responses as they are made and received
- We can observe JavaScript being run
- We can debug issues with our code
- We can issue JavaScript commands on a console, or browser command line

Having such a powerful set of browser tools at our disposal is incredibly valuable, and you should get into the habit of using them to their full potential.

## DevTools Demo (5 min)

First, let's navigate to [http://generalassemb.ly](http://generalassemb.ly).

Now to access the DevTools, we can press:

- `⌘ + ⌥ + i` to open the DevTools (to the most recent tab used)

If you forget this command, you can go to *View > Developer > Developer Tools* or right click on the page and select *Inspect*, but try to memorize the keyboard shortcut.

#### DevTools Tabs

Overall, there are eight main tools available in the Developer Tools. You may see people with a few more as you can add custom ones using extensions.

<!--This is not accurate anymore, we need to fix it -->

- [**Elements**](https://developer.chrome.com/devtools/docs/dom-and-styles): Inspect and edit the HTML & CSS of the DOM (Document Object Model)
- [**Console**](https://developer.chrome.com/devtools/docs/console): Run JavaScript in the browser
- [**Network**](https://developer.chrome.com/devtools/docs/network): Evaluate network performance (refresh to see it in action)
- [**Resources**](https://developer.chrome.com/devtools/docs/resource-panel): Manage application storage
- **Sources**: A graphical interface to the V8 debugger
- [**Timeline**](https://developer.chrome.com/devtools/docs/timeline): Evaluate page load performance (refresh to see it in action)
- [**Profiles**](https://developer.chrome.com/devtools/docs/profiles): Identify optimizations in the performance of an app or webpage.
- **Audits**: The Audit panel can analyze a page as it loads.

The key ones to focus on are:

- **Elements**
- **Console**
- **Network**

## Elements Tab (10 min)

![elements-tab](./imgs/elements-tab.png)

Inspect and edit the HTML & CSS of the [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction), which is structured like a [tree](https://en.wikipedia.org/wiki/Tree_(data_structure)). In this view we can see a representation of the DOM as interpreted by the browser.

**Selecting**

Target a specific element to inspect or edit:

- In the top-left corner of the elements tab there is an icon that looks like a mouse pointer inside of a box—click on it and then click any element you want to inspect.

    *or*

- Right-click any element you want to inspect and then click the option "Inspect" in the menu

**Inspecting**

*Note: The `elements` tab has additional tabs. We will use the `styles` tab to view and edit all styles, but we can also use the `computed` tab to look at only the styles being applied to an element.*

Inspect the styles applied to an element:

* See the styles for any page or element *exactly* as the browser has interpreted all of the CSS styles collectively.

* Access a visual representation of the box model along with a set of the computed values.
    * Since CSS loads styles sequentially, it's possible for a rule in one stylesheet to be overwritten by another that was loaded subsequently. That's what's happening when you see a style rule that is crossed out.


**Editing**

Delete elements:

- Select an element in the elements tab, such as the `body`, and delete it by pressing the `Delete` button, and then undo it by pressing `⌘ + z`

Copy & paste elements:

- Copy & paste elements with `⌘ + c` & `⌘ + v`

Change text:

- Select an element that contains text in the elements tab, and double click the text inside of it to edit; when you click back outside of the element the changes will reflect on the page

Change values:

- Use up/down arrow to increment/decrement any value by one (try it with font-size or padding)
- Use `⌥ + ↑` or `⌥ + ↓` to increment/decrement by 0.1
- Use `SHIFT + ↑` or `SHIFT + ↓`to increment/decrement by 10

Anything else:

- Edit the raw HTML content by *right-clicking* and choosing "Edit as HTML" (clicking outside of the text-edit box will save the changes, while using the `esc` key will erase them).


**Styling** 

Choose the perfect color:

- Notice that as you start defining a CSS `property` such as `background` with a `value` such as `red` the browser will try to autocomplete
    - If Chrome recognized the color you typed, you will also see a colored box appear next to the color `value`
- Press `SHIFT` and click on the colored box to toggle through color format: rgb, hex, hsl, etc
- Click on the colored box to choose a more specific color
- Click onto the page to see a color selector and grab a color already on the page

<!--WDI6 3:06 -->

## Exercise: 15 Minutes of Fame (only 10 mins of time to complete ☹) 

For modifying and editing your HTML & CSS, the dev tools has made it super easy to quickly test and edit these changes before incorporating them into your application. On the [New York Times](http://www.nytimes.com/) complete the following challenges.

Using the tips above, change:

* the lead headline to "Anonymous and WDI Take Down North Korea"
* the lead photo to a picture the happiest kitten you can find
* the `body`'s background to your favorite color
* Add a `margin-top` of 10px to the `main` element (that also has `id` and `class` `main`) and increment it up to 20px using the arrow keys

The goal is get you comfortable editing and manipulating the DOM. This skill will be essential in every one of your projects.

<!--WDI6 3:15 -->

## Network Tab (15 min)

![network-tab](./imgs/network-tab.png)

The Network panel records information about each network operation in your application, including detailed timing data, HTTP request and response headers, cookies, WebSocket data, and more.

- Refresh the page and have a look at the requests being made by the page
  - Notice that the status of a lot of the resources are **304** (not modified)
- Momentarily check 'Disable Cache' so the requests are processed as new each time we ask for a resource from the server
  - Refresh the page, and you should see that everything is now **200** (ok)

#### Meaning of HTTP Status Codes

* 1xx — Informational
* 2xx — Success
* 3xx — Redirection
* 4xx — Client Error
* 5xx — Server Error

For more information on status codes you can reference [HTTP Cat](https://http.cat/) or the much better [HTTP Status Dogs](https://httpstatusdogs.com/).

[Comment]: # (Talk a bit about 400 vs 500 and consistent status codes.)

#### Filtering

By default, the network Tab shows all requests being made. However, you can filter these requests by:

- All
- XHR Requests
- Script
- Style
- Images
- Media
- Fonts
- Documents
- WebSockets
- Other

You can also search through these requests, which can be useful.

## Console Tab (10 min)

Lastly, let's have a look at the console tab (you can use the shortcut – `⌘ + ⌥ + j` to navigate directly to it).

The JavaScript Console provides two primary functions for developers testing web pages and applications. It is a place to:

- Write JavaScript that interacts with the DOM and browser
- Log diagnostic information in the development process using the [Console API](https://developer.chrome.com/devtools/docs/console-api)


When we write JavaScript that we intend to be processed in a browser, we can use commands like `console.log()` to log values from our Javascript straight to this tab, as the code executes. It's the next best thing to setting a breakpoint when we're debugging; we'll talk about this strategy later in the debugging lesson.  

#### Console Shell

The console shell also allows us to execute Javascript and interact with the DOM using Javascript, just like we would from a JavaScript file that we load with the page.

Let's try this:

```
> var a = 1;
> var b = 1;
< undefined

> a + b
< 2
```

<!--WDI6 3:23 -->

## Independent Practice (30 min)

Take a look at this screenshot:

![screenshot](https://i.imgur.com/5ruzGhc.png)

Using the Chrome dev tools, try to recreate this screenshot on [Google.com](http://www.google.com).

No pressure, this is meant to be exploratory!  You'll have to dig through some HTML elements and their CSS to make this work.

Keep in mind if you refresh the page you **will** lose all your work.

The General Assembly large logo can be sourced from the [General Assembly homepage](https://generalassemb.ly/) and the smaller logo, in the search bar, will have to be found through Google.  

## Closing Thoughts

Knowledge of the Dev Tools is *necessary* for developing client-side applications. It illustrates what's happening **"behind the scenes"** and allows for developers to **experiment** with change. This tool inevitably leads to a better workflow and **greater productivity**.

## Additional Resources

* Learn more about the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* Memorize the dev tool [keyboard shortcuts](https://developer.chrome.com/devtools/docs/shortcuts)
* Explore the [Window API](https://developer.mozilla.org/en-US/docs/Web/API/Window); the window object represents the window containing the DOM.

<!--Wdi6 3:50 -->

## Licensing
All content is licensed under a CC­BY­NC­SA 4.0 license.
All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.
