# View path replacements

View path repalcements helps plugin to find path to views calculated during runtime. 
There following cases when it can be used:
* Themes
* Aliases
* Non standart project structure

To add replacement go to plugin settings in sections Views > View replacments. 
Replacement consists of two values, "Path to be replaces" and "Replacements path".
Plugin then simple replace part of the path from Path to be replaces.
"Replacement path" if the path from root of project. 
You can unserstand what replacement you need to create by looking error message when plugin can not find view.

### Aliases
Similar whay it works with aliases. There is build in @app alias that points to root of project. 
Often we have different applications in different fodlers, for example backend and frontend.
You can redefine @app alias, but only one in current implementation. To solve this problem you can use different aliases for applications, for exampel @frontend and @backend

### Examples:

* Your models located not in views folder but modules/views.
Replacement: /views;/modules/views

* Themes
/views;/themes/basic

* Aliases
Imagine you have frontend and backend applciation. You can create following replacements.
@frontend;/frontend
@backend;/backend
@app;/frontend

Uunfortunatly in current implemention you can redefine @app only one time, so @app in backend with be resolved incorrectly.

