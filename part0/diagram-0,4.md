sequenceDiagram
    participant Browser
    participant Server

    Note right of Browser: User writes a new note and clicks "Save"

    Browser->>Server: POST /exampleapp/new_note\ncontent=My new note
    activate Server
    Server-->>Browser: 302 Redirect to /exampleapp/notes
    deactivate Server

    Note right of Browser: Browser follows the redirect

    Browser->>Server: GET /exampleapp/notes
    activate Server
    Server-->>Browser: HTML document
    deactivate Server

    Browser->>Server: GET /exampleapp/main.css
    activate Server
    Server-->>Browser: CSS file
    deactivate Server

    Browser->>Server: GET /exampleapp/main.js
    activate Server
    Server-->>Browser: JavaScript file
    deactivate Server

    Note right of Browser: The browser starts executing JavaScript that fetches JSON

    Browser->>Server: GET /exampleapp/data.json
    activate Server
    Server-->>Browser: JSON list of notes (including the new one)
    deactivate Server

    Note right of Browser: Browser renders updated notes
