# BOBALAB JSON Repository
This is a centralized repo to serve JSON files for game data.

# Usage
1) Drop your JSON file with a specific name `<x>.json` into the repo (NOT IN A SUBFOLDER) and create a pull request
2) Get it approved by Prof. Park
3) In Qualtrics, use the following code to fetch from GitHub on the onload section of Qualtrics JS:
```javascript
function loadJSON(url, callback) {
  fetch(url)
    .then(response => {
      return response.json();
    })
    .then(data => {
      callback(data); // Pass data to callback
    })
    .catch(error => {
      callback(error.message); // Pass error message to callback
    });
}

let url = "https://kjeelani.github.io/bobalab-jsons/<X>.json" // Where <X> is the name of your JSON file
let testInput = '{}';
loadJSON(url, (data) => {
	isReady = true;
	testInput = data;
});
```
4) Note the callback you pass into loadJSON is important because it will allow you to signal to the rest of the code when the data is finally received and you can move on with the rest of your game's code.
