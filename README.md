<script>
    var alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
    function encode()
    {
        var inTB = document.getElementById("input");
        var input = inTB.value;
        var words = input.split(" ");
        var output = "";
        console.log(words.length);
        var curWord;
        for (i = 0; i < words.length; i++){
            curWord = words[i];
            output += (curWord.charAt(0));
            output += ("oi ");
            output += (alphabet[((findLetter(words[i].charAt(0)) + 14)%26)]);
            output += (words[i].substr(1));
            output += (" ");
            console.log(i);
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
        var inTB = document.getElementById("input");
        var input = inTB.innerHTML;

        var output = "Yah dummy decoding isnt done yet!!!!! what are you doing!!!!!";

        var outTB = document.getElementById("output");
        outTB.innerHTML = output;
    }
</script>
<h1>This is where we do the stupid stupid cyphering boys step right up step right up</h1>
<input type = "text" value = "Input for coding/decoding" id = "input">
<br>
<input type = "button" value = "Encode the input" onclick = "encode();">
<input type = "button" value = "Decode the input" onclick = "decode();">
<br>
<textarea id = "output">

</textarea>