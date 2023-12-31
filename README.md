# fullstackopen
Main repository to upload the exercises and homework of the bootcamp.

### 0.4: Diagrama de Secuencia hecho en mermaid.js.org.
```mermaid
 sequenceDiagram
    actor user
    participant navegador
    participant servidor
    
    Note right of user: The user type in the input type text the note to add and press enter.
     navegador->>servidor: POST https://studies.cs.helsinki.fi/exampleapp/new_note
      activate servidor
      Note right of navegador: The navegador Return 302 to indicate to the navegador to make another request to /exampleapp/notes!
      servidor->>navegador: 302 Status Code
      deactivate servidor
      

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate servidor
    servidor-->>navegador: HTML document
    deactivate servidor

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate servidor
    servidor-->>navegador: the css file
    deactivate servidor

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate servidor
    servidor-->>navegador: the JavaScript file
    deactivate servidor

    Note right of navegador: The navegador starts executing the JavaScript code that fetches the JSON from the server

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate servidor
    servidor-->>navegador: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate servidor

    Note right of navegador: The navegador executes the callback function that renders the notes
```

### 0.5: Diagrama de Secuencia mermaid https://studies.cs.helsinki.fi/exampleapp/spa.
```mermaid
 sequenceDiagram
    actor user
    participant navegador
    participant servidor
    
    Note right of user: The user type The URL https://studies.cs.helsinki.fi/exampleapp/spa.
    user->>navegador: https://studies.cs.helsinki.fi/exampleapp/spa

      

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate servidor
    servidor-->>navegador: HTML document
    deactivate servidor

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate servidor
    servidor-->>navegador: the css file
    deactivate servidor

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate servidor
    servidor-->>navegador: the JavaScript file
    deactivate servidor

    Note right of navegador: The navegador starts executing the JavaScript code that fetches the JSON from the server

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate servidor
    servidor-->>navegador: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate servidor

    Note right of navegador: The navegador executes the callback function that renders the notes
     navegador-->>user: FULL HTML, With styles and js with data from json.
```

### 0.6: Diagrama de Secuencia mermaid https://studies.cs.helsinki.fi/exampleapp/spa when user create send a new note.
```mermaid
 sequenceDiagram
    actor user
    participant navegador
    participant servidor
    
    Note right of user: The user type in the input type text the note to add and press enter.

     navegador->>servidor: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
      activate servidor
      Note right of navegador: The navegador Return 201 to indicate to the navegador the note have been created  /exampleapp/notes!
      servidor-->>navegador: 201 Status Code
      deactivate servidor
    

    Note right of navegador: The navegador executes the callback function that renders the notes
```
