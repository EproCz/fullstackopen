sequenceDiagram
    participant Browser
    participant Server

    Note right of Browser: User writes a new note and clicks "Save"

    Note right of Browser: JavaScript creates a new note object

    Browser->>Server: POST /exampleapp/new_note_spa
    activate Server
    Server-->>Browser: 201 Created
    deactivate Server

    Note right of Browser: SPA updates the notes list without reloading the page

    Note right of Browser: Browser renders the new note immediately
