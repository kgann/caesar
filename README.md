# jQuery Caesar

### Decrypt a simple caesar cypher stored in any html attribute
---------------------------------------------------------------

Example

    $(".selector").caesar()

Options

    attr: "data-href", // the location of the caesar string

    // default character lookup object
    charLookup: {
      a: "z", b: "a", c: "b", d: "c", e: "d", f: "e", g: "f", h: "g", i: "h", j: "i",
      k: "j", l: "k", m: "l", n: "m", o: "n", p: "o", q: "p", r: "q", s: "r", t: "s",
      u: "t", v: "u", w: "v", x: "w", y: "x", z: "y", 1: "0", 2: "1", 3: "2", 4: "3",
      5: "4", 6: "5", 7: "6", 8: "7", 9: "8", 0: "9"
    },

    // optional onClick event - you are passed both decoded and encode versions of the string in the event object
    onClick: function(e) {
      // function
    }

Encrypt the string on the backend, then provide a character lookup table or use the default

Any character that does not have a property in the lookup object will be left alone

Most recently used for a client who didn't want some links visible to crawlers

    <span class="caesar" data-href="some encrypted link">Click Me!</span>

    $(".caesar").caesar({
      onClick: function(e){
        window.location = e.data.decoded;
      }
    })