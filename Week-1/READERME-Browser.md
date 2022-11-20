

BROWSER:

A browser retrieves information from other parts of the web and displays it on the desktop or mobile device. The information is transferred using the Hypertext Transfer Protocol(HTTP), which defines how text, images and video are transmitted on the web.

Functionality:

The Web browser function supports the following operations.
- Displaying and printing Web contents on the Internet or intranet.
- Displaying, printing, and saving a file on the Internet or intranet.
- Uploading scanned original data (via a server on the Internet or intranet)

Components of a Browser:

- The user interface: this includes the address bar, back/forward button, bookmarking menu, etc. Every part of the browser display except the window where you see the requested page.
- The browser engine: marshals actions between the UI and the rendering engine.
- The rendering engine: responsible for displaying requested content. For example if the requested content is HTML, the rendering engine parses HTML and CSS, and displays the parsed content on the screen.
- Networking: for network calls such as HTTP requests, using different implementations for different platform behind a platform-independent interface.
- UI backend: used for drawing basic widgets like combo boxes and windows. This backend exposes a generic interface that is not platform specific. Underneath it uses operating system user interface methods.
- JavaScript interpreter. Used to parse and execute JavaScript code.
- Data storage. This is a persistence layer. The browser may need to save all sorts of data locally, such as cookies. Browsers also support storage mechanisms such as localStorage, IndexedDB, WebSQL and FileSystem.


Rendering and its use:

- Rendering helps you to present the content on a webpage
- It makes use of HTML, CSS files to design the webpage however is required.
- The design of the webpage and what would be the functionality of the web page is decided by the developer who designs the page.
- Based on the design, the end-user will be able to understand the content, it would make the usage of the page easier for the end-user.

Parsers:

The output tree (the "parse tree") is a tree of DOM element and attribute nodes. DOM is short for Document Object Model. It is the object presentation of the HTML document and the interface of HTML elements to the outside world like JavaScript. The root of the tree is the "Document" object. The DOM has an almost one-to-one relation to the markup.

Script Processor:

The script processor executes Javascript code to process an event. The processor uses a pure Go implementation of ECMAScript 5.1 and has no external dependencies. This can be useful in situations where one of the other processors doesn’t provide the functionality you need to filter events.
Order of Script Processing:

- `<script> in <head>` - VeryHigh (Blocks parser)
- `<script type=module async>` - High (Interupts Parsser)
- `<script async>` - High (Interupts Parsser)
- `<script> at the end of <body>` - Low (Waits parser end)
`<link rel=prefetch>` + `<script>` in a next-page navigation - Depends on when and how the script is consumed.



Tree Construction:

The input to the tree construction stage is sequence of tokens from tokenisation stage. This stage is associated with DOM object when a parser is created. The “output” of this stage dynamically modifying or extending that document’s DOM Tree

Layout and Printing:

To construct the render tree, the browser roughly does the following:

Starting at the root of the DOM tree, traverse each visible node.
Some nodes are not visible (for example, script tags, meta tags, and so on), and are omitted since they are not reflected in the rendered output.
Some nodes are hidden via CSS and are also omitted from the render tree; for example, the span node---in the example above---is missing from the render tree because we have an explicit rule that sets the "display: none" property on it.
For each visible node, find the appropriate matching CSSOM rules and apply them.
Emit visible nodes with content and their computed styles.

The final output is a render tree that contains both the content and style information of all the visible content on the screen. With the render tree in place, we can proceed to the "layout" stage.
Up to this point we've calculated which nodes should be visible and their computed styles, but we have not calculated their exact position and size within the viewport of the device that's the "layout" stage, also known as "reflow."
