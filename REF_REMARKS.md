# Remarks Convention

This is my attempt to standardize remarks in my JavaScript.

## Start JavaScript Doc 

/* ================================= */
/* ====== By John McCutchan ======== */
/* ================================= */
//

## Begin

console.log("Begin."); //**** Message
//

## Any Dev Scripts

/* +++++++++ DEV TOOL ++++++++++++++ */
document.querySelector("body").addEventListener("click", function(e) {
  console.log(e);
});
/* +++ REMOVE BEFORE PRODUCTION ++++ */
//

## Global Variables

/* ================================= */
/* ====== Global Vars ============== */
/* ================================= */
var inventory = [];
loadInventory();
var focusTgt = "";
var counter = false;
//

## JSON (with Callback)

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

## Functions

/* ================================= */
/* ====== Create Cards ============= */
/* ================================= */
function populatePage () {
  for(var i = 0; i < loadInventory.cars.length; i++){ // Loops through the JSON Parse to creat inner HTML
    inventory += `<div class="col-lg-4 col-md-6">
                    <div class="card">
                      <img class="card-img-top img-fluid img-xs-center" ${loadInventory.cars[i].img} alt="Card image cap">
                      <div class="card-block">
                        <h4 class="card-title">${loadInventory.cars[i].make}</h4>
                        <h5 class="year">${loadInventory.cars[i].year}</h5>
                        <h5 class="model">${loadInventory.cars[i].model}</h5>
                        <h3 class="price">${loadInventory.cars[i].price}</h3>
                        <p class="card-text">${loadInventory.cars[i].description}</a>
                      </div>
                    </div>
                  </div>  `
  } // End loop
  // console.log("Inventory", inventory);//**** Shows the inner HTML string
  document.getElementById("cardsGoHere").innerHTML = inventory; // Loads inventory into DOM
  activateEvents();
} // End function
//

## End

// END

