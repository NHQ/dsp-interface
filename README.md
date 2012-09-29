**Generic DSP Interface**

Require this generic HTML5 / Touch compatible web socket interface. It returns to arrays, which valaues you can change in your browser.

**POSTED:** This is a slow, string transporting, pseudo midi signal. The GUI is a clumsy, DOM based implementation with non-continunous values. And I traded multi-touch + non working range sliders for single touch capable sliders that actually work! So it works on the ipad.

Future version will sweet tho: binary transprt, real midi, canvas face, continuous value ranges.

The interface has 10 range sliders, and 8 corresponding exponents buttons.

    var gui = require('dsp-interface');

    gui.start(5001);

    gui.line // a length 10 array
    gui.exp // a length 10 array ([0] and [1] do are empty, do not use);

    line3 = gui.line[2]
    line3exp = gui.exp[2]

    function(time){
      return Math.sin(time * Math.PI * (line1 * Math.pow(10, line3exp)))
    }


line[0] and line[1] return values 0,...,11 inclusive to correspond with either cranking it past ten, or for 12 octaves for each of the 12 note classes in the western scale. Why 12 octaves? You can't hear 7 hertz, but you can feel it!

line[2] returns range [-12, 12] inclusive 

lines 3-9 return values 0-9.9 at intervals of 0.1. 

ui.exp channels all return values 0-3, meant to be used to define the exponent for the their corresponding channels values. exp[0] and exp[1] are always zero.

    npm install dsp-interface



TODO:

* Add incr / decr buttons to range sliders
* Add on/off punch buttons
* Add placeholders for values you want to come back to