# Lean-react-app-template

A simple and lean react template.

To start parcel server in port 3000:

```
npm start
```



## Recipe to get to this template

```
mkdir react-project
cd react-project
npm init -y
```

Install dependencies:

```
npm install --save react react-dom
npm install --save-dev @babel/preset-react @babel/preset-env parcel-bundler
```

Next, create the `.babelrc` file.

```
{
  "presets": [
    "@babel/preset-react"
  ],
  "plugins": [
    [
      "@babel/plugin-proposal-class-properties",
      {
        "loose": true
      }
    ],
    [
      "@babel/plugin-transform-react-jsx",
      {
        "pragmaFrag": "React.Fragment"
      }
    ]
  ]
}
```

Next create our react app files. First `index.html`:

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<title>Lean-react-app-template</title>
</head>

<body>
	<div id="root"></div>
	<script src="index.js"></script>
</body>

</html>
```

Then `index.js`:

```
import React from "react"
import ReactDOM from "react-dom";

import App from "./src/components/App";

ReactDOM.render(<App />, document.querySelector("#root"));
```

Finally `src/components/App.js`:

```
import React from "react";

const App = () => <div>A simple and lean react template.</div>;

export default App;
```

We just need to add a script entry to `package.json` to be able to start our app:

```
"scripts": {
  "start": "parcel index.html --port 3000",
},
```

And back to the beginning, to start parcel server in port 3000:

```
npm start
```
