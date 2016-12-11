#Form Boilerplate
***
```
<form>
  <fieldset>
    <legend>Temperature Converter</legend><br>
    <label>Enter Temperature:</label>
    <input type="number" name="inputTemp" id="inputTemp">
    <br>
    <br>
    <input type="radio" name="temp" value="celsius" id="cels" checked> Celsius
    <input type="radio" name="temp" value="fahrenheight" id="fahr"> Fahrenheight
    <br>
    <br>
    <button type="button" id="converter" onkeyup="putNumberIn()" >Convert Temp</button>
    <br>
    <br>
  </fieldset>
</form>
```
