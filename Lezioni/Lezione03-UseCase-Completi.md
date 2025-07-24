\# Lezione 3: Use Case Diagrams Completi



\## 🎯 Obiettivi

\- Padroneggiare le 4 relazioni tra use cases

\- Creare diagrammi Use Case professionali

\- Applicare le relazioni al progetto biblioteca

\- Gestire layout e chiarezza visiva



\## 🔗 Le 4 Relazioni Fondamentali



\### 1. INCLUDE - Sempre Obbligatorio 🔴

\*\*Significato\*\*: Per fare A, devi SEMPRE fare anche B

\*\*Esempio\*\*: Per prenotare libro → DEVI fare login

```plantuml

BOOK .> LOGIN : include

\\###2. EXTEND - Opzionale ⭐

\\\*\\\*Significato\\\*\\\*: A volte, se vuoi, puoi fare anche B

\\\*\\\*Esempio\\\*\\\*: Quando cerchi → PUOI filtrare per anno



## FILTER .> SEARCH : extends



###3. ENABLE - Prerequisito 🟢

Significato: A deve finire PRIMA che B possa iniziare

Esempio: Docente suggerisce → POI bibliotecario può decidere

plantumlSUGGEST .> DECIDE : enable



###4. FEED INTO - Arricchisce 🟠

Significato: A fornisce informazioni utili a B

Esempio: Suggerimenti docente migliorano decisioni bibliotecario

plantumlSUGGEST .> DECIDE : feed into

🎭 Gerarchia Attori con Ereditarietà

Principio: Utente Sistema base con specializzazioni



Tutti gli utenti ereditano capacità di login

Ogni specializzazione ha funzioni specifiche



plantumlactor "Utente Sistema" as BASE

actor "Studente" as ST

BASE <|-- ST

BASE --> LOGIN

ST --> SEARCH

🎨 Best Practices Layout

Problemi Comuni



Package troppo stretti e lunghi

Relazioni sovrapposte e confuse

Troppo testo nei nomi



###Soluzioni



Nomi compatti nei package

Use cases essenziali

Colori per distinguere relazioni

Legenda per chiarezza



###📊 Progetto Biblioteca - Caso Completo

File: Diagrammi/lezione3-completo.puml



##Attori e Ruoli



Utente Sistema: Login base

Studente: Ricerca e prenotazione

Bibliotecario: Gestione fisica + acquisti

DSGA: Approvazione budget

Docente: Suggerimenti e valutazioni



##Flussi Principali



Autenticazione: Tutti devono fare login

Ricerca/Prenotazione: Studenti cercano e prenotano

Gestione Fisica: Bibliotecario usa robot per ricollocazione

Processo Acquisti: Docente → Bibliotecario → DSGA



🎯 Risultati Lezione

✅ 4 relazioni UML padroneggiate

✅ Gerarchia attori corretta

✅ Layout ottimizzato e leggibile

✅ Use Case completo progetto biblioteca

✅ Best practices per diagrammi professionali

📝 Esercizi



Identificare altre relazioni nel sistema biblioteca

Creare use case per sistema di notifiche

Progettare gerarchia per diversi tipi di libri


