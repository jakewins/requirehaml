# requirehaml

A quick-hack javascript that monitors a folder tree for changes in *.haml files, and
compiles them into javascript templates that you can import using require.js.

Requires node.js and haml-js (npm install haml)

Usage:

    requirehaml my/source/folder my/target/folder

Note: Does not pick up if you create a new file, simply re-issue the command if you create a new file.


Example:

    #home
      = title
      %ul.menu
        %li Go Home
        %li Go Back

Becomes:
    
    define(function(){return function(vars){ with(vars) { return "<div id=\"home\">" + title + "<ul class=\"menu\"><li>Go Home</li><li>Go Back</li></ul></div>";}});

