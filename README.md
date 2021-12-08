# Logisim-project

FERMA LA BOMBA
Progetto di: *********
Numero di matricola: ******
OBIETTIVO
Inserire la combinazione corretta per fermare il conto alla rovescia della bomba che sta per
esplodere.


INPUT
Gli input del circuito sono in totale 8 pulsanti:
- 1 per cominciare una nuova partita
- 2 per scegliere la difficoltà della partita
- 3 per inserire la combinazione per fermare la bomba
- 1 per cancellare la combinazione inserita
- 1 per cancellare il numero di bombe disinnescate


OUTPUT
Sono stati utilizzati diversi tipi di output:
- 9 led per presentare la combinazione inserita
- 4 Hex Digit Display:
- 1 per mostrare il numero di input corretti
- 1 per mostrare il numero di bombe disinnescate
- 2 per mostrare il conto alla rovescia della bomba
- 2 Led Matrix per mostrare la bomba e l’esito della partita


FUNZIONAMENTO NELLO SPECIFICOCONTO ALLA ROVESCIA E LIVELLI
Il countdown è scandito da due contatori, uno per il livello difficile, 7 secondi, e uno per quello
facile, 15 secondi.
La scelta della difficoltà fa partire il contatore che poi viene proiettato sull’ Hex Digit Display. In
particolare quello del livello facile viene presentato su due display, dato che necessita della doppia
cifra, tramite l’utilizzo di alcuni multiplexer e operatori aritmetici. Il contatore si ferma se arriva
l’input della vittoria.


SEQUENZA IN INPUT
La combinazione inserita viene registrata grazie all’utilizzo di 3 register che memorizzano l’input se
gli viene permesso dal contatore e i valori vengono inseriti in un unica stringa di bit.
Ovviamente è presente un tasto che permette di azzerare il contatore e la sequenza inserita.


GENERAZIONE COMBINAZIONE E CONTROLLO VITTORIALa sequenza di sblocco viene generata in maniera random dividendo il codice in 3 parti e usando
seed differenti. Se uno degli input generati equivale a 00 allora gli si sommerà uno dato che gli
input corrispondo a 01,10,11. Il controllo della vittoria avviene semplicemente confrontando le due
stringhe con un comparatore.



MACCHINA A STATI FINITI PER LA RAPPRESENTAZIONE DELLO STATO
Ho utilizzato una macchina a stati finiti che prendeva in input lo stato della vittoria e del countdown
per decidere cosa mettere in output nello schermo.



CIRCUITI SEMPLICI:
Sono presenti dei sotto circuiti molto semplici come quello del numero di bombe disinnescate che è
un semplice contatore o quello del numero di input corretti che si basa sul confrontare le porzioni di
stringhe con dei comparatori.
I disegni rappresentati nei Led Matrix (Bomba, faccina sorridente, faccina triste, scritta WON e
LOST) sono conservati sotto forma esadecimale in delle costanti.
Conclusione
Durante la realizzazione del progetto ho cercato di utilizzare tutte le componenti viste durante le
lezioni di laboratorio.Il progetto come da richiesta è dotato di:
- Parte combinatoria: le porte logiche e i multiplexer
- Parte sequenziale: memorie come i counter,register e FlipFlop
- Parte temporale: il clock per il countdown
- Input e Output: i bottoni e i diversi modi di presentare l’output (Led semplici, Hex e Led Matrix)
