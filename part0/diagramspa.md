sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML base (minimal)
    deactivate server

    browser->>server: GET main.css
    server-->>browser: CSS
    browser->>server: GET main.js
    server-->>browser: SPA JavaScript

    Note right of browser: The browser renders the page using JS

    browser->>server: GET data.json
    server-->>browser: JSON with the notes

    Note right of browser: The notes are dynamically rendered in the DOM