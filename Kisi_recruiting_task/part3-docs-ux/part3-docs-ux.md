# Kisi + Legacy Hardware Integration

This guide explains how Kisi works when integrating with legacy hardware.  


Integrating Kisi with Legacy Hardware means you can modernize access control without replacing all existing hardware, avoiding extra costs. 
 

**Scenario A: Legacy reader + Kisi Reader**

- User present card by tapping it on legacy reader
- The reader forwards the signal to the Kisi system via Wiegand board (READER mode).
- Kisi checks credential in cloud
- If valid, Kisi relay/reader unlocks door


**Scenario B: Legacy controller + Kisi Controller**

- User taps card on legacy reader
- Wiegand board (READER mode) sends to Kisi → credential verified
- Kisi outputs via Wiegand board (CONTRL mode) → Legacy controller
- Legacy controller executes door unlock

## Wiring Overview (Mermaid Diagram)

```mermaid
flowchart TD
  subgraph ScenarioA[Legacy Reader + Kisi Reader]
    A1["User taps legacy reader"] --> A2["Wiegand Board\nREADER mode"]
    A2 --> A3["Kisi Controller"]
    A3 --> A4["Relay unlocks door"]
  end

  subgraph ScenarioB[Legacy Controller + Kisi Controller]
    B1["User taps legacy reader"] --> B2["Wiegand Board\nREADER mode"]
    B2 --> B3["Kisi Controller"]
    B3 --> B4["Wiegand Board\nCONTRL mode"]
    B4 --> B5["Legacy Controller"]
    B5 --> B6["Door unlock"]
  end

