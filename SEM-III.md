### Oppgave 1.1

a) ![alt text](image.png)

b) ![alt text](image-1.png)

c)
1. ### Protokoller 
    HTTP og TCP protokoller

2. ### 3-veis-hilsen TCP 
    - Klienten sender først en SYN segment (Synchronize Sequence Number) for å etablere en kobling til serveren.
    - Deretter svarer serveren med et (SYN + ACK) segment for å anerkjenne klienten.
    - Til slutt svarer klienten med å anerkjenne svaret til klienten og deretter etablere en stabil forbindelse mellom klient og server.

    ![alt text](image-2.png)
    (SYN - SYN+ACK - SCK)

3. ### Avslutning av TCP sesjon
    - Klient sender et FIN segment for å fortelle serveren at den ønsker å avslutte forbindelsen.
    - Server svarer med FIN og ACK for å anerkjenne.
    - Klient svarer med ACK, og avslutter forbindelsen.
    ![alt text](image-3.png)

### Oppgave 1.2

a) ![alt text](image-4.png)
![alt text](image-5.png)

b) ![alt text](image-7.png)

c) ![alt text](image-6.png)
Her er det flere likheter, fra 3-veis-hilsen til FIN avslutning. Forskjellen er flere `keep-alive` TCP forespørsler i nettleseren.

--- 

### Oppgave 2.1

a) ![alt text](image-8.png)

b) ![alt text](image-9.png)
(1.2, 2.1)


### Oppgave 2.2

a) Man kan bruke `docker container commit ex02-wordpress-1` for å ta vare på forandringer.

b) I denne fangsten kan man se at serveren kommuniserer med databasen (MySQL)
![alt text](image-12.png)

---

### Oppgave 3
![alt text](image-11.png)

TLS blir brukt av HTTPS for kryptering. 
TLS pakkene har hilsninger i protokollene.
![alt text](image-10.png) Man ser ikke hva som blir servert over https.

TCP pakkene viser både kilde-port og destinasjons-port. Man kan også se hvilke flag (ACK) den sender.

De andre pakkene i fangsten er DNS for å løse nettaddressen til en IP adress. 