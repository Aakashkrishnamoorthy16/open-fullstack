```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types note and clicks Save

    Note right of browser: JS intercepts form submit (no page reload)
    Note right of browser: New note added to DOM immediately

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note/spa
    activate server
    Note right of server: Server saves the note
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: No redirect! Page stays the same.
```
