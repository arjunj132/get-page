# Get-Page Project
[![](https://data.jsdelivr.com/v1/package/gh/carrotscript/get-page/badge)](https://www.jsdelivr.com/package/gh/carrotscript/get-page)    [![Codacy Badge](https://app.codacy.com/project/badge/Grade/515eb13b01e544338f48648424d60779)](https://www.codacy.com/gh/arjunj132/get-page/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=arjunj132/get-page&amp;utm_campaign=Badge_Grade)
## Installation

This project is only for GET requests. To use this, just import the via the CDN:

```
<script src="https://cdn.jsdelivr.net/gh/carrotscript/get-page@1.2/install.min.js"></script>
```

## Usage

To use it, you use the function `get` and add a `.then` statement to get the promise. For example:

```
get("https://google.com").then(data => {
  console.log(data);
})
```
 If you are accessing JSON and want to parse it, you use the `json` function:
 
```
get("https://jsonplaceholder.typicode.com/todos/1").then(data => {
  console.log(data.id); // getting undefined
  data = json(data);
  console.log(data.id); // getting 1
})
```
## Advantages


### 1. Supports CORS requests
The best feature may be it's built-in CORS proxy! It never expires and does not have a quota! Regular requests via JS only support non-CORS blocked servers.

### 2. Really easy to use
JavaScript is pretty hard to use without a framework. And for calling data from server's, they can be extremly hard. Check out this comaparison:

#### XMLHttpRequest - A waste of time
```
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
       console.log(xhttp.responseText);
    }
};
xhttp.open("GET", "https://jsonplaceholder.typicode.com/todos/1", true);
xhttp.send();
```

#### Fetch API - Close, but not the best
```
let url = "https://jsonplaceholder.typicode.com/todos/1";
fetch(url)
.then(response => {
	response.json();
})
.then(data => {
	console.log(data);
});
```

#### Get-Page - The best out of all of them

```
get("https://jsonplaceholder.typicode.com/todos/1").then(data => {
  console.log(json(data));
})
```
