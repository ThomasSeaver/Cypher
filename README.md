<script>
    var alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
    function encode()
    {
        var inTB = document.getElementById("input");
        var input = inTB.value;
        var area = input.split(/\r|\n/);
        var words;
        var output = "";
        for (k = 0; k < area.length; k++) {
            words = area[k].split(" ");
            for (i = 0; i < words.length; i++){
                if (words[i].length >= 2 && findLetter(words[i].charAt(0)) != -1) {
                    output += (words[i].charAt(0));
                    output += ("oi ");
                    output += (alphabet[((findLetter(words[i].charAt(0)) + 14)%26)]);
                    output += (words[i].substr(1));
                    output += (" ");
                } else {
                    output += words[i];
                }
            }
            output += "\n";
        }
        var outTB = document.getElementById("output");
        outTB.innerHTML = output;
        console.log(output);
    }

    function findLetter(letter) {
        letter = letter.toLowerCase();
        for (j = 0; j < alphabet.length; j++) {
            if (letter == alphabet[j]) {
                return j;
            }
        }
        return -1;
    }

    function decode()
    {
        document.getElementById("output").innerHTML = document.getElementById("input").value.replace(/[A-Za-z]oi [A-Za-z]/, replacer);

        /*var inTB = document.getElementById("input");
        var input = inTB.innerHTML;

        output

        var outTB = document.getElementById("output");
        outTB.innerHTML = output;*/
    }
    function replacer(match, p1, offset, string) {
        const [first, second, ...rest] = match;
        if (((first.charCodeAt(0) - 97 + 14) % 26 + 97) == second.charCodeAt(0)) {
            return first;
        } else {
            return match;
        }
    }
</script>
<h1>This is where we do the stupid stupid cyphering boys step right up step right up</h1>
<textarea id = "input" cols = "10" rows = "20">
Place to add text to be cyphered
</textarea>
<br>
<input type = "button" value = "Encode the input" onclick = "encode();">
<input type = "button" value = "Decode the input" onclick = "decode();">
<br>
<textarea id = "output" cols = "10" rows = "20">

</textarea>