# BOBALAB JSON Repository
This is a centralized repo to serve JSON files for game data.

# Usage
1) Drop your JSON file with a specific name `<x>.json` into the repo (NOT IN A SUBFOLDER) and create a pull request
2) Get it approved by Prof. Park
3) In Qualtrics, use the following code to fetch from GitHub on the onload section of Qualtrics JS:
```javascript
async function loadJSON(url) {
  try {
    // Fetch the JSON data
    const response = await fetch(url);

    // Check if the response is ok (i.e., status code 200)
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }

    // Parse the JSON in the response
    const data = await response.json();
    console.log(data); // You can handle the JSON data here
    return data;
  } catch (error) {
    console.error('Failed to fetch JSON:', error);
  }
}

loadJSON("https://kjeelani.github.io/bobalab-jsons/<X>.json") // Where <X> is the name of the json file you've dropped
```
