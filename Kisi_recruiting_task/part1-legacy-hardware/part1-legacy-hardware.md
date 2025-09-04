# Integrating Kisi with Legacy Hardware: modernize access control without replacing all existing hardware  
 

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