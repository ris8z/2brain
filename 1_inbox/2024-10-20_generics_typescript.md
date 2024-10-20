---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# generics_typescript

#### Generics
```javascript
//TypeScript supporta i tipi generici, che permettono di creare funzioni o classi che funzionano con qualsiasi tipo.
function identità<T>(arg: T): T {
  return arg;
}

let numero = identità<number>(10);  // T è number
let testo = identità<string>("Ciao");  // T è string
```

#### Tipi condizionali
```javascript
//I tipi condizionali permettono di creare tipi dinamici in base a condizioni.
type TipoCondizionale<T> = T extends string ? string : number;

let risultato: TipoCondizionale<string>;  // Risulta essere di tipo string
let risultato2: TipoCondizionale<number>;  // Risulta essere di tipo number
```
