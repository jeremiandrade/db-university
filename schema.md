 Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.



# Table Uni:

- id 
- nome_studente
- cognome_studente
- dipartimenti 
- corsi di laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- insegnanti
- esito_voto


# Table dipartimento
- id
- dipartimenti



# Table corsi di laurea
- id 
- corso_di_laurea
- id_dipartimento FK



#  Table corsi 
- id
- corsi
- id corsi_di_laurea FK



# Table studente
- id
- nome_studente
- cognome_studente
- id corsi_di_laure

# Table esito_voto
- id
- esito voto
- id corso FK
- id studente FK


# Table insegnanti 
- id
- insegnanti
- id corso KF





