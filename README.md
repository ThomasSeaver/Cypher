# Cypher
<script>
function encode()
{
    var inTB = document.getElementById("input");
    var input = inTB.innerHTML;

    var output = input;

    var outTB = document.getElementById("output");
    outTB.innerHTML = output;
}

function encode()
{
    var inTB = document.getElementById("input");
    var input = inTB.innerHTML;

    var output = input;

    var outTB = document.getElementById("output");
    outTB.innerHTML = output;
}
</script>
<input type = "text" value = "Input for coding/decoding" id = "input">
<input type = "button" value = "Encode the input" onclick = "encode();">
<input type = "button" value = "Decode the input" onclick = "decode();">
<input type = "text" id = "output">