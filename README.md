# Eines de Google

| Eina | | Propòsit | | Target |
| :---: | | :---: | | :---: |
| Gmail | | Enviem correus per compartir informació | | Persones o empreses | 
| Calendar | | Organitza el teu horari | | Equips i famílies | 
| Drive | | Organitza els teus arxius | | Qualsevol usuari | 
| Docs | | Fer documents | | Estudiants i oficines |
| Maps | | Mapes, rutes i llocs | | Viatgers i empreses |
| Fulls de càlcul | | Organitza despeses | | Families i empreses |

# Diferència entre IMAP I POP3

* **IMAP:** Mantiene los correos en el servidor y los sincroniza entre varios dispositivos (móvil, ordenador, tablet).
* **POP3:** Descarga los correos en un dispositivo y puede eliminarlos del servidor, según la configuración.

# Prova de etiqueta, filtres i resposta automàtica

<img width="1920" height="1080" alt="Captura desde 2026-11-12 14-11-18" src="https://github.com/user-attachments/assets/92805f7e-891c-403f-be24-4027008ad170" />

## Fase 2: Comprovar l'accés

### 1. Estat de l'accés IMAP i paràmetres dels serveis

L'accés **IMAP** es troba **actiu per defecte** al compte educatiu de Google Workspace (Institut Puig Castellar), mentre que l'accés POP està inhabilitat.

| Servei / Protocol | Estat | Servidor | Port | Seguretat / Xifratge | Autenticació |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Correu entrant (IMAP)** | Actiu (habilitat) | `imap.gmail.com` | `993` | SSL/TLS | Sí (OAuth / contrasenya) |
| **Correu sortint (SMTP)** | Actiu | `smtp.gmail.com` | `465` (o `587`) | SSL/TLS (o STARTTLS) | Sí (obligatòria) |
| **Correu entrant (POP)** | Inhabilitat | `pop.gmail.com` | `995` | SSL/TLS | Sí |

<img width="1853" height="961" alt="Captura desde 2026-11-26 10-48-47" src="https://github.com/user-attachments/assets/68204058-77e5-411c-93cd-eba7f2b01c92" />

---

### 2. Enviament entre dues sessions i aplicació d'etiquetes

S'han obert dues sessions simultànies (navegador normal i finestra d'incògnit) i s'ha enviat un missatge complint les condicions del filtre configurat. El correu s'ha rebut correctament i se li ha aplicat automàticament l'etiqueta **`institut`**.

<img width="1913" height="252" alt="Captura desde 2026-11-26 10-58-51" src="https://github.com/user-attachments/assets/17d8e571-e0e9-4c5e-89c0-f77f90a213b6" />


---

### 3. Resposta i verificació de retorn

Des del compte receptor s'ha respost al missatge anterior i s'ha comprovat que la resposta torna correctament a la safata d'entrada del compte original dins el mateix fil de conversa.

<img width="1853" height="961" alt="Captura desde 2026-11-26 10-57-08" src="https://github.com/user-attachments/assets/3775e4c2-9b43-470b-95aa-294501f81a57" />

---

### 4. Anàlisi de la capçalera original (SPF, DKIM i DMARC)

En obrir l'opció **Mostra l'original** d'un dels missatges rebuts, els tres mecanismes d'autenticació mostren el resultat **`PASS`**:

* **SPF (`PASS`):** Verifica que el servidor des d'on s'ha enviat el correu té permís oficial del domini remitent per fer-ho.
* **DKIM (`PASS`):** Confirma mitjançant una signatura criptogràfica que el missatge no ha estat modificat ni alterat durant el trànsit.
* **DMARC (`PASS`):** Certifica que el missatge compleix les polítiques de seguretat del domini en haver superat correctament les validacions SPF i DKIM.

---

### 5. Llista de proves (Checklist)

| Nº | Cas de prova | Acció realitzada | Resultat esperat | Resultat real | Estat |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | Accés IMAP actiu | Revisar *Configuració > Reenviament i correu POP/IMAP*. | L'accés IMAP figura com a actiu. | IMAP actiu per defecte. | OK |
| **2** | Enviament de correu bàsic | Enviar correu del Compte A al Compte B. | El missatge arriba a la safata d'entrada de B. | Rebut correctament. | OK |
| **3** | Resposta de correu | Respondre des del Compte B al missatge d'A. | La resposta arriba al Compte A al mateix fil. | Rebut al mateix fil. | OK |
| **4** | Filtre etiqueta `institut` | Enviar correu amb la paraula clau/remitent del filtre. | S'aplica l'etiqueta `institut` automàticament. | Etiquetat correctament. | OK |
| **5** | Filtre no coincident | Enviar correu normal sense la paraula clau del filtre. | Arriba a Rebuts sense aplicar l'etiqueta `institut`. | Arriba sense etiqueta. | OK |
| **6** | Segon filtre configurat | Enviar correu que compleixi la regla del segon filtre. | S'executa l'acció configurada (destacar/arxivar). | Acció executada. | OK |
| **7** | Resposta automàtica (1r enviament) | Activar resposta automàtica i enviar correu des d'un compte extern. | El remitent rep el missatge automàtic configurat. | Resposta rebuda. | OK |
| **8** | Resposta automàtica (repetició) | Enviar un segon correu seguit des del mateix compte extern. | Gmail no torna a enviar la resposta automàtica (evita spam). | No es repeteix l'enviament. | OK |
| **9** | Resposta automàtica (fora de dates) | Enviar correu fora del rang de dates configurat. | No s'envia cap resposta automàtica. | Sense resposta automàtica. | OK |
| **10** | Autenticació a la capçalera | Obrir *Mostra l'original* en un missatge rebut. | SPF, DKIM i DMARC mostren estat `PASS`. | Tots tres indiquen `PASS`. | OK |

## Fase 3: El viatge a Alemanya (3 - 9 de març de 2027)

* **Ruta a Google Maps (7 dies):** [Veure ruta completa](https://maps.app.goo.gl/vYpNpnaXvZMkmNTD7)
* **Pressupost (Google Sheets):** [Veure full de càlcul](https://docs.google.com/spreadsheets/d/15Hx6Cryi21U2MsU5gEiiFSfL6VXLl1kCabi9r5NB78I/edit?usp=sharing)
* **Calendari (Google Calendar):** [Veure calendari del viatge](https://calendar.google.com/calendar/u/0?cid=Y19kZjI3YjczMjJjMWQ5MGJiNzNjMjQ2ZWU5OWM5YTlkZDBiMDVhY2YxZTAzZDQwZTA5NzNkNDc3OTViOGVmYTcyQGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20)

### Convidat al Calendari
<img width="773" height="160" alt="Captura desde 2026-11-26 13-16-16" src="https://github.com/user-attachments/assets/92969de8-472f-49a8-9b1a-d05b2e155069" />

### Tasques que fer

<img width="674" height="357" alt="Captura desde 2026-11-26 13-27-02" src="https://github.com/user-attachments/assets/319fa98e-7641-45cd-9da3-7aaecc0bdfeb" />
