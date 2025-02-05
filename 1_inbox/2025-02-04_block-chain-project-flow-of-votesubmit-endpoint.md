---
date: 2025-02-04 
tags: 
    - blockchain
hubs: 
    -   "[[]]"
urls:
    -
---

# block chain project flow of votesubmit endpoint

Flusso Completo con ZKP e Pedersen Commitment

    Crittografia dei Dati (Client-Side):
        L'utente cifra:
            candidate_id con la chiave pubblica dell'elezione.
            numero_voti con la chiave pubblica dell'elezione.
            costo (voti²) con la propria chiave pubblica.
        L'utente genera Pedersen Commitments per:
            candidate_id
            numero_voti
            costo

    Generazione delle Prove ZKP (Client-Side):
        Set Membership Proof: Prova che il candidate_id appartiene ai candidati validi.
        Credit Proof: Prova che il costo è corretto e non supera i crediti disponibili.
        Le prove ZKP sono legate ai dati cifrati tramite i Pedersen Commitments, assicurando che le prove siano valide per quei dati specifici.

    Invio al Server:
        Il client invia:
            I dati cifrati (candidate_id, numero_voti, costo).
            I Pedersen Commitments.
            Le prove ZKP.

    Verifica e Aggiornamento dei Crediti (Server-Side):
        Il server verifica:
            I Pedersen Commitments per legare le prove ai dati cifrati.
            Le prove ZKP per assicurarsi che il candidato sia valido e che l'utente abbia abbastanza crediti.
        Se tutto è valido:
            I crediti cifrati vengono aggiornati omomorficamente.
            Il voto cifrato viene registrato sulla blockchain.

