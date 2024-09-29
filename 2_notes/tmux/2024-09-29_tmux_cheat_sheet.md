---
date: 2024-09-29 
tags: 
    - tmux
---

# tmux_cheat_sheet

tmux consist of 3 main objects:

session{
        windows{
            panes
        }
}

session contains one or more windows (but you can attach to one at time)

windows are container for one or more panes (they are like tabs)

panes are the splits in the window, and reappresnt individual terminal session




CHEAT SHEET:

Riconnettersi a una sessione esistente:
tmux attach


Elencare tutte le sessioni:
tmux ls


Uscire da tmux:
exit
Oppure usa la combinazione di tasti Ctrl+d per chiudere il pane attivo o uscire dalla sessione.


Dividere in orizzontale (schermo in alto e in basso):
Ctrl + b, "


Dividere in verticale (schermo a sinistra e destra):
Ctrl + b, %


Chiudere un pane:
Ctrl + b, x


Creare una nuova finestra:
Ctrl + b, c


hiudere una finestra:
Ctrl + b, &


Rinominare una finestra:
Ctrl + b, ,


Creare una nuova sessione:
tmux new -s nome_sessione


Scollegarsi da una sessione senza chiuderla:
Ctrl + b, d

Attaccarsi a una sessione esistente:
tmux attach -t nome_sessione


Elencare tutte le sessioni:
tmux ls


Cambiare il nome di una sessione:
Ctrl + b, $


Uccidere una sessione:
tmux kill-session -t nome_sessione


Copiare nel buffer (modalità copia):
Ctrl + b, [


Incollare dal buffer:
Ctrl + b, ]


Scorrere lo schermo (scroll):
Ctrl + b, [
Poi usa le frecce per scorrere su e giù.
