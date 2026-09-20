# Audio Basics
Parliamo di cose oggettive, numeri!

## Volume e decibels

Il volume di una canzone (un suono) o sound pressure level (SPL) si misura in `decibel`.
Si misura quindi un cambiamento della pressione dell'aria che si propaga fino ai timpani, facendoli vibrare.

Per definizione il decibel esprime un `rapporto` tra due SPL ma in pratica puo' anche rappresentare un volume assoluto. In questo caso esiste una reference implicita a 0dB (il suono piu' piano che il nostro orecchio puo' sentire (threshold of hearing)).

> [!NOTE] Lo sapevi?
> 0dB SPL sono circa 20 micropascals (pressione dell'aria)
>

Sono in scala `logaritmica`:
* +6 dB = il doppio di pressione dell'aria o di volts
* +20 dB = 10 volte la pressione dell'aria o di volts
* +40 dB = 100 volte la pressione dell'aria o di volts
* +60 dB = 1_000 volte la pressione dell'aria o di volts
* +80 dB = 10_000 volte la pressione dell'aria o di volts
* -6 dB = la metà di pressione dell'aria o di volts

Quindi se il voltaggio di una sorgente acustica aumenta di 10 volte, il suono emesso da quella sorgente aumenta di 20dB

A noi per sembrarci di avere raddoppiato il volume di una canzone ci bastano 8-10dB (a seconda delle frequenze presenti nella canzone).
Infatti siamo più sensibili ai cambiamenti di volume tra le frequenze medie, invece poco negli alti/bassi.
Anche la stanza in cui si ascolta influenza il modo in cui sentiamo un cambiamento di volume: in una stanza non trattata con molti echo sarà sicuramente più difficile sentire una differenza di mezzo decibel.

## Livelli Standard di Segnale (p33)

Anche nei componenti elettronici che trasportano segnali audio si usano i decibel.
Un amplificatore che raddoppia il segnale in output si dice che ha un gain di 6dB (nota che non importa il valore di volt che ha in ingresso).

Scegliendo delle reference diverse (diverse da 0dB (soglia dell'udibile)) posso ricavare altre unità di misura.
Tra i dispositivi audio professionali si usa il `dBu` per dire i voltaggi di input e output che supportano. 0 dBu corrispondono a 0.775 volts (reference).

In questo modo se ho un numero di dBu posso direttamente convertire in volt (normalmente non potrei farlo perchè il dB non è un valore assoluto)

20 dBu sono 10 volte 0 dBu (quindi 7.75 volts).

Obsoleto, si usava anche il `dBm` che fissa a 0dBm 1 milliwatt.

Poi c'è il `dBV` in cui 0 dBV corrispondono a 1 volt. L'offset di 0.225 volt tra dBV e dBu da si che lo stesso numero in dBV e dBu abbia una differenza di 2.21 dB.

Per l'audio digitale si ha il `dBFS` dove FS sta per Full Scale. 0 dBFD è il piu' grande numero digitale che una sound card o analog digital converter può accettare in input/dare in output (infatti si misurano con i numeri negativi).

Poi c'è la differenza tra il livello di picco e il medio in un segnale digitale (pensa al segnale elettrico che passa nel cavo delle cuffie o in quello di un diffusore, li' la corrente e' alternata, la ddf cambia continuamente tra diversi voltaggi, è il voltaggio che cambia che fa muovere la membrana che poi sposta l'aria).
Questo si chiama livello `RMS`. Diciamo che misura matematicamente l'energia media del segnale.
* Quando si registra l'audio ci interessa molto il voltaggio di picco (peak level) perché è quello che poi determina se l'audio avrà distorsioni.
* Invece la _loudness_ percepita è determinata dal voltaggio medio (anche questa ci importa).
* Il valore di RMS invece serve più agli ingegneri elettrici che a noi audiofili.

Per calcolare la loudness e i livelli di picco prendi tutti i valori assoluti ovviamente (perchè i volt che passano nei fili delle cuffie possono anche essere negativi (fanno muovere la membrana dall'altra parte))

## Livelli di segnale e Metering

Gli strumenti di misurazione dei livelli audio sono importantissimi per la registrazione e il mixing perchè ogni recording medium (analog tape, ...) ha un range di livelli di volume che puo' supportare.
Infatti se registrando in analog tape l'audio è registrato troppo piano poi senti un hiss quando lo senti, invece se lo registri troppo forte viene distorto.
Uno dei primi strumenti di misurazione volume audio era il `VU meter` (VU = volume units).
I moderni strumenti digitali invece usano un scala con LED come questa (anche quelli dei DAW):

![Digital audio meter](./digitalmeter.png)

Questi strumenti digitali possono anche avere uno switch per mostrarti i valori di picco oppure medi.
Questo è un concetto importante (il fatto che possano mostrare anche i valori medi) perchè le nostre orecchie riconoscono l'average loudness di un suono, e non molto i valori di picco. I valori di picco sono comunque importantissimi perchè sono quelli che vengono distorti dalle sound card dei computer e analog tape quando raggiungono il cosiddetto `clipping point`.

I VU meters invece per loro natura mostrano i livelli di voltaggio medi e quindi il volume medio. Infatti la lancetta impiega del tempo a muoversi e stabilizzarsi, non riesce a star dietro ai rapidi cambiamenti dei voltaggi della musica e del parlato quindi tende ad aggirarsi nei volumi medi.
Sono ottimi quando una canzone ha dei volumi che cambiano costantemente perchè rappresentano meglio quello che sentono le nostre orecchie.
Ma non ti dicono i valori precisi di picco (se non aggiungi altri strumenti di supporto).

Gli strumenti digitali ti possono anche mostrare contemporaneamente i valori di picco e average e poi possono anche mostrarti il valore di picco piu' alto raggiunto. Così se mentre registri non te ne sei accorto lo vedi dopo il picco più alto raggiunto.

La differenza tra il livello di picco di un segnale e il suo livello medio è detto `crest factor`.

> [!WARNING]
> non confondere crest factor e dynamic range.
> Il crest factor è la differenza tra i picchi e i livelli medi (per i valori medi si prende l'RMS).
> Il dynamic range è la differenza tra i picchi e i livelli minimi.
>

## Calcolare i decibel







