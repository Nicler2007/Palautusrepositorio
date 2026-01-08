# Palautusrepositorio

sequenceDiagram
    participant browser
    participant server

    Note right of browser: Käyttäjä kirjoittaa tekstikenttään muistiinpanon ja painaa "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note right of server: Palvelin tallentaa muistiinpanon palvelimen muistiin
    server-->>browser: HTTP 302 Redirect /exampleapp/notes
    deactivate server

    Note right of browser: Selain seuraa uudelleenohjausta ja lataa sivun uudelleen

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: JavaScript file
    deactivate server

    Note right of browser: JavaScript hakee päivitetyn muistiinpanodatan

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON (sisältää myös uuden muistiinpanon)
    deactivate server

    Note right of browser: Selain renderöi muistiinpanot näkyviin