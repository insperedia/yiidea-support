# View path replacements

View path replacements help the plugin to find paths to views calculated during runtime. 
There are the following cases when it can be used:
* Themes
* Aliases
* Non-standard project structure

Use plugin settings in sections Views > View replacements to add a replacement. 
The replacement consists of two values, "Path to be replaced" and "Replacements path".
The plugin simply replaces part of the path from Path to be replaced.
"Replacement path" is the path from the root of the project. 
Looking at the error message when the plugin cannot find the view can help you understand what replacement you need to create.

### Aliases
Similarly, it works with aliases; the plugin replaces @alias with the path in the "Replacement path."
Often, we have different applications in different folders, for example, backend and frontend.
You can redefine @app alias, but only one in the current implementation. To solve this problem you can use different aliases for applications, for example, @frontend and @backend
There is a built-in @app alias that points to the root of the project. 

### Examples:

* Your models are located not in the views folder but in modules/views.
Replacement: /views;/modules/views

* Themes
/views;/themes/basic

* Aliases
Imagine you have frontend and backend applications. You can create the following replacements.
@frontend;/frontend
@backend;/backend
@app;/frontend

Unfortunately, in the current implementation, you can redefine @app only once, so @app in the backend will be resolved incorrectly.

