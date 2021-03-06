# String Extensions
A set of string extensions to extend string capabilities of JavaScript.

The list of extensions:

* [trimLeft](#trimleft)
* [trimRight](#trimright)
* [trim](#trim)
* [padLeft](#padleft)
* [padRight](#padright)
* [insert](#insert)
* [startsWith](#startswith)
* [endsWith](#endswith)
* [isNullOrEmpty](#isnullorempty)
* [isNullOrWhitespace](#isnullorwhitespace)
* [append](#append)
* [appendTo](#appendto)
* [prepend](#prepend)
* [prependTo](#prependto)
* [capitalize](#capitalize)
* [count](#count)
* [isEmail](#isemail)
* [isURL](#isurl)
* [toTime (integer)](#totime-integer)
* [toTime (string)](#totime-string)
* [valiDate](#validate)

## trimLeft

    var textToBeTrimmed = "     No space please!";
    console.log( textToBeTrimmed.trimLeft() ); // outputs: "No space please!"

    textToBeTrimmed = "zzzzzzzzzzWake up!";
    console.log( textToBeTrimmed.trimLeft("z") ); // outputs: "Wake up!"

## trimRight

    var textToBeTrimmed = "No space please!     ";
    console.log( textToBeTrimmed.trimRight() ); // outputs: "No space please!"

    textToBeTrimmed = "Sleeping Beautyzzzzzzzzzz";
    console.log( textToBeTrimmed.trimRight("z") ); // outputs: "Sleeping Beauty"

## trim

    var textToBeTrimmed = "     Space, space everywhere!     ";
    console.log( textToBeTrimmed.trim() ); // outputs: "Space, space everywhere!"

    textToBeTrimmed = "zzzzzzzzzzDo not disturb...zzzzzzzzzzz";
    console.log( textToBeTrimmed.trim("z") ); // outputs: "Do not disturb..."

## padLeft

    var textToBePadded = "Pad me, right?!?";
    console.log( textToBePadded.padLeft(20) ); // outputs: "    Pad me, right?!?"

    textToBePadded = "Fill in the blanks";
    console.log( textToBePadded.padLeft(20, "_") ); // outputs: "__Fill in the blanks"

## padRight

    var textToBePadded = "No space left";
    console.log( textToBePadded.padRight(20) ); // outputs: "No space left       "

    textToBePadded = "Fill in the blanks";
    console.log( textToBePadded.padRight(20, "_") ); // outputs: "Fill in the blanks__"

## insert

    var myText = "NoSpace";
    console.log( myText.insert(2, " ") ); // outputs: "No Space"

## startsWith

    var trickyQuestion = "Does this dress make me look fat?";
    console.log( trickyQuestion.startsWith("Does") ); // outputs: true
    console.log( trickyQuestion.startsWith("D") );    // outputs: true
    console.log( trickyQuestion.startsWith("Yes") );  // outputs: false

## endsWith

    var scaryQuestion = "Does this look infected?";
    console.log( scaryQuestion.endsWith("?") );        // outputs: true
    console.log( scaryQuestion.endsWith("ed?") );      // outputs: true
    console.log( scaryQuestion.endsWith("infected") ); // outputs: false

## isNullOrEmpty

    var temp = "";
    console.log( temp.isNullOrEmpty() );        // outputs: true
    temp = "  ";
    console.log( temp.isNullOrEmpty() );        // outputs: false
    temp = "full";
    console.log( temp.isNullOrEmpty() );        // outputs: false

## isNullOrWhitespace

    var temp = "";
    console.log( temp.isNullOrWhitespace() );   // outputs: true
    temp = "  ";
    console.log( temp.isNullOrWhitespace() );   // outputs: true
    temp = "full";
    console.log( temp.isNullOrWhitespace() );   // outputs: false

## append

    console.log( "You complete ".append("me") );   // outputs: "You complete me"

## appendTo

    var perfect = "yang", balance = "ying";
    console.log( perfect.appendTo(balance) );   // outputs: "yingyang"

## prepend

    var yodaStyle = "Do, or do not. There is no try.";
    console.log( yodaStyle.prepend("No! Try not. ") );   // outputs: "No! Try not. Do, or do not. There is no try."

## prependTo

    var reverseYodaStyle = "Do, or do not. There is no try. ";
    console.log( reverseYodaStyle.prependTo("No! Try not.") );   // outputs: "Do, or do not. There is no try. No! Try not."

## capitalize

    var capitalizeMe = "hello";
    console.log( capitalizeMe.capitalize() );             // outputs: "Hello"
    console.log( capitalizeMe.capitalize("w") );          // outputs: "Hello"
    console.log( capitalizeMe.capitalize("word") );       // outputs: "Hello"
    
    capitalizeMe = "hello world!";
    console.log( capitalizeMe.capitalize() );             // outputs: "Hello world!"
    console.log( capitalizeMe.capitalize("e") );          // outputs: "Hello World!"
    console.log( capitalizeMe.capitalize("every-word") ); // outputs: "Hello World!"
    
    capitalizeMe = "no! try not. do, or do not. there is no try.";
    console.log( capitalizeMe.capitalize("p") );          // outputs: "No! Try not. Do, or do not. There is no try."
    console.log( capitalizeMe.capitalize("paragraph") );  // outputs: "No! Try not. Do, or do not. There is no try."
    console.log( capitalizeMe.capitalize("e") );          // outputs: "No! Try Not. Do, Or Do Not. There Is No Try."
    
    console.log( capitalizeMe.capitalize("s", ".") );     // outputs: "No! try not. Do, or do not. There is no try."
    console.log( capitalizeMe.capitalize("split", ".") ); // outputs: "No! try not. Do, or do not. There is no try."
    console.log( capitalizeMe.capitalize("s", ",!") );    // outputs: "No! Try not. do, Or do not. there is no try."

## count

    var text = "no! try not. do, or do not. there is no try.";
    console.log( text.count() );      // outputs: 11 (word count)
    console.log( text.count("o") );   // outputs: 7  (character count)
    console.log( text.count("do") );  // outputs: 2  (string count)
    
## isEmail

    var temp = "this.is@an.email.com";
    console.log( temp.isEmail() );    // outputs: true
    temp = "this,however@is.not.an.email.com";
    console.log( temp.isEmail() );    // outputs: false
    
## isURL

    var temp = "https://github.com/karalamalar/StringExtensions";
    console.log( temp.isURL() );      // outputs: true
    temp = "github.com/karalamalar/StringExtensions";
    console.log( temp.isURL() );      // outputs: false

## toTime (integer)

    var temp = 134;
    console.log( temp.toTime() );     // outputs: 00:02:14
    console.log( temp.toTime(true) ); // outputs:     2:14 (compact mode)

## toTime (string)

    var temp = "4543";
    console.log( temp.toTime() );     // outputs: 01:15:43
    console.log( temp.toTime(true) ); // outputs:  1:15:43 (compact mode)

## valiDate[*](https://github.com/karalamalar/valiDate)

    var myDate = "8.1.2013";
    if(myDate = myDate.valiDate()) {
      console.log( myDate ); // outputs: "Tue Jan 08 2013 00:00:00 GMT+0200 (GTB Standard Time)"
    }
    myDate = "13.13.2013";
    console.log( myDate.valiDate() ); // outputs: false

Copyright (c) 2009-2013 İzzet Emre Erkan  
Licensed under Creative Commons Attribution-Share Alike 3.0 Unported License  
http://creativecommons.org/licenses/by-sa/3.0/
