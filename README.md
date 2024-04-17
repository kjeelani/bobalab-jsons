# BOBALAB JSON Repository
This is a centralized repo to serve JSON files for game data.

# Usage
1) Clone the repository to your local computer and create a new branch
2) Add your JSON file with a specific name `<x>.json` into the local repo
3) `git add .` -> `git commit -m <file_name>` -> `git push origin <branch_name>`
4) Create a pull request on GitHub
5) Get it approved by Prof. Park (or just DM me on Discord @Kaijen)
6) In Qualtrics, use the following code to fetch from GitHub on the onload section of Qualtrics JS:
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
