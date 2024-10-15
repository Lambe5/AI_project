# progettoAI
Progetto AI 2023 
IPOTESI: Una casa ha due tipi di prezzi, uno legato alle sue caratteristiche strutturali (prezzo reale) e uno legato alle sue caratteristiche non strutturali (prezzo stimato dall'utente).
Prese in considerazione caratteristiche non strutturali come le recensioni, i tipi di servizi e la luminosità dell'immagine della casa quali di queste influisce maggiormente nella variazione del prezzo della casa nel tempo?
(IMPORTANTE: possiamo scegliere un singolo dato non strutturale come molteplici nella nostra ipotesi, non abbiamo obblighi di nessun tipo)
ORGANIZZAZIONE DEL PROGETTO: Il problema non è più tanto quello di stimare il prezzo ma di costruire un dataset che venga incontro alla nostra ipotesi, quindi:
  1. Possiamo effettuare una clasterizzazione (K-mean) sulle caratteristiche strutturali e fingere che le case con stesse caratt. ma prezzi e recensioni diverse siano la stessa in periodi diversi
  2. Poi possiamo vedere come il/i dai non struttu. hanno influenzato quel prezzo, per esempio vedendo se in quel periodo sono aumentate le recensioni positive, oppure se l'host ha aggiunto nuovi servizi
  3. Possiamo anche vedere se la "stessa casa" ma con immagini diverse ha un prezzo stimato dall'utente diverso
  4. Possiamo vedere alla fine quali di questi dati non strutt. abbia il maggior impatto

(IMPORTANTE: Anche se otteremo un dataset piccolo va bene lo stesso, ciò che importa davvero sono le ipotesi che facciamo durante la creazione di esso)

(ACCORGIMENTI: a seconda di come si processa la colonna delle Amenities dobbiamo stare attenti a quando effettuare lo split, prima o dopo il processamento, nel caso di TF-IDF dobbiamo prima dividere il dataset e poi eseguire TF-IDF in ogni parte suddivisa)

IDEA PROCEDIMENTO: Una volta pulito i tre dataset e fatto il clustering in ognuno di loro si potrebbeero estrarre le abitazioni più simili tra loro presenti nei vari cluster e inserirle in un nuovo dataset che verrà poi utilizzato per fare l'analisi finale.
In questo dataset finale dovremo aggiungere delle nuove colonne per salvare nella stessa riga i vari valori che sono cambiati nel tempo per la "stessa" abitazione. Per esempio, noi troviamo due abitazioni che appartangono allo stesso cluster e che hanno delle caratteristiche strutturali uguali (o quanto più possibile simili) allora potremo ottenere una riga di questo tipo:

neighbourhood  neighbourhood_cleansed  beds  ...  number_of_reviews_t1 number_of_reviews_t2 review_scores_rating_t1 
Florence       Centro Storico          2          0                    100                  0

review_scores_rating_t2 ...  price_t1  price_t2
4.7                          86        92
# Avvio del progetto
1. eseguire tutto il file "CleanDatasets.ipynb"
2. eseguire tutto il file "CreateOurDataset.ipynb"
3. eseguire tutto il file "amenities.ipynb"
