# Project Title
UnlockPA, l'assistente virtuale per i comuni

# Project Description
UnlockPA consente di fornire a diversi comuni un assistente virtuale in
grado di rispondere a domande legate alla gestione della pandemia COVID19
e domande generiche relative alle attività del comune.
Le categorie disponibili sono:
- 😷 Covid
- 🚌 Mobilità
- 🙋 Segnalazioni
- 👐 Volontariato
- ✏️ Scuola 
- 🌲 Ambiente 
- 🏢 Uffici comunali
- 👩‍⚕️ Salute 
- 🏀 Sport
- 🎻 Cultura e servizi
- 📋 Tributi

Il sistema è nativamente multi-tenant e consente di gestire più comuni su
una sola istanza. Il modello di riconoscimento delle domande è comune
mentre le risposte sono configurabili per ogni comune.

Il sistema è suddiviso nei seguenti componenti:
 - [db](https://github.com/csipiemonte/unlockpa-db): contiene lo schema del database e gli script di installazione
 - [chatcontrolapi](https://github.com/csipiemonte/unlockpa-chatcontrolapi): api per verifica disponibilità bot su dominio 
 - [csibot](https://github.com/csipiemonte/unlockpa-csibot): componente che contiene:
    - un'api che riconosce una FAQ a partire da una domanda 
    - un'api di gestione per l'addestramento del modello
 - [unlockbotrasa](https://github.com/csipiemonte/unlockpa-unlockbotrasa): api che utilizza soluzione rasa (rasa.org) per identificare frase di uso comune
 - [backoffice](https://github.com/csipiemonte/unlockpa-backoffice): applicazione web di backoffice
 - [examplewebsite](https://github.com/csipiemonte/unlockpa-examplewebsite): esempio di comune fruitore e proxy dei servizi esposti necessari


# Getting Started and Installing
Per installare il sistema in locale e configurare il primo comune in grado di rispondere alle domande configurate 
è possibile seguire i seguenti passi:
 * scaricare tutti i 6 i componenti all'interno di una directory
 * avviare tramite docker-compose la componente unlockDB
 * avviare tramite docker-compose la componente chatcontrolapi
 * avviare tramite docker-compose la componente csibot
 * seguire le istruzioni sul README.md di csibot per caricare il file excel con il modello di esempio 
   ed aggiornare il chatbot rispetto a tale modello (reboot)
 * avviare tramite docker-compose la componente lockbotrasa
 * avviare tramite docker-compose la componente unlockbackoffice
 * loggarsi sul backoffice e :
   * censire un comune associato al dominio localhost
   * inserire la risposta ad alcune domande e validarle
 * avviare tramite docker-compose la componente webchat
 * provare la soluzione da http://localhost


# Versioning
Per la gestione del codice sorgente viene utilizzata la metodologia (http://semver.org)

# Authors
Gli autori sono:
* Claudio Parodi
* Fabio Di Ninno
* Dario Milanese
* Sergio Austa
* Maurizio Dipierro
* Stefano Giorgi

# Copyrights
(C) Copyright 2020 CSI Piemonte

# License
SPDX-License-Identifier: Licensed under the EUPL-1.2-or-later
See the LICENSE.txt file for details
