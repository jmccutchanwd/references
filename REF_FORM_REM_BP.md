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
#Remarks Boilerplate
***
```
/* ================================= */
/* ====== By John McCutchan ======== */
/* ================================= */
//
console.log("Begin."); //**** Message
//
/* +++++++++ DEV TOOL ++++++++++++++ */
document.querySelector("body").addEventListener("click", function(e) {
  console.log(e);
});
/* +++ REMOVE BEFORE PRODUCTION ++++ */
//
/* ================================= */
/* ====== Global Vars ============== */
/* ================================= */

//
/* ================================= */
/* ====== Load JSON ================ */
/* ================================= */
function loadInventory (callback) { // Load the inventory
  var inventoryLoader = new XMLHttpRequest();
  inventoryLoader.addEventListener("load", function (e) { // Callback .......=
  loadInventory = JSON.parse(e.target.responseText);//.......................=
  console.log("Load complete.");//...........................................=**** Message
  console.log("JSON: ", loadInventory);//....................................=**** Shows the JSON
  populatePage(e);//.........................................................=
  console.log("Number of cars in inventory: ",loadInventory.cars.length);//..=**** Number of cars in inventory
  });//..................This is not called until after the section below is =
  inventoryLoader.open("GET", "https://car-sales-jm.firebaseio.com/.json"); // JSON Called from Firebase :)
  inventoryLoader.send();
} // End function
//
/* ================================= */
/* ====== Function ================= */
/* ================================= */

// End loop

// END
```
