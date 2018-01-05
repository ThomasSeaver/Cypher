# Cypher
<script>
    var alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
    function encode()
    {
        var inTB = document.getElementById("input");
        var input = inTB.innerHTML;
        input.toLowerCase();
        input.split(" ");

        var output = input;

        var outTB = document.getElementById("output");
        outTB.innerHTML = output;
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