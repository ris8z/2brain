---
date: 2025-02-20 
tags: 
    - https
---

# https with duckDNS and Lets encrypt su ec2

## Registra un dominio gratuito su DuckDNS

- Vai su DuckDNS e accedi con GitHub/Google.
- Nella sezione "Domains", scegli un nome per il tuo sottodominio (es. mio-backend.duckdns.org).
- Inserisci il tuo IP pubblico EC2 (lo trovi nella console AWS).
- Clicca "Add Domain" → Il tuo dominio è ora attivo! 🎉


## Installa Certbot su EC2

Ora dobbiamo installare Certbot, lo strumento che genera il certificato HTTPS gratuito con Let’s Encrypt.
```bash
sudo apt update && sudo apt install certbot python3-certbot-nginx -y

```

## Configura Nginx per usare DuckDNS

Se non hai già Nginx installato:

```bash
sudo apt install nginx -y

```

Ora crea un file di configurazione per il tuo dominio:

```bash
sudo nano /etc/nginx/sites-available/flask
```

Incolla questo:
```nginx
server {
    listen 80;
    server_name mio-backend.duckdns.org;

    location / {
        proxy_pass http://localhost:5000;  # Il tuo backend Flask in Docker
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
Salva (CTRL+X, Y, INVIO) e abilita il sito:

```bash
sudo ln -s /etc/nginx/sites-available/flask /etc/nginx/sites-enabled/
sudo systemctl restart nginx
```
Ora il tuo backend è accessibile su http://mio-backend.duckdns.org.

## Ottieni un certificato SSL con Let’s Encrypt

Ora generiamo il certificato HTTPS:

```bash
sudo certbot --nginx -d mio-backend.duckdns.org
```

Segui le istruzioni e scegli l'opzione per forzare il redirect HTTPS. Se tutto va bene, vedrai "Congratulations! Your certificate is now active." 🎉

Prova ad accedere: https://mio-backend.duckdns.org 

## Configura il rinnovo automatico del certificato

Let’s Encrypt scade ogni 90 giorni, quindi impostiamo un cron job per rinnovarlo automaticamente:

```bash
sudo crontab -e

```
Aggiungi questa riga in fondo:

```bash
0 3 * * * certbot renew --quiet && systemctl reload nginx
```

Questo comando eseguirà il rinnovo ogni notte alle 3:00. 🌙


## Se us ec2 su aws apri na porta per http e https
