Browser -->  Server: GET /exampleapp/spa
Server --> Browser: HTML document

Browser --> Server: GET /exampleapp/main.css
Server --> Browser: CSS file

Browser --> Server: GET /exampleapp/spa.js
Server --> Browser: JavaScript file

Note right of Browser: Browser executes spa.js

Browser --> Server: GET /exampleapp/data.json
Server --> Browser: JSON data

Note right of Browser: JS renders notes using DOM
