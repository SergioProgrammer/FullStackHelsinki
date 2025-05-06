```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    note right of server: The server receives the form data (note, date)
    server-->>browser: Redirect to /notes
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: Updated HTML with the new note
    deactivate server

    browser->>server: GET main.css
    server-->>browser: CSS
    browser->>server: GET main.js
    server-->>browser: JS

    browser->>server: GET data.json
    server-->>browser: JSON with the notes, including the new one