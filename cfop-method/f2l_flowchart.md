``` mermaid
info
---
config:
  layout: fixed
  securityLevel: loose
---
flowchart TB
    Start((("Bring both pieces to the Up layer"))) --> A{{"Are the pieces connected"}}
    A -- Yes --> B{{"Is the edge to the left or right of the corner?"}}
    B -- Left --> T@{img: "../assets/images/edge_left.png", w: 100, constraint: on, shape: rounded}
    T --> D[Separate the pieces using **U F' U F**]
    B -- Right --> U@{img: "../assets/images/edge_right.png", w: 100, constraint: on, shape: rounded}
    U --> E[Separate the pieces using **U' R U' R'**]
    D --> C{{Is the white side of the corner facing up?}}
    E --> C
    C -- Yes --> F[Move the Up layer so the edge's side color matches its center]
    C -- No --> G["Move the Up layer in a way so that you can still see the whit face on the corner"]
    F --> H["Move the edge to the Middle layer without sending another F2L pair to the Up layer"]
    H --> I["Move the corner over the edge"]
    I --> J[Move the edge back to the Up layer. Now do either:]
    J --> K((**R U' R'**)) & L((**L' U L**))
    G --> M{{"Are the top colors on the edge and corner the same or different?"}}
    M -- Same --> N["Turn the layer where the white side of the corner is to move it to the bottom layer"]
    N --> O["Move the edge next to where the corner just was, **without being on the same layer as the white face**"]
    O --> P[Bring the corner back up. Now do: **U2 F' U F'**]
    M -- Different --> Q["Turn the layer where the white side of the corner is to move it to the bottom layer"]
    Q --> R["Move the edge across from where the corner was"]
    R --> S[Bring the corner back up. Now do: **U F' U' F**]
    A -- No --> C
```
