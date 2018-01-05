# Cypher
<script>
    var alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
    function encode()
    {
        var inTB = document.getElementById("input");
        var input = inTB.innerHTML;
        var lowerIn = input.toLowerCase();
        var words = lowerIn.split(" ");
        var output = "";

        words.forEach(function(item, index, array) {
          output.concat(item.charAt(0));
          output.concat("oi ");
          output.concat(alphabet[((findLetter(item.charAt(0)) + 14)%26)]);
          output.concat(item.substr(1));
          output.concat(" ");
        });

        var outTB = document.getElementById("output");
        outTB.innerHTML = output;
    }

    function findLetter(letter) {
        for (i = 0; i < alphabet.length; i++) {
            if (letter == alphabet[i]) {
                return i;
            }
        }
        return -1;
    }

    function decode()
    {
        var inTB = document.getElementById("input");
        var input = inTB.innerHTML;

        var output = input;

        var outTB = document.getElementById("output");
        outTB.innerHTML = output;
    }
</script>
<input type = "text" value = "Input for coding/decoding" id = "input">
<br>
<input type = "button" value = "Encode the input" onclick = "encode();">
<input type = "button" value = "Decode the input" onclick = "decode();">
<br>
<input type = "text" id = "output">