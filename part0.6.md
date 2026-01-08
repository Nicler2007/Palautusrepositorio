sequenceDiagram
    participant browser
    participant server

    Note right of browser: Käyttäjä kirjoittaa muistiinpanon ja painaa Save

    Note right of browser: spa.js estää lomakkeen oletustoiminnan (preventDefault)

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of server: Palvelin tallentaa muistiinpanon
    server-->>browser: 201 Created (JSON vastauksena)
    deactivate server

    Note right of browser: JavaScript lisää uuden muistiinpanon lokaalisti
    Note right of browser: DOM päivitetään ilman sivun uudelleenlatausta
