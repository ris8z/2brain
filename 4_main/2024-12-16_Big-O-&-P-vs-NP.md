---
date: 2024-12-16 
tags: 
    - CA320
hubs: 
    -   "[[2024-12-14_Computability-&-Complexity|Computability & Complexity]]"
---

# Big O & P vs NP
 
## Big O Notation:

Misura il tasso di crescita del tempo o spazio richiesto da un algoritmo al crescere della dimensione dell’input.
Si ignorano costanti e termini più piccoli, concentrandosi sull’andamento generale.

## Classi di Complessità:
P: Problemi decisionali risolvibili in tempo polinomiale da una macchina di Turing deterministica.
NP: Problemi decisionali in cui una soluzione, se fornita, può essere verificata in tempo polinomiale da una macchina di Turing deterministica.
Se esistesse un algoritmo veloce (polinomiale) per risolvere un problema NP-completo, allora tutti i problemi in NP sarebbero risolvibili in tempo polinomiale.
NP-Complete:

## Sottoinsieme di NP.
Ogni problema in NP può essere ridotto in tempo polinomiale a un problema NP-completo.
Se trovi una soluzione polinomiale per un NP-completo, risolvi l’intera classe NP in tempo polinomiale.

## Teorema di Cook-Levin:
Dimostra che SAT (Soddisfacibilità di formule booleane) è NP-completo.
Ogni problema in NP si può trasformare in un’istanza di SAT in tempo polinomiale.
Questo ha identificato SAT come il primo problema NP-completo.

## P vs NP:
Problema aperto: non si sa se P = NP oppure no.
Se P = NP, si troverebbero algoritmi efficienti per tutti i problemi NP-completi, rivoluzionando la computazione.
La maggior parte dei ricercatori ritiene P ≠ NP, ma non esiste una prova formale.

