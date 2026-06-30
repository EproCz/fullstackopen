sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: GET /exampleapp/spa
    activate Server
    Server-->>Browser: HTML document (SPA version)
    deactivate Server

    Browser->>Server: GET /exampleapp/main.css
    activate Server
    Server-->>Browser: CSS file
    deactivate Server

    Browser->>Server: GET /exampleapp/spa.js
    activate Server
    Server-->>Browser: JavaScript file
    deactivate Server

    Note right of Browser: Browser executes spa.js which fetches JSON data

    Browser->>Server: GET /exampleapp/data.json
    activate Server
    Server-->>Browser: JSON list of notes
    deactivate Server

    Note right of Browser: Browser renders notes using JavaScript (SPA)
