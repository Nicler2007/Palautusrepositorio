flowchart TD
    A[Käyttäjä kirjoittaa muistiinpanon] --> B[Painaa Save]
    B --> C[spa.js estää lomakkeen<br/>oletustoiminnan (preventDefault)]
    C --> D[Selaimen lähettää POST<br/>/new_note_spa]
    D --> E[Palvelin tallentaa<br/>muistiinpanon]
    E --> F[Palvelin palauttaa<br/>201 Created + JSON]
    F --> G[JavaScript lisää uuden<br/>muistiinpanon lokaalisti]
    G --> H[DOM päivitetään<br/>ilman sivun uudelleenlatausta]