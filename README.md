# TwincatTestRepo

Repo di prova per TwinCat3, vedi:

[Jakob Sagatowski - PLC programming using TwinCAT 3 - Version control (Part 13/18)](https://www.youtube.com/watch?v=1g6eYnlzKtA&t=345s&ab_channel=JakobSagatowski)

## file .gitignore completo anche per HMI:
[Westwood85/gitignore-for-twincat-3](https://github.com/Westwood85/gitignore-for-twincat-3/blob/main/.gitignore)

fai una copia del file `.gitignore` direttamente nella cartella del progetto Twincat, quella che contiene anche la cartella `.git`

---

## Comparazione tra file

TwinCat3 memorizza i propri file in un formato XML. 
Per rendere più agevole il confronto tra versioni differenti dello stesso file (vedi comando _git diff_ ) Beckhoff mette a disposizione un tool di comparazione file.

Per attivarlo:

1. dalla tray area, selezionare col tasto **destro** l'icona di TwinCat3 e scegliere la voce **Tools > TwinCat Project Compare**

2. si apre la finestra di *TwinCAT 3.x Project Compare*

3. dal suo menu **Tools** scegliere **Configure user tools...**

4. click sul pulsante **Export Configuration**, selezionare il plugin **GIT** e confermare con **OK**

5. Il tool a questo punto dovrebbe aver trovato il percorso del file di configurazione *globale* di GIT, ad esempio `C:\Users\utente\.gitconfig`, altrimenti cercarlo manualmente tramite il pulsante **Browse**. Confermare con **OK**

6. se i permessi di scrittura sono attivi, il tool scrive alcune informazioni nel file `C:\Users\utente\.gitconfig` e ne da conferma col messaggio `Export to GIT successfully done!`. confermare con **OK**

7. premere ancora **OK** per chiudere tutti i pop-up, poi chiudere la finestra di *TwinCAT 3.x Project Compare*

Da questo momnto in poi, verrà utilizzato lo strumento *TwinCAT 3.x Project Compare* ogni volta che, dalla finestra di Team Explorer, si intende visualizzare le **differenze** tra la versione attuale e la precedente di un file: fare **click destro** sul file e selezionare **Confronta con versione non modificata...**

---

## Configurazione _fine_ dell'ambiente TwinCAT3

### 1. Eliminazione delle voci `LineIds` dal file sorgente XML

* dall'IDE TcXaeShell, selezionare il menu **Strumenti** (o *Tools* ) e poi **Opzioni** ( o *Options*)

* Selezionare l'opzione **TwinCAT > PLC Environment > Write options** ed impostare a **True** la voce *Separate LineIDs*. Inquesto modo le voci `LineIds` vengono salvate in un altro file, distinto dal file del codice sorgente, che sarà escluso dalle operazioni di version control. Confemare con **OK**

### 2. Abilitare l'uso di file multipli per la configurazione di sistema

Di default TwinCAT3 salva in un unico file tutte le informazioni di configurazione di sistema. Ciò è scomodo per una efficiente gestione del versioning. E' preferibile imporre a TwinCAT3 l'uso di file multipli per le singole parti.

* dall'IDE TcXaeShell, selezionare il menu **Strumenti** (o *Tools* ) e poi **Opzioni** ( o *Options*)

* Selezionare l'opzione **TwinCAT > XAE Environment > File settings** ed impostare a **True** tutte le voci in elenco. Confemare con **OK** e poi riavviare l'IDE.

