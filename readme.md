CSS parser and optimizer.
=========================

Parses css code, automatically inserts browser-specific prefixes and compresses the code.
There is a possibility of caching the result.

The browser-specific prefixes is not a complete list but the most used css properties.
So it can easily be extended.

## Feachures

* Automatically inserts browser-specific prefixes for defined css properties.
* Removes two or more consecutive spaces.
* Removes the spaces, if a curly bracket, colon, semicolon or comma is placed before or after them.
* Removes newline characters and tabs.
* Writes and reads the compiled data into/from cache.

## Requirements

This program requires PHP 5.4+

## Example

<pre>
    /* File styles.css */

    .some_class {
        background: #1e5799;
        background: linear-gradient(to bottom, #1e5799 0%, #2989d8 50%, #207cca 51%, #7db9e8 100%);

        border: #000 solid 1px;
        border-radius: 5px;
        box-sizing: content-box;

        margin: 0em 5px;  /* This will be replaced with 0 ( 0em; )*/
        padding: 5px 0px; /* This will be replaced with 0 ( 0px; )*/

        transition: height .25s ease .1s;
    }
</pre>

## Result

<pre>
.some_class{
background:#1e5799;
background:-webkit-linear-gradient(to bottom,#1e5799 0%,#2989d8 50%,#207cca 51%,#7db9e8 100%);
background:-moz-linear-gradient(to bottom, #1e5799 0%,#2989d8 50%,#207cca 51%,#7db9e8 100%);
background:-o-linear-gradient(to bottom, #1e5799 0%,#2989d8 50%,#207cca 51%,#7db9e8 100%);
background:linear-gradient(to bottom,#1e5799 0%,#2989d8 50%,#207cca 51%,#7db9e8 100%);
borrder:#000 solid 1px;
-webkit-border-radius:5px;
-moz-border-radius:5px;
border-radius:5px;
-webkit-box-sizing:content-box;
-moz-box-sizing:content-box;
box-sizing:content-box;
margin:0 5px;
padding:5px 0;
-webkit-transition:height .25s ease .1s;
-moz-transition:height .25s ease .1s;
-o-transition:height .25s ease .1s;
transition:height .25s ease .1s;
}
</pre>

After finishing (removing newlines) the data file will be prepared, placed in one line.

The original code: (https://github.com/Greenray/css-optimizer).
Copyright (C) 2016 Victor Nabatov <greenray.spb@gmail.com>