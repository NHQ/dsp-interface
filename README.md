**Generic DSP Interface**

Require this generic HTML5 / Touch compatible web socket interface.

**POSTED:** This is a slow, string transporting, pseudo midi signal. The GUI is a clumsy, DOM based implementation which traded multi-touch and non working range sliders for single touch capable sliders that actually work!

Future version will sweet tho: binary transprt, real midi, canvas face

The interface has 10 channels. 8 have corresponding exponents.

    var gui = require('dsp-interface').listen(5001);

    line3 = gui.val[2]
    line3exp = gui.exp[2]

    function(time){
      return Math.sin(time * Math.PI * (line1 * Math.pow(10, line3exp)))
    }


The first channel ui.val[0] return values 0,...,11 to correspond with either cranking it past ten, or the 12 note classes in the western scale.

ui.val[1] returns values [1/12, 1/11, ...,1/2, 1, 2, ..., 12] for semi-tones

channels 2-9 return values 0-9.9 at intervals of 0.1. 

ui.exp channels all return values 0-3, meant to be used to define the exponent for the their corresponding channels values. The exp[0] and exp[1] are undefined.

    npm install dsp-interface



