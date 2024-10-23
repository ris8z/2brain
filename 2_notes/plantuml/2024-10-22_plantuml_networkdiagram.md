---
date: 2024-10-22 
tags: 
    - plantuml
---

# plantuml_networkdiagram
```plantuml
@startuml

node "Linux Server" {
    frame "Match Manager (Node.js)" {
        component "WSS (WebSocket Secure)" as WSS
    }
}

node Client1 {
    node "Browser" as c1 {
        component "website (React)" as WB1
    }
}

node Client2 {
    node "Browser" as c2 {
        component "website (React)" as WB2
    }
}

node Client3 {
    node "Browser" as c3 {
        component "website (React)" as WB3
    }
}

node Client4 {
    node "Browser" as c4 {
        component "website (React)" as WB4
    }
}



WB1 --> WSS 
WB2 --> WSS 
WB3 --> WSS 
WB4 --> WSS 

@enduml
```
