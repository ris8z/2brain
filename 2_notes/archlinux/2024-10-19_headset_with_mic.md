---
date: 2024-10-19 
tags: 
    - archlinux
---

# headset_with_mic
1. Open pavucontrol
    Si aprirà la finestra del controllo del volume di PulseAudio.

2. Configurazione dell'uscita audio (cuffie):

    Vai alla scheda "Output Devices" (Dispositivi di Uscita).
    Nella lista dei dispositivi, dovresti vedere le tue cuffie elencate.
    Se le cuffie non sono selezionate, clicca sull'icona a forma di menu a tendina accanto al dispositivo e seleziona le tue cuffie come dispositivo predefinito.
    Verifica che il volume delle cuffie sia impostato correttamente.

3. Configurazione del microfono (input):

    Vai alla scheda "Input Devices" (Dispositivi di Ingresso).
    Nella lista dei dispositivi, dovresti vedere il microfono delle cuffie elencato.
    Se non è selezionato, clicca sul menu a tendina accanto al dispositivo e imposta il microfono delle cuffie come predefinito.
    Verifica che il volume del microfono sia adeguato, e aumenta il livello di input se necessario.

4. Verifica il Profilo Audio:

    Vai alla scheda "Configuration" (Configurazione).
    Trova il dispositivo delle cuffie nella lista dei profili e assicurati che sia selezionato un profilo che supporti sia uscita (cuffie) che ingresso (microfono).
    Un profilo come "Analog Stereo Duplex" o "Headset Head Unit (HSP/HFP)" è ideale, in quanto supporta sia il microfono che le cuffie.

5. Testare le cuffie e il microfono:

    Vai alla scheda "Recording" (Registrazione) mentre stai usando un'applicazione che richiede il microfono (come un software di chat o registrazione vocale).
    Verifica che il microfono delle cuffie venga rilevato e che il livello di input sia visibile.
    Puoi fare un test del microfono utilizzando strumenti come Audacity o la funzione di test del microfono in un'applicazione di chat come Discord.
