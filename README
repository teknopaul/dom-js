dom-js is a node module that creates a DOM from a String using sax-js.

DomJS has a parse() method  that takes a string and a callback which is used when the DOM is ready, or if there is an error.

The DOM returned is made of Element, Comment and Text objects (N.B.  no ProccessingInstruction or other stuff)

An Element has a name, a map of attributes, and an array of children, so you can find everything.

You get a couple of convenience methods on Element   text()  and  firstChild()  usage is hopefully obvious and save some boiler plate null checking.

The Element object has a method toXml() which returns a String with whitespace in tact.

Thats it (for now) no bells, no whistles. 


    var DomJS = require("dom-js").DomJS;

    var domjs = new DomJS();

    var string = '<xml><!-- the comment --><elem someAtt="fat &amp; red">Hello &amp; World</elem></xml>';
    domjs.parse(string, function(err, dom) {
    	console.log(util.inspect(dom, false, 23));
    	console.log("serializes to : " + dom.toXml());
    });




Gotchas (that I can fix if it bothers anyone)

An empty tag <a></a>  will always be serialized in the short form <a/>.

<?xml version="1.0" encoding="UTF-8"?>  is ignored and dropped if there is one
var xml = '<?xml version="1.0" encoding="UTF-8"?>' + dom.toXml()  to fix that one :)

An instance of DomJS should only be used once, but if you must reuse, call reset() before re-calling parse().

