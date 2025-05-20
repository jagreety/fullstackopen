````mermaid

sequenceDiagram
    participant browser
    participant server


    Note over browser: User writes a not and clicks "Save"


    Note right of browser: JavaScript intercepts the form submission 


    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note over server: Request body contains JSON like:<br>{"content": "My new note", "date": "2025-05-19"}
    server->>browser: 201 Created (Note saved)
    deactivate server


    Note right of browser: JavaScript updates the page<br>with the new note without reloading
