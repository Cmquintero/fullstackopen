---ejercicio06---
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML + CSS + JavaScript 
    deactivate server
    
    Note right of browser : the server only load once 

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: XML FILE(json)
    deactivate server

    Note right of browser: new note in spa

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: New_notes_spa(json)
    deactivate server

    browser->>server: POST https://translate-pa.googleapis.com/v1/translateHtml
    activate server
    server-->>browser: translateHtml
    deactivate server
    

    Note right of browser: the server only can read the notes using the headers of code 