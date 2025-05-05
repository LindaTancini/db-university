# DB UNIVERSITY

## ESERCIZIO

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:

- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
  Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.
  Utilizzare https://www.drawio.com/ per la creazione dello schema.
  Esportare quindi il diagramma in jpg e caricarlo nella repo.

  ## SPIEGAZIONE DELLE RELAZIONI

  - **Dipartimento → Corsi di Laurea** = Un Dipartimento può avere più corsi di Laurea, ma ogni corso di Laurea appartiene a uno solo dipartimento. **(UNO A MOLTI)**
  - **Corso di Laurea → Corsi** = Ogni corso di Laurea offre più corsi, ma ogni corso appartiene a uno solo corso di Laurea. **(UNO A MOLTI)**
  - **Studenti → Corsi di Laurea** = Ogni studente è iscritto a uno solo corso di Laurea, ma ogni Corso di Laurea ha più Studenti. **(UNO A MOLTI)**
  - **Corso ↔ Corsi Insegnanti ↔ Insegnanti** = Un corso può essere tenuto da più insegnanti, e un insegnante può tenere più corsi. **(MOLTI A MOLTI)**
  - **Corso → Appelli** = Ogni corso ha più appelli, ma ogni appello ha un solo corso. **(UNO A MOLTI)**
  - **Studente ↔ Appelli** = Uno studente può iscriversi a più appelli, e l'appello può avere più studenti. **(MOLTI PER MOLTI)**
  - **Studente ↔ Appelli D'Esame** = Uno studente puà iscriversi a più appelli d'esame, e l'appello d'esame può avere più studenti **(MOLTI PER MOLTI)**
