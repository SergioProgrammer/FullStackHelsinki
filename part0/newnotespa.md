sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user writes a note and clicks "Save"
    Note right of browser: JS intercepts the submit event and creates a note object

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: 201 Created (no redirection)
    deactivate server

    Note right of browser: The browser updates the view without reloading the page