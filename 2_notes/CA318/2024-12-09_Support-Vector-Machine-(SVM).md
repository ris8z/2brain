---
date: 2024-12-09 
tags: 
    - CA318
hubs: 
    -   "[[2024-12-03_Advanced-Algorithms-and-AI-Search|Advanced Algorithms and AI Search]]"
---

# Support Vector Machine (SVM)

## Come Funziona SVM?

### Passaggi Principali

1. **Input dei dati:**
   - Consideriamo un dataset di immagini del viso, ciascuna rappresentata come un vettore numerico.
   - Ogni immagine viene convertita in scala di grigi e "appiattita" in un vettore di caratteristiche (es. intensità dei pixel).
   - Supponiamo di voler classificare due persone: Alice e Bob.

2. **Rappresentazione nello spazio:**
   - Ogni immagine viene rappresentata come un punto in uno spazio multidimensionale, dove ogni dimensione rappresenta una caratteristica (es. valore di un pixel).

3. **Separazione delle classi:**
   - L'SVM cerca un **iperpiano** che separi i dati di Alice e Bob nel modo più chiaro possibile.
   - Cerca di massimizzare il **margine** tra i dati più vicini al confine della classe (chiamati **support vectors**) e l'iperpiano.

4. **Predizione per nuovi dati:**
   - Quando una nuova immagine viene data in input, l'SVM determina da quale lato dell'iperpiano si trova e la classifica come Alice o Bob.

5. **Riconoscimento facciale non lineare:**
   - Per problemi complessi (es. diverse angolazioni del volto o variazioni di illuminazione), i dati non sono linearmente separabili.
   - L'SVM utilizza il **kernel trick** (es. kernel radiale o polinomiale) per trasformare i dati in uno spazio di dimensioni superiori, dove diventano separabili linearmente.


## Un Piccolo Esempio

### Supponiamo:
- Abbiamo immagini in scala di grigi di 10x10 pixel (100 caratteristiche per immagine).
- **Obiettivo:** Distinguere tra i volti di Alice e Bob.

### **Preparazione dei dati:**
- Immagini di Alice e Bob sono etichettate:
  - Alice = 1
  - Bob = -1
- Esempio:
  - Immagine 1 (Alice): `[0.1, 0.2, 0.3, …]`
  - Immagine 2 (Bob): `[0.2, 0.4, 0.1, …]`

### **Addestramento del modello:**
- L'SVM calcola un iperpiano che separa queste due classi con il massimo margine.
- Utilizza solo i **support vectors** (le immagini più vicine al margine) per definire il modello.

### **Classificazione:**
- Per una nuova immagine, l'SVM verifica da quale lato dell'iperpiano si trova il punto:
  - Se \(> 0\), è Alice.
  - Se \(< 0\), è Bob.


## Perché SVM era la scelta migliore prima delle reti neurali?

1. **Eccellente generalizzazione su piccoli dataset:**
   - Non richiede enormi quantità di dati, rendendola ideale per problemi di riconoscimento facciale con dataset limitati.

2. **Gestione della dimensionalità:**
   - Le immagini facciali, una volta convertite in vettori di caratteristiche, hanno dimensioni molto alte. L'SVM gestisce bene queste situazioni, riducendo il rischio di overfitting.

3. **Precisione:**
   - Risultati accurati e robusti rispetto ad altre tecniche disponibili all'epoca (es. k-NN o clustering).

4. **Efficienza:**
   - Meno intensivo computazionalmente rispetto alle reti neurali profonde.


## Un Caso Reale: Viola-Jones + SVM

- **Viola-Jones:** Rileva regioni del viso in un'immagine.
- **SVM:** Classifica ulteriormente le regioni come volti di specifiche persone.

### In un'applicazione pratica:
1. Viola-Jones rileva una regione del viso.
2. L'SVM classifica ulteriormente la regione come un volto di una specifica persona.


## Come gestire più classi con SVM

Per identificare più classi (es. Marco, Maria e Renzo), esistono due approcci principali:

### 1. **One-vs-One (OvO):**
- **Come funziona:**
  - Si costruisce un SVM separato per ogni coppia di classi. Ad esempio:
    - SVM1: Marco vs Maria.
    - SVM2: Marco vs Renzo.
    - SVM3: Maria vs Renzo.
  - Quando arriva un nuovo dato, ogni SVM lo classifica come appartenente a una delle due classi che sta confrontando.
  - Il risultato finale è determinato dalla **votazione maggioritaria** tra tutti i classificatori.
- **Pro:** Più accurato in certi casi, soprattutto con dati ben separabili.
- **Contro:** Richiede più modelli \((n \times (n - 1) / 2)\), aumentando il tempo di calcolo.

### 2. **One-vs-Rest (OvR):**
- **Come funziona:**
  - Si costruisce un SVM per ogni classe, confrontando quella classe contro tutte le altre. Ad esempio:
    - SVM1: Marco vs (Maria + Renzo).
    - SVM2: Maria vs (Marco + Renzo).
    - SVM3: Renzo vs (Marco + Maria).
  - Quando arriva un nuovo dato, ogni SVM assegna un punteggio alla propria classe, e la classe con il punteggio più alto viene scelta.
- **Pro:** Meno modelli rispetto a OvO (solo \(n\) modelli).
- **Contro:** Può essere meno preciso se le classi non sono ben separate.


## Un Esempio Pratico per OvR

1. **Preparazione dei dati:**
   - Etichettiamo le immagini:
     - Marco = 1, Maria = 2, Renzo = 3.
   - Creiamo tre dataset:
     - Per SVM1: Marco = 1, Maria/Renzo = 0.
     - Per SVM2: Maria = 1, Marco/Renzo = 0.
     - Per SVM3: Renzo = 1, Marco/Maria = 0.

2. **Addestramento:**
   - Addestriamo tre SVM separati, uno per ogni classe.

3. **Classificazione:**
   - Per un nuovo volto, ogni SVM restituisce un punteggio.
   - Scegliamo la classe con il punteggio più alto.
