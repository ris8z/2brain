---
date: 2024-10-15 
tags: 
    - interview
---

# hubspot_interview

## First working solution, than optimize code ecc

## What do I need to know?

### The basics off http and APIs

#### How one would communicate with an api using (GET,POST) methods
using request in python3
```python
response = request.get(url)
response = request.post(url, json=data)

response.status_code    #status code
response.json()         #ottieni i dati in json quindi python dict
response.text           #ottini i dati come stringa di testo
response.headers        #accede agli header della riposta (un dict)
response.content        #ottine il contenuto in bin
```
#### How you would interpret Http status code, 

##### 2xx - Successo
- 200 **Ok** la richiesta e' andata a boun fine e il server ha restituito i dati richesti
- 201 **Creadted** la richiesta e' andata a boun fine e ha portato alla creazione di una nuova risorsa
- 203 **No Content** la richiesta e' andata a boun fine ma non c'e' contentuto da restituire
##### 3xx - redirezioni 
- 301 **Moved Permanetly** risorsa spostata a un altro url 
- 302 **Found** risorsa temporanemaente spostata a un altro url 
- 304 **Not Modified** risorsa non e' stata modificata
##### 4xx - errori del client 
- 400 **bad request** sintax error or invalid data in the request
- 401 **Unauthorized** authentication not valid or not given
- 403 **Forbidden** richiesta compresa ma il server si rifiuto (no autroizzazione) 
- 404 **Not Found**

##### 5xx - errori del server 
- 500 *Internal server error* e' espoloso il server

### The JSON data format 
#### Serealize from object to json
```python
import json
data = {'name':'peppe', 'age':21}

json_string = json.dumps(data)
```
#### Deserealize from json to object 
```python
import json
json_string = "{'name':'peppe', 'age':21}"

data = json.loads(json_string)
```

### Commond data structures - arrays, sets, maps
Up to me

