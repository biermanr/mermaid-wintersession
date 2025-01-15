The documentation for sequence diagram messages is located at [mermaid-js/messages](https://mermaid.js.org/syntax/sequenceDiagram.html#messages)

How actors interact? Take the first requirement `A User created a new object: I need to mint a ID with ID System X`

1. User Creates a thingamajig in our system
   ```
   user ->> sys: ...
   ```
1. Our System asks System X to mint an ID
1. System X responds with the ID
1. We show the user the ID


```mermaid
%%{
  init: {
    'theme': 'base',
    'themeVariables': {
      'primaryColor': '#BB2528',
      'primaryTextColor': '#fff',
      'primaryBorderColor': '#7C0000',
      'lineColor': '#F8B229',
      'secondaryColor': '#006100',
      'tertiaryColor': '#fff'
    }
  }
}%%

sequenceDiagram
title  System Requirements Diagram
accTitle: System Requirements Sequence Diagram

actor user as User
participant sys as Our System
participant ext as External System
actor curator as Curator

user ->> sys : Create thingamajig
sys ->> ext : Mint ID
sys ->> sys : Wait
ext ->> sys : Send ID
sys ->> user : Show ID
```
