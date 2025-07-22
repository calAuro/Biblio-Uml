# Lezione 2: Principi SOLID

## 🎯 Obiettivi
- Capire perché il codice "tutto in una classe" diventa problematico
- Single Responsibility Principle (S)
- Open/Closed Principle (O)

## 💡 Problema Iniziale
Classe BibliotecaManager che fa tutto: gestione libri + database + email + log
**Rischio**: Se cambi una parte, rischi di rompere tutto

## ✅ Soluzione S - Single Responsibility
Una classe = una responsabilità
- GestoreLibri (solo gestione)
- DatabaseLibri (solo persistenza)  
- NotificatoreEmail (solo comunicazioni)

## ✅ Soluzione O - Open/Closed
Esempio: Sistema tariffe biblioteca
- Invece di if-else giganti
- Interfaccia CalcolatoreTariffa + classi specifiche
- Aggiungere nuovi tipi = zero rischi per codice esistente

## 🎯 Applicazione Progetto Biblioteca
- Strategie di ricerca libri
- Calcolatori tariffe utenti
- Gestori notifiche diverse
## ✅ Principio D - Dependency Inversion
**Problema**: Classi importanti dipendono da dettagli tecnici
**Soluzione**: Dipendere da interfacce, non da implementazioni concrete

### Esempio Biblioteca
```java
// Interface
interface DatabaseLibri {
    void salvaLibro(Libro libro);
}

// Implementazioni
class MySQLDatabase implements DatabaseLibri { ... }
class SQLiteDatabase implements DatabaseLibri { ... }

// Classe principale usa interface
class GestoreLibri {
    private DatabaseLibri database; // Flessibile!
}
