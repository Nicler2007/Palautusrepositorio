# Palautusrepositorio Part 0 – Diagrams

0.4: New note (traditional web app)

graph TD
    A[User writes a note] --> B[Clicks Save]
    B --> C[Browser sends POST /new_note]
    C --> D[Server saves the note]
    D --> E[Server responds with redirect]
    E --> F[Browser reloads /notes]
    F --> G[Browser requests data.json]
    G --> H[Notes are rendered]

0.5: Single Page App

graph TD
    A[User opens /spa] --> B[Browser loads HTML]
    B --> C[Browser loads CSS]
    C --> D[Browser loads spa.js]
    D --> E[spa.js requests data.json]
    E --> F[Server returns notes as JSON]
    F --> G[Notes rendered without page reload]

0.6: New note (SPA)

graph TD
    A[User writes a note] --> B[Clicks Save]
    B --> C[spa.js prevents default form action]
    C --> D[POST /new_note_spa]
    D --> E[Server saves the note]
    E --> F[Server returns JSON response]
    F --> G[spa.js updates notes list]
    G --> H[DOM updates without reload]
