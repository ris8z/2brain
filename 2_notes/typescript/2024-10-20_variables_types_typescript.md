---
date: 2024-10-20 
tags: 
    - typescript
hubs: 
    -   "[[2024-10-20_typescript-basics|typescript basics]]"
---

# variables_types_typescript

## How? using var, let, const

### Table

| **Feature** | **var** | **let** | **const**|
| --------------- | --------------- | --------------- | --------------- |
| Scope | function | block | block |
| Modifible | yes | yes | no |
| Mandatory Inizialitation | no | no | yes|
| Hosting | Yes, but the value is `undefind` before the declaration| Yes, but it's not accessible before the declaration | Yes, but it's not accessible before the declaration|
| Ridefinition | yes | no | no|

### Examples:

Scope 
```javascript
if (true) {
  let a = 10;
  const b = 20;
  var c = 30;
}
console.log(a); // Errore: a non è definito
console.log(b); // Errore: b non è definito
console.log(c); // Funziona: c = 30
```
Modifiable
```javascript
let x = 5;
x = 10; // Funziona

const y = 15;
y = 20; // Errore: y non può essere riassegnato
```

Hoisting
```javascript
console.log(a); // undefined
var a = 5;

console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 10;

console.log(c); // ReferenceError: Cannot access 'c' before initialization
const c = 15;
```
## Types

### Primitives
```javascript
let nome: string = "Mario";
let eta: number = 25;
let isOnline: boolean = false;
let vuoto: null = null;
let nonDefinto: undefined = undefined;

// symbol: Un valore univoco e immutabile (introdotto in ES6).
let simbolo: symbol = Symbol("descrizione");

// bigint: Per numeri interi molto grandi, introdotto in ES2020.
let grandeNumero: bigint = 12345678901234567890n;
```

### Compelx
```javascript
//arrays
let num1: number[] = [1,2,3];
let num2: Array<number> = [1,2,3];

//tuple
let tuple1: [string, number] = ["Mario", 12];

//object
let persona: { nome: string, age: number } = { nome: "Mario", age: 12};
```
### Special
```javascript
//any: Rappresenta qualsiasi tipo di valore. Disabilita il controllo dei tipi statico e dovrebbe essere evitato quando possibile.

let qualunque: any = "testo";  // Può essere qualsiasi cosa
qualunque = 10;  // Anche un numero

//unknown: Simile a any, ma più sicuro perché richiede un controllo del tipo prima di essere utilizzato.

let sconosciuto: unknown;
sconosciuto = "testo";
sconosciuto = 10;

if (typeof sconosciuto === "string") {
  console.log(sconosciuto.toUpperCase());  // Sicuro ora
}

//never: Rappresenta un tipo che non dovrebbe mai accadere (ad esempio, una funzione che non restituisce mai o che lancia sempre un'eccezione).

function errore(msg: string): never {
  throw new Error(msg);
}

//void: Usato tipicamente per indicare che una funzione non restituisce un valore.

function saluta(): void {
  console.log("Ciao");
}
```
### Union and Intersection
```javascript
//Union Types (|): Permette di specificare una variabile che può essere di uno o più tipi.
let id: number | string;
id = 123;  // Va bene
id = "ABC";  // Va bene


//Intersection Types (&): Permette di combinare più tipi, dove l'oggetto risultante deve soddisfare tutti i tipi combinati.
interface Studente {
  nome: string;
  matricola: number;
}

interface Lavoratore {
  azienda: string;
}

let persona: Studente & Lavoratore = {
  nome: "Mario",
  matricola: 1234,
  azienda: "TechCorp"
};
```

### Custom Types
```javascript
//Type Aliases (type): Permette di creare alias di tipi personalizzati.
type Punto = {
  x: number;
  y: number;
};

let coordinata: Punto = { x: 10, y: 20 };


//interface: Simile a un type, ma più flessibile e può essere estesa.
interface Persona {
  nome: string;
  età: number;
}

let p: Persona = { nome: "Mario", età: 25 };

//Le interfacce possono essere estese:
interface Studente extends Persona {
  matricola: number;
}

let s: Studente = { nome: "Luigi", età: 22, matricola: 1234 };
```

### Enum
```javascript
//enum: Tipo enumerativo per definire un insieme di valori costanti.
enum Colore {
  Rosso,
  Verde,
  Blu
}

let c: Colore = Colore.Rosso;


//Puoi anche definire enum con valori personalizzati:
enum Stato {
  Attivo = "ATTIVO",
  Inattivo = "INATTIVO",
}

let statoUtente: Stato = Stato.Attivo;
```

### Tipi di Funzione
```javascript
//Le funzioni in TypeScript possono avere tipi per i loro parametri e per il valore di ritorno.
function somma(a: number, b: number): number {
  return a + b;
}


//Puoi anche dichiarare i tipi per le funzioni anonime e gli event handlers:
let addizione: (x: number, y: number) => number = function(x, y) {
  return x + y;
};
```

### Modificatore di tipo
```javascript
//readonly: Rende una proprietà immutabile.
interface Punto {
  readonly x: number;
  readonly y: number;
}

let punto: Punto = { x: 10, y: 20 };
// punto.x = 30; // Errore, perché x è readonly

//? (opzionale): Rende una proprietà opzionale.
interface Persona {
  nome: string;
  età?: number;  // Opzionale
}

let p: Persona = { nome: "Mario" };  // età è opzionale
```
