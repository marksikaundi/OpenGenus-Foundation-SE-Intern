# OpenGenus-Foundation-SE-Intern(2Months)
- Different ways to detect if JavaScript is disabled in a browser
There are several ways to detect if JavaScript is disabled in a browser: And below is my explaination
There are several ways to detect if JavaScript is disabled in a browser: And below is my explaination
1. **Noscript tag:** This method uses the ``<noscript>`` tag in HTML to display a message when JavaScript is not enabled. The message is shown to users who have disabled JavaScript in their browser or have a browser that does not support JavaScript.
```
<noscript>
<p>Please enable JavaScript to use this website.</p>
</noscript>
```
2. **Document.write method**: Another way to detect if JavaScript is disabled is to use the ``document.write()`` method to write a message to the page. This method is used when the page loads and if JavaScript is not enabled, the message will be displayed.
```
<script>
  document.write("Please enable JavaScript to use this website.");
</script>
```
3. **Modernizr library:** Modernizr is a JavaScript library that detects the features available in a user's browser. By using this library, you can detect if JavaScript is enabled or not.
```
if (Modernizr.js) {
  // JavaScript is enabled
} else {
  // JavaScript is disabled
}
```
4. **Navigator object:** The ``navigator`` object in JavaScript provides information about the user's browser. The ``navigator`` object has a property called ``javaEnabled()`` that returns a Boolean value indicating whether the browser has JavaScript enabled.

```
if (navigator.javaEnabled()) {
  // JavaScript is enabled
} else {
  // JavaScript is disabled
}
```
It is important to note that while these methods can detect if JavaScript is disabled, they should not be used to prevent users from accessing the website. It is recommended to provide alternative functionality for users who have disabled JavaScript.

**EXAMPLE 1** website with javascript disabled 
https://en.wikipedia.org/wiki/Main_Page

This is the main page of Wikipedia, a popular online encyclopedia. The website has been designed to work without JavaScript, and most of the functionality of the website can be accessed without JavaScript.

Without JavaScript, some advanced features of the website may not work, such as collapsible menus or interactive elements. However, the website's core functionality remains intact, and users can still browse and read articles on the website.

When JavaScript is disabled, Wikipedia displays a message at the top of the page asking users to enable JavaScript for optimal experience, but the site still remains fully functional.

This is a good example of how websites can be designed to be accessible to users who have disabled JavaScript or are using browsers that don't support it.

**EXAMPLE 2** Website that works without JavaScript enabled:

https://www.w3schools.com/html/html_basic.asp

This website is a basic HTML tutorial from W3Schools. It contains mostly text and images, and the website's functionality does not depend on JavaScript.

When JavaScript is disabled, the website still works as intended, and users can browse the content, view images, and interact with links.

While the website may not have advanced features or interactive elements without JavaScript, it serves as a good example of how websites can be designed to work without JavaScript and still provide useful information to users.

**Website example that utilizes JavaScript:**

https://www.todomvc.com/examples/vanillajs/

This website is a to-do list application built with vanilla JavaScript. Users can create, edit, and delete tasks, and the website's functionality relies heavily on JavaScript to provide a seamless user experience.

When JavaScript is enabled, users can interact with the to-do list by adding, editing, or deleting tasks, and the website updates in real-time. The application is designed to be responsive and intuitive, with features such as drag-and-drop task reordering.

This is a good example of how JavaScript can be used to enhance a website's functionality and provide an improved user experience. However, it's important to keep in mind that websites should still be designed to work without JavaScript for users who have disabled it or are using browsers that don't support it.

**Here is how you can know if javascript is enable**
You can use JavaScript to check if it's enabled in a user's browser. Here's an example code snippet that checks if JavaScript is enabled:
```
<script>
  if (typeof(Storage) !== "undefined") {
    // JavaScript is enabled
    localStorage.setItem("jsEnabled", "true");
  } else {
    // JavaScript is disabled
    localStorage.setItem("jsEnabled", "false");
  }
</script>
```
In this example, the code checks if the ``Storage`` object is available in the user's browser, which is an indicator that JavaScript is enabled. If the ``Storage`` object is available, the script sets a key-value pair in the ``localStorage`` object to indicate that JavaScript is enabled. If the Storage object is not available, the script sets the key-value pair to indicate that JavaScript is disabled.

You can also use the navigator object to check if JavaScript is enabled, like this:
```
<script>
  if (navigator && navigator.userAgent && 
    !navigator.userAgent.includes("Edge") && 
    !navigator.userAgent.includes("Trident")) {
    // JavaScript is enabled
    localStorage.setItem("jsEnabled", "true");
  } else {
    // JavaScript is disabled
    localStorage.setItem("jsEnabled", "false");
  }
</script>
```
This code checks the user agent string to see if the browser is Edge or Internet Explorer, which do not support some modern JavaScript features. If the browser is not Edge or Internet Explorer and the ``navigator`` object is available, the script sets a key-value pair in the localStorage object to indicate that JavaScript is enabled. If the ``navigator`` object is not available or the browser is Edge or Internet Explorer, the script sets the key-value pair to indicate that JavaScript is disabled.

Note that while these methods can detect if JavaScript is enabled, they should not be used to prevent users from accessing the website. It is recommended to provide alternative functionality for users who have disabled JavaScript.
