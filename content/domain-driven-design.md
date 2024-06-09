---
title: Perchè usare il Domain Driven Design?
---

# Ma cos'è il Domain Driven Design (DDD)?

Un concetto difficile da spiegare che non puo' essere sintetizzato in una frase ma ci provo lo stesso: 
Il DDD è un approccio di modellazione del software che punta a dividere il codice in categorie cercando di mettere sulla stessa lunghezza d'onda tecnici e non tecnici definendo un linguaggio comune.

In questo modo si progetta il codice attorno ai requisiti funzionali e non viceversa come spesso accade.

## Cos'è il dominio?

Un dominio è quello che definiremmo la materia che tratta l'azienda. Per esempio *shop online*, *gestione denaro* ecc.

Quindi il dominio e' la materia che contiene il business. In pratica, molto spesso accade che un'azienda tratti più materie insieme oppure che le materie siano molto generiche.

## Bounded Context

Per poter scomporre un dominio il DDD ci mette a disposizione quelli che sono chiamati *Bounded Context* ossia dei contenitori con un proprio specifico linguaggio.

Potremmo vedere i *Bounded Context* come delle nazioni ognuna con la propria cultura e la propria lingua.

Con questa scomposizione un dominio diventa piu' gestibile rispetto ad essere un grande impero di cui poi si perde pezzi per strada (come l'impero romano).

Quindi la vera chiave che permette al Domain-Driven Design di essere cosi di successo e' che si stabilisce un linguaggio comune tra sviluppatori e gli esperti del dominio.
Molte parole infatti hanno diversi significati a seconda del contesto ed e' importante esplicitare il significato di un certo concetto all'interno del contesto.

Per esempio *client* potrebbe assumere diversi significati:

- Colui che usufruisce di una chiamata API
- Un utente che fa il login all'interno dell'applicazione

E' importante quindi avere un linguaggio comune e accordato tra gli addetti ai lavori.

Qualche volta questi *buonded context* avranno bisogno di comunicare tra di loro per scambiarsi certe informazioni, ma come facciamo se questi usano lingue diverse? 
Utilizziamo quello che si chiama un *Anti-Corruption Layer* cioe' colui che si occupa di tradurre i diversi linguaggi, una specie di interprete. 
Generalmente l'*Anti-Corruption Layer* e' implementato da design pattern come l'*Adapter* o il *Facade*.


## Oggetti

Quando si sta possiamo avere due tipi di oggetti:
- Entity Object: sono gli oggetti che sono identificati univocamente da un attributo. Es. *Utente* e' identificato da *userId: 1234a*. Quindi nonostante cambino poi gli altri suoi attributi, sappiamo comunque riconoscerlo grazie al suo *id*.
- Value Object: sono gli oggetti che contengono informazioni che non sono identificate univocamente da un attributo. In questo caso gli oggetti che hanno gli stessi valori degli attributi sono considerati lo stesso oggetto. Es. *Indirizzo* sara' formato da *via*, *citta'*, *CAP* se avessimo due indirizzi con la stessa via, citta' e CAP si tratterebbe dello stesso indirizzo.

Gli *Entity Object* sono importanti nella modellazione del DDD perche' si utilizzano per tracciare comportamento e stato che cambiano nel tempo. Infatti quest'ultimi sono degli oggetti mutabili mentre i *Value Object* sono immutabili.

Qualcuno avra' gia' intuito che questi due costrutti si sposano bene con la programmazione ad oggetti (OOP). Non necessariamente pero' siamo limitati ad utilizzare questo tipo di programmazione sicuramente pero', risulta intuitivo farlo.


Puo' capitare che ci siano delle relazioni molto complesse tra le entita' e quindi ogni volta che bisogna utilizzarle insieme puo' risultare difficile comprenderle. In questo caso, si puo' ricorrere agli *Aggregates* che sono delle entita' composte che semplificano l'accesso e rendono piu' comprensibile il modello.

Sono presenti altri concetti nel DDD come *Repository*, *Service*,  *Modules*. Quest'ultimi in realta' sono abbastanza intuitivi per qualcuno che ha gia' fatto programmazione in un qualche framework MVC in queanto essi si usano spesso.
