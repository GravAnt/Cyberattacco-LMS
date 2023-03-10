# Attacco a un servizio di Learning Management System
Questa è una simulazione di attacco realizzata come progetto per il corso di Sicurezza Informatica del CdL di Informatica e Comunicazione Digitale (Università degli Studi di Bari).
Tutti gli script sono stati utilizzati in rete locale, in un ambiente controllato, per scopi didattici. Non si assume alcuna responsabilità per eventuali utilizzi delle tecnologie adoperate.

Lo scenario di attacco è un ambiente scolastico/universitario in cui ogni corsista può accedere a Chamilo
(versione 1.11.16) utilizzando il PC messo a disposizione dalla struttura, connesso alla rete locale. Ogni 
dispositivo ha Windows 7 come sistema operativo.
L’obiettivo del Red Team è l’ottenimento dei dati dei dispositivi scolastici usati dagli studenti attraverso le 
tecniche di attacco riportate in seguito.

L’attacco prevede l’infezione dei dispostivi utilizzati dagli studenti mediante il caricamento di un file <b>PDF 
malevolo</b>, che dev’essere aperto dalla vittima utilizzando Adobe Reader (versione 8.X o 9.X).
L’attacco richiede la messa in pratica di tecniche di <b>social engineering</b> per rendere gli studenti più propensi a 
scaricare il PDF malevolo. Per questo, entrare nell’account di un docente è essenziale: i file caricati dai docenti 
sono contenuti didattici o avvisi che devono essere scaricati dagli studenti; quindi, il PDF con payload potrebbe 
essere spacciato come, ad esempio, l’elenco degli appelli d’esame. In questo momento, quindi, l’attaccante deve 
fingersi docente, in modo da avere la fiducia degli studenti.
Per poter entrare nell’account di un docente si potrebbero utilizzare varie tecniche, come il <b>bruteforce</b>.

Durante lo scaricamento del PDF malevolo, gli studenti potrebbero essere avvisati dall’antivirus del dispositivo 
che stanno utilizzando, per cui è fondamentale avere un’opzione di attacco alternativa: oltre al PDF, l’attaccante 
caricherà in piattaforma un link per accedere a Google Drive, da cui poter scaricare il file nel caso in cui ci siano 
problemi di download. In realtà, questo è un link di <b>phishing</b> che conduce a una falsa pagina di login in cui le 
vittime inseriranno le loro credenziali, inviandole involontariamente all’attaccante.

In tutte le fasi di attacco è fondamentale il mascheramento dell’indirizzo MAC, assegnato univocamente dal 
produttore ad ogni scheda di rete. L’indirizzo MAC, infatti, può essere utilizzato per risalire al tipo di dispositivo 
connesso, per cui l’attaccante rischierebbe di essere identificato. Inoltre, l’amministratore di rete può bannare 
un dispositivo dalla rete aggiungendo il suo indirizzo MAC in una blacklist.
Per poter svolgere l’attacco è quindi essenziale l’utilizzo di un software che permette il cosiddetto <b>MAC 
spoofing</b>.
