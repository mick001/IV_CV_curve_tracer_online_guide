# IV & CV Curve Tracer online guide
A set of operational guides for the IV &amp; CV curve tracer (V. 2.0).

![Intro image](https://user-images.githubusercontent.com/13961654/31069802-3e11ed88-a75e-11e7-806d-aac4084c591b.png)

---
---

## What to do

+ Leggere il [changelog](https://github.com/mick001/IV-CV-Curve-Tracer-online-guide/blob/master/changelog.md).
+ Ottenere il [file Excel](https://github.com/mick001/IV-CV-Curve-Tracer-online-guide/blob/master/TEST_CHECKLIST.xlsx) contenente le procedure di test da effettuare dopo ogni modifica sostanziale dell'applicazione al fine della verifica del corretto funzionamento della stessa.
+ Leggere la [guida operativa](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#cosa-contiene-questa-guida) dell'applicazione.
+ Visualizzare [esempi di misure effettuate](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#esempi-di-misure-effettuate).

---
---

## Cosa contiene questa guida

+ [**Impostazione della working directory.**](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#impostazione-della-working-directory-sezione-52-del-manuale)
+ [**Tracciamento curva IV/CV semplice.**](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#tracciamento-curva-ivcv-semplice-sezione-53-del-manuale)
+ [**Tracciamento curve IV/CV con l’applicazione di tensioni di polarizzazione.**](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#tracciamento-curve-ivcv-con-lapplicazione-di-tensioni-di-polarizzazione-sezione-54-del-manuale)

---
---

## Impostazione della working directory (sezione 5.2 del manuale)

Ad ogni avvio, il programma utilizzerà di default la cartella data sul desktop dell’utente come working directory. Se la cartella C:/users/user/Desktop/data esiste già, il programma utilizzerà tale cartella, se invece non esiste, il programma la creerà.

Si consiglia di selezionare la working directory subito dopo l’avvio dell’applicazione e prima di iniziare ad utilizzare le funzionalità del programma.

Se si desidera modificare la working directory, è necessario effettuare la seguente procedura:
1.	Cliccare sul controllo Working directory path posizionato nel general panel tab del general pane (figura 5.2).
2.	Selezionare la nuova working directory dalla finestra di dialogo.
3.	Cliccare su “Seleziona carella”.

    ![Figura 5.2](https://user-images.githubusercontent.com/13961654/31053219-e392ff34-a698-11e7-81b5-bbae22098eb9.png)  
    Fig. 5.2 General pane, dettaglio del general panel


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Cosa contiene questa guida".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#cosa-contiene-questa-guida)

---
---

## Tracciamento curva IV/CV semplice (sezione 5.3 del manuale)

Una volta avviato il programma, per tracciare una curva IV oppure una curva CV senza l’utilizzo di sorgenti di polarizzazione (ossia eseguendo il solo ciclo for interno), la procedura operativa alla quale attenersi è la seguente:
1.	Si sceglie la sorgente di tensione principale (in questo caso tale sorgente sarà anche l’unica sorgente utilizzata) e si seleziona il corrispondente instrument tab. A titolo di esempio, si utilizza come sorgente di tensione principale lo strumento Keithley 6430.
2.	Si seleziona dal menu a tendina VISA resource name Keithley 6430 (mostrato in figura 5.3) l’indirizzo GPIB dello strumento. Per visualizzare una lista degli indirizzi GPIB e seriali individuati dal programma è possibile utilizzare il controllo nel tab VISA resources del general pane descritto nella sezione 4.2. In ogni caso, anche il controllo VISA resource name Keithley 6430 nell’Instrument tab dello strumento mostrerà gli indirizzi GPIB e seriali disponibili.
    ![Fig. 5.3](https://user-images.githubusercontent.com/13961654/31053241-51c1fb90-a699-11e7-97dc-aace9a321e9e.png)
    Fig. 5.3 Dettaglio Instrument tab del Keithley 6430

3.	Se lo strumento è in grado di funzionare sia da sorgente di tensione che di corrente, si seleziona la funzione DC volts. Ad eccezione dello strumento Yokogawa 7651, si è scelto di impedire a priori l’utilizzo degli strumenti come sorgenti di corrente e quindi, nel caso del Keithley 6430, non è necessario selezionare la funzione DC volts siccome è già selezionata di default.
4.	Si imposta la corrente massima erogabile dallo strumento tramite il controllo Current Compliance [A]. In figura 5.3 il limite di corrente è stato fissato pari a 10 mA.
5.	Si selezionano eventuali impostazioni aggiuntive, specifiche dello strumento (ad esempio: canale, range della tensione di output, ecc…). 

    **Se si desidera tracciare una curva IV si eseguano le istruzioni ai punti 6, 7 e 8 saltando le istruzioni ai punti 9, 10 e 11 mentre se si desidera tracciare una curva CV, si saltino le istruzioni ai punti 6, 7 e 8.**

6.	Si seleziona l’Instrument tab dello strumento scelto per l’utilizzo come amperometro. A titolo di esempio si utilizza lo strumento Keithley 6485.
7.	Si seleziona dal controllo VISA resource name Keithley 6485 (mostrato in figura 5.4) l’indirizzo GPIB dello strumento.

    ![Fig. 5.4](https://user-images.githubusercontent.com/13961654/31053242-53451b8c-a699-11e7-9c6b-343b92f801f9.png)
    Fig. 5.4 Instrument tab del Keithley 6485

8.	Si selezionano eventuali impostazioni aggiuntive dello strumento per la misura: autorange, tempo di integrazione, filtri digitali, funzioni matematiche, ecc… Si noti che è possibile utilizzare (al momento in cui viene scritto questo manuale) fino a 5 strumenti di misura (4 amperometri e 1’LCR meter) contemporaneamente.

    **Per configurare ogni singolo amperometro è necessario ripetere, per ogni strumento, i punti 6, 7 e 8.**

9.	Si seleziona l’Instrument tab dello strumento Agilent 4263B. Si seleziona dal controllo VISA resource name Agilent 4263B (mostrato in figura 5.5) l’indirizzo GPIB dello strumento.

    ![Fig. 5.5](https://user-images.githubusercontent.com/13961654/31053243-54f89af8-a699-11e7-83ee-cd3cabbf8032.png)
    Fig. 5.5 Dettaglio Instrument tab Agilent 4263B
 
10.	Si seleziona il livello e la frequenza del segnale di test, i parametri che si intende misurare, il tempo di misura, e la lunghezza del cavo utilizzato. Nell’esempio in figura 5.5 si è scelto di utilizzare un segnale di test pari a 20 mV con frequenza 100 Hz per la misura della capacità parallela equivalente e del fattore di perdita. Si è inoltre ritenuta trascurabile la lunghezza del cavo. Opzionalmente si possono impostare le funzioni matematiche sui due parametri di interesse.
11.	Qualora si utilizzi una sorgente unipolare per effettuare il tracciamento della curva CV (essenzialmente, lo strumento ISEG NHQ223M oppure lo strumento CAEN DT540P), si colleghi il dispositivo di scarica al PC e si effettui un test di verifica del corretto funzionamento mediante il pulsante “TEST DISCHARGE DEVICE” presente nell’Instrument tab della sorgente unipolare dopo aver inserito l’indirizzo seriale del dispositivo nel controllo Discharge device VISA resource name (ISEG NHQ223M). A titolo di esempio, viene riportato l’Instrument tab dello strumento ISEG NHQ223M in figura 5.6. Qualora il test abbia avuto esito positivo, si fissa il tempo scelto per la scarica mediante il controllo Seconds to wait after discharge [s] e si può procedere oltre. Qualora il test abbia invece avuto esito negativo, si provi a disconnettere e riconnettere il dispositivo di scarica al PC e ripetere il test.

    ![Fig. 5.6](https://user-images.githubusercontent.com/13961654/31053245-56f3d764-a699-11e7-852a-56707dd6b1f5.png)
    Fig. 5.6 Dettaglio Instrument tab ISEG NHQ223M: in rosso il sotto pannello impostazioni e test del dispositivo di scarica

12.	Si seleziona il tab DC Sweep. Nel sotto pannello Sweep voltage source settings si imposta come sorgente di tensione lo strumento Keithley 6430 (figura 5.5) mediante il controllo Set voltage source. Si imposta la tensione iniziale (Start [V]), la tensione finale (Stop [V]) e l’incremento/decremento in valore assoluto (Step [V]). Nell’esempio mostrato in figura 5.7, si è scelta una tensione iniziale di 0 V, una tensione finale di 100 V e un incremento di 10 V. Qualora si decida di fornire al programma i valori di tensione da applicare attraverso un file esterno, si inserisca il percorso del file nel controllo Vsource file (single column txt or csv file) e si selezioni la spunta Set Vsource using external file. Il file deve essere in formato .txt oppure .csv, avere una singola colonna di numeri e nessuno spazio in fondo.

    ![Fig. 5.7](https://user-images.githubusercontent.com/13961654/31053246-58e0494a-a699-11e7-9f7b-b4bbc6436d7f.png)
    Fig. 5.7 Dettaglio del tab DC Sweep

13.	Si seleziona il tempo di attesa (in millisecondi) tra l’applicazione di tensione e la misura di corrente mediante il controllo Waiting time nel sotto pannello Timing settings. Eventualmente si imposta anche un timeout (in secondi). Nell’esempio si è scelto di non applicare nessun timeout e quindi il controllo Timeout time [s] è stato impostato al valore di default -1 corrispondente all’assenza di timeout. 
14.	Nel sotto pannello Other settings si può assegnare un nome personalizzato al file .csv che il programma produrrà come output mediante il controllo Output file name. A tale nome sarà inserito il suffisso “_” e l’estensione .csv.
15.	Nel sotto pannello Current and voltage sensing settings (figura 5.7) si seleziona l’interruttore booleano corrispondente allo strumento prescelto per effettuare la misurazione: nell’esempio si imposta al valore TRUE il controllo Use Keithley 6485 (I2).
16.	Nel caso in cui si volesse effettuare una media delle misurazioni effettuate e registrare il solo valor medio, si imposti il controllo Average count (I2) ad un valore diverso da 1. Il valore immesso rappresenta il numero di misure che verranno effettuate ad ogni ciclo di misura e mediate per ottenere il valore complessivo. Si noti che la media è effettuata dal programma e non dallo strumento. Nell’esempio si è scelto di effettuare 10 misurazioni ad ogni iterazione e salvare quindi il solo valor medio.
17.	Opzionalmente è possibile cambiare il nome della variabile misurata che comparirà nel file .csv di output mediante il controllo corrispondente. Nell’esempio si può intervenire sul controllo I2 name.
18.	Se lo si desidera, è possibile aggiungere alcune note nel controllo Notes.
19.	Selezionare la spunta nel controllo Clear graphs before new sweep se si desidera eliminare dai grafici i dati di misure effettuate precedentemente (figura 5.8).
20.	 Cliccare sul pulsante START DOUBLE IV SWEEP (figura 5.8): se i parametri immessi sono coerenti con le caratteristiche degli strumenti scelti comparirà una finestra con il riassunto dei parametri selezionati e la richiesta di conferma (figura 5.9). Nel caso in cui fossero presenti incongruenze tra i parametri scelti per la misura e gli strumenti selezionati, comparirà un messaggio di errore con informazioni utili per la correzione degli errori rilevati. Fino a quando gli errori non sono stati corretti, non è possibile avviare la funzione di misura.
    ![Fig. 5.8](https://user-images.githubusercontent.com/13961654/31053247-5b3bcc0a-a699-11e7-807a-5d738dfb11a6.png)  
    Fig 5.8 Pulsanti di comando tab DC sweep  
    ![Fig. 5.9](https://user-images.githubusercontent.com/13961654/31053248-5cc4a8d0-a699-11e7-8d9a-7d1a7d12104f.png)  
    Fig 5.9 Finestra di conferma avvio della funzione di misura  

21.	Cliccare “OK” per avviare la funzione di misura, altrimenti cliccare su “Cancel” per tornare allo stato Idle.
22.	Cliccando su “OK” si avvia la funzione di misura e il programma esegue i cicli di misura richiesti. Sul grafico corrispondente allo strumento di misura utilizzato, compariranno, istante per istante, i valori rilevati dallo strumento (oppure la loro media se si è attivata la media aritmetica al punto 16 di questa procedura).

Qualora si intenda mettere in pausa la funzione di misura, si clicchi il pulsante PAUSE SWEEPING LOOP indicato in figura 5.8. Cliccando il pulsante, il programma terminerà l’iterazione corrente del ciclo for interno e metterà in pausa la funzione di misura: comparirà una finestra che richiederà se continuare oppure arrestare la funzione di misura.
Nel caso in cui si voglia arrestare la funzione di misura prematuramente, si clicchi il pulsante STOP SWEEPING LOOP. Cliccando tale pulsante, il programma uscirà dal doppio ciclo for annidato e ritornerà in stato Idle dopo aver riportato gli strumenti in uno stato noto. I dati di misura vengono, in ogni caso, salvati ad ogni iterazione.


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Cosa contiene questa guida".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#cosa-contiene-questa-guida)

---
---

## Tracciamento curve IV/CV con l’applicazione di tensioni di polarizzazione (sezione 5.4 del manuale)

Si ricorda che delle due sorgenti di polarizzazione disponibili, una sola è indipendente. La sorgente dipendente dipende dall’array lineare di tensioni definito per la sorgente indipendente. Utilizzando la nomenclatura dei controlli delle sorgenti di polarizzazione del tab DC sweep, nel seguito si chiamerà la sorgente indipendente Bias1 e la sorgente dipendente Bias2. I casi possibili sono i seguenti tre:
1.	Bias1 è utilizzata e Bias2 non è utilizzata. Si applica una singola polarizzazione (indipendente) al DUT.
2.	Bias1 è utilizzata e anche Bias2 è utilizzata: i valori di tensione applicati al DUT da Bias2 sono funzione dei valori di tensione applicati al DUT da Bias1. Sia Bias1 che Bias2 sono utilizzati, si applica quindi una doppia polarizzazione al DUT.
3.	Bias1 non è utilizzata e Bias2 è utilizzata: i valori di tensione applicati al DUT da Bias2 sono funzione dei valori di tensione che Bias1 dovrebbe applicare al DUT se fosse utilizzata. Ma Bias1 non viene utilizzata: si applica quindi una singola polarizzazione al DUT tramite Bias2. Mediante questo metodo è possibile applicare una polarizzazione che cresce/decresce, per esempio, esponenzialmente oppure in modo logaritmico.

**Per tracciare più curve IV/CV al variare di una o due tensioni di polarizzazione, la procedura operativa è la seguente:**
1.	Si sceglie la sorgente di tensione principale e si seleziona il corrispondente Instrument tab. A titolo di esempio, si utilizza come sorgente di tensione principale nuovamente lo strumento Keithley 6430.
2.	Si seguono le istruzioni per il set-up dello strumento indicate nei punti 2, 3, 4 e 5 della procedura contenuta nella sezione 5.3.

    **A questo punto, tenendo in considerazione le tre modalità di utilizzo delle sorgenti di polarizzazione Bias1 e Bias2 si decide quante e quali sorgenti di polarizzazione utilizzare. Nel punto 3 viene effettuato il setting di uno strumento per applicare la polarizzazione indipendente (Bias1) mentre nel punto 4 viene effettuato il setting di uno strumento per applicare la polarizzazione dipendente (Bias2). Si scelga quali punti saltare coerentemente con il tipo di polarizzazione che si intende applicare al DUT.**

3.	Si sceglie la sorgente di tensione Bias1 (polarizzazione indipendente) e si seleziona il corrispondente Instrument tab. In questo caso si seleziona lo strumento Yokogawa 7651. L’Instrument tab di tale strumento è raffigurato in figura 5.10. Si imposta il VISA resource name dello strumento mediante l’apposito controllo, il range di tensione nel quale lo si intende utilizzare (oppure si fissa tale controllo ad un valore arbitrario in volt e poi si sceglie l’autorange), e il limite di corrente massima erogabile. Nell’esempio in figura 5.10 il range di tensione è stato fissato a 10 V (lo strumento sarà in grado di erogare una tensione compresa tra -10 V e 10 V). Si è scelto infine di limitare la corrente erogabile a 1 mA.  
    ![Fig. 5.10](https://user-images.githubusercontent.com/13961654/31053249-5f25ee72-a699-11e7-82aa-663a28452ab9.png)  
    Fig. 5.10 Instrument tab Yokogawa 7651

4.	Si sceglie la sorgente di tensione Bias2 (polarizzazione dipendente) e si clicca sull’Instrument tab corrispondente. Nell’esempio, si sceglie lo strumento TTi QL355TP. Nella figura 5.11 è raffigurato il corrispondente Instrument tab. Si imposta il VISA resource name dello strumento, il canale che si intende utilizzare, il comportamento dello strumento nel caso in cui la corrente superi il limite di corrente erogabile e si fissa la corrente massima erogabile (20 mA nella figura 5.11).  
    ![Fig. 5.11](https://user-images.githubusercontent.com/13961654/31053250-6096ea40-a699-11e7-837a-646fc483c796.png)  
    Fig. 5.11 Instrument tab TTi QL355TP 

    **Se si desidera tracciare più curve IV si eseguano le istruzioni ai punti 6, 7 e 8 della sezione 5.3 per il setup di uno o più amperometri, invece se si desidera tracciare una curva CV, si seguano le istruzioni ai punti 9, 10 e 11 della sezione 5.3 per il setup dello strumento Agilent 4263B.**

5.	Si seleziona il tab DC Sweep. Nel sotto pannello Sweep voltage source settings si imposta come sorgente di tensione lo strumento Keithley 6430 mediante il controllo Set voltage source. Si imposta la tensione iniziale (Start [V]), la tensione finale (Stop [V]) e l’incremento/decremento in valore assoluto (Step [V]). Nell’esempio, in fig. 5.12, si è scelta una tensione iniziale di 0 V, una tensione finale di 10 V e una variazione di 0.5 V.  
    ![Fig. 5.12](https://user-images.githubusercontent.com/13961654/31053252-627cd0ae-a699-11e7-8129-7b43c7932c8e.png)  
    Fig. 5.12 Tab DC sweep: dettaglio sotto pannelli

6.	Nel sotto pannello Single/double DC bias settings si seleziona la sorgente indipendente (Bias1) mediante il menu a tendina Bias1. Si sceglie la tensione di polarizzazione iniziale (Start bias [V]), la tensione di polarizzazione finale (Stop bias [V]) e l’incremento/decremento in valore assoluto (Step bias [V]). Nell’esempio si è scelto di utilizzare i valori 0 V, 0.5 V e 0.1 V rispettivamente. Se si è scelto di utilizzare anche la sorgente di polarizzazione dipendente (Bias2), si sceglie dal menu a tendina Bias2 la sorgente scelta al punto 4 e si definisce la formula per il calcolo della tensione di polarizzazione dipendente nel controllo Bias 2 formula y=f(x). Anche in questo caso è possibile predefinire l’array di tensioni da utilizzare per la sorgente principale e per la sorgente di polarizzazione indipendente e caricare i file mediante gli appositi controlli presenti nel tab DC sweep come descritto nella sezione 5.3.
7.	Si seguono le istruzioni indicate a partire dal punto 13 (incluso) nella sezione 5.3.
Anche in questo caso è possibile mettere in pausa oppure arrestare prematuramente la funzione di misura esattamente come descritto al fondo della sezione 5.3.


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Cosa contiene questa guida".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#cosa-contiene-questa-guida)

---
---

## Esempi di misure effettuate

Di seguito un elenco di misurazioni effettuate:

+ [Caratteristica IV LED rosso 5 mm.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#caratteristica-iv-led-rosso-5-mm)
+ [Caratteristiche Ids Vds N-Channel JFET BF862.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#caratteristiche-ids-vds-n-channel-jfet-bf862)
+ [Caratteristiche CV e δV condensatori realizzati in diversi materiali.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#caratteristiche-cv-e-%CE%B4v-condensatori)
+ [Caratteristiche Cgs Vgs e δVgs N-Channel JFET BF862 e 2N4416.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#caratteristiche-cgs-vgs-e-%CE%B4vgs-n-channel-jfet-bf862-e-2n4416)

---
---

## Caratteristica IV LED rosso 5 mm

Si riportano i risultati del tracciamento di un tratto della caratteristica IV nel primo quadrante di un comune LED rosso 5 mm.
La caratteristica è stata tracciata utilizzando le seguenti impostazioni:

- Sorgente di tensione principale: Keithley 6430 (limite di corrente fissato a 20 mA).
- Amperometro: Keithley 6430 in modalità autorange.
- Tensione iniziale, tensione finale e variazione: 0.5, 1.7 e 0.01 V.
- Numero punti media: 1 (singola misurazione).
- Tempo di attesa: 1 s.

**Circuito di misura**
![RED LED circuit](https://user-images.githubusercontent.com/13961654/32105534-1a9b9898-bb29-11e7-8a81-aa9f589b9aa3.png)

**Risultati misurazione**
![RED LED characteristic](https://user-images.githubusercontent.com/13961654/32105188-e44d7b5e-bb27-11e7-908d-9a450147acb6.png)


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Esempi di misure effettuate".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#esempi-di-misure-effettuate)

---
---

## Caratteristiche Ids Vds N-Channel JFET BF862

Si riportano i risultati del tracciamento di un tratto della caratteristica Ids Vds al variare della tensione di polarizzazione Vds, nel primo quadrante del dispositivo N-Channel JFET BF862. Nella misura si è trascurata la corrente Igs.
Le caratteristiche sono state tracciate utilizzando le seguenti impostazioni:
- Sorgente di tensione principale utilizzata per imporre la Vds: TTi QL355TP (limite di corrente fissato a 20 mA).
- Vds iniziale, finale e sua variazione: 0, 10 e 0.1 V.
- Sorgente di polarizzazione utilizzata per imporre la Vgs: Yokogawa 7651 (limite di corrente fissato a 20 mA).
- Vgs iniziale, finale e sua variazione: 0, -0.5 e 0.1 V.
- Amperometro utilizzato per misurare la Ids: Keithley 6487 in modalità autorange. Prima di iniziare la misura è stata effettuata la zero correction (si ricorda che tale correzione è effettuata di default dal programma per gli amperometri). 
- Numero punti media: 1 (singola misurazione).

**Circuito di misura**
![IV JFET circuit](https://user-images.githubusercontent.com/13961654/32105546-252b2e18-bb29-11e7-8b5b-37d40de9e884.png)

**Risultati misurazione**
![IV JFET results](https://user-images.githubusercontent.com/13961654/32105228-0cf079bc-bb28-11e7-9ff1-e61e2bfe9450.png)


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Esempi di misure effettuate".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#esempi-di-misure-effettuate)

---
---

## Caratteristiche CV e δV condensatori.

Si riportano le caratteristiche CV e delta δV (δ è il fattore di perdita) dei seguenti tipi di condensatori:

- Condensatore ceramico SMD, capacità nominale: 22 µF.
- Condensatore in poliestere THT, capacità nominale: 100 nF.
- Condensatore ceramico HV THT, capacità nominale: 4.7 nF.
- Condensatore ceramico X7R, capacità nominale: 100 nF.

Per lo strumento Agilent 4263B si sono adottate le seguenti impostazioni comuni a tutte le misure effettuate per i condensatori elencati sopra:

- Livello segnale di test: 0.5 V.
- Frequenza segnale di test: 1 kHz.
- Numero punti media: 1 (misurazione singola).
- Tempo di misura: 0.025 s (short).
- Parametri misurati: CP e δ (capacità equivalente parallelo e fattore di perdita).
- Lunghezza cavo di test considerata trascurabile.
- Correzione open non effettuata.

Per la polarizzazione del condensatore HV THT 4.7 nF è stata utilizzata la seguente sorgente di tensione principale:

- ISEG NHQ223M (limite di corrente fissato pari a 4 mA).
- Tensione di polarizzazione iniziale, finale e sua variazione: 0, 600 e 30 V.

Per la polarizzazione dei condensatori rimanenti, è stata utilizzata la seguente sorgente di tensione principale:

- Yokogawa 7651 (limite di corrente fissato pari a 10 mA).
- Tensione di polarizzazione iniziale, finale e sua variazione: 0, 25 e 1 V.

Il circuito di misura utilizzato, comune a tutti i condensatori testati è il seguente:

**Circuito di misura capacità condensatori**
![CV capacitors circuit](https://user-images.githubusercontent.com/13961654/32105558-2dc9a338-bb29-11e7-8dde-d3c6f71a1fb1.png)

**Condensatore ceramico 22uF**
![SMD ceramic 22u capacitor](https://user-images.githubusercontent.com/13961654/32105430-c18487ec-bb28-11e7-84f7-337240b704ca.png)

**Condensatore in poliestere 100nF**
![poliestere 100n capacitor](https://user-images.githubusercontent.com/13961654/32105431-c1adf460-bb28-11e7-93ea-be89ececde9a.png)

**Condensatore ceramico HV 4.7nF**
![HV ceramic 4.7n capacitor](https://user-images.githubusercontent.com/13961654/32105433-c1ee1586-bb28-11e7-8945-1966058a581c.png)

**Condensatore X7R 100nF**
![X7R 100n capacitor](https://user-images.githubusercontent.com/13961654/32105435-c2745286-bb28-11e7-81d5-a6601a1a456f.png)


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Esempi di misure effettuate".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#esempi-di-misure-effettuate)

---
---

## Caratteristiche Cgs Vgs e δVgs N-Channel JFET BF862 e 2N4416

Si è misurata la caratteristica CgsVgs al variare della tensione Vds. Si è cercato di misurare la caratteristica CgsVgs nelle condizioni di utilizzo del JFET: solitamente nei data sheet la capacità Cgs è misurata mantenendo la tensione Vds pari a 0, tuttavia può essere interessante e utile misurare tale capacità in una condizione più prossima a quella in cui il dispositivo viene effettivamente utilizzato.
Si è effettuata una misura per il BF862, e due misure per il 2N4416 (una con il case mantenuto flottante e una con il case collegato a massa).

La configurazione di misura dello strumento Agilent 4263B utilizzata per le tre misure è la seguente:

- Livello segnale di test: 0.05 V.
- Frequenza segnale di test: 100 kHz.
- Numero punti media: 1 (misurazione singola).
- Tempo di misura: 0.025 s (short).
- Parametri misurati: CP e δ (capacità equivalente parallelo e fattore di perdita).

La tensione Vgs è stata applicata utilizzando lo strumento Yokogawa 7651 con le seguenti impostazioni:

- Limite di corrente fissato pari a 20 mA.
- Tensione iniziale, finale e sua variazione: 0, 3 e 0.1 V (corrispondente a una Vgs iniziale e finale rispettivamente uguali a 0 e -3 V) per il BF862 e 0, 8 e 0.3 V (corrispondente a una Vgs iniziale e finale rispettivamente uguali a 0 e -8 V) per il 2N4416.

La tensione Vds è stata applicata utilizzando lo strumento TTi QL355TP con le seguenti impostazioni:

- Limite di corrente fissato pari a 20 mA.
- Tensione iniziale, finale e sua variazione: 3, 0 e 0.1 V per il BF862 e 10, 0, e 0.3 V per il 2N4416.

Questa misura ha presentato una notevole criticità per quanto riguarda la corretta applicazione della tensione Vgs: a causa della presenza della resistenza da 2000 Ω all’interno del dispositivo utilizzato per la misura, si verifica una caduta di tensione che altera la tensione sul nodo di source rispetto a quella applicata dalla sorgente Yokogawa 7651. Per far sì che la tensione di source sia quella richiesta, si è utilizzata la funzione sense dello Yokogawa 7651 che regola opportunamente la tensione in uscita dal generatore in modo che la tensione al nodo di sense (e quindi al source nel caso in esame) sia quella richiesta. Il filtro notch LCR (taglia banda) evita che la tensione sinusoidale di test arrivi al drain. La frequenza centrale del filtro taglia banda è 100 kHz. Il circuito per effettuare questa misura è stato preso da <sup>1</sup>.

**Circuito di misura**
![Circuito di misura](https://user-images.githubusercontent.com/13961654/32105576-3cdc67fc-bb29-11e7-82b1-72d7acb6c765.png)

**Circuito di misura**
![Circuito di misura 2](https://user-images.githubusercontent.com/13961654/32105577-3d05311e-bb29-11e7-8332-28db8ad0881a.jpg)

**Caratteristiche Cgs Vgs e δVgs N-JFET BF862**
![Risultati BF862](https://user-images.githubusercontent.com/13961654/32105443-cc8ccdfc-bb28-11e7-8530-600ea2063f2b.png)

**Caratteristiche Cgs Vgs e δVgs N-JFET 2N4416**
![Risultati 2N4416](https://user-images.githubusercontent.com/13961654/32105444-ccb61f7c-bb28-11e7-8677-e1d8cc74ec85.png)


Torna a [inizio pagina.](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/)
Torna al menu ["Esempi di misure effettuate".](https://mick001.github.io/IV-CV-Curve-Tracer-online-guide/#esempi-di-misure-effettuate)

---
---

<sup>1</sup> Boggini, R., DIODI PIN e transistori JFET integrati su silicio ad alta resistività per la spettroscopia X ad alta risoluzione, Politecnico di Milano, tesi di laurea, Milano, anno accademico 2006-2007.
