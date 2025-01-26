## OutPut & Comments

Il primo commando da imparare è il `print`:  
==è una funzione built-in che ti consente di mandare in output del testo o qualsiasi altra cosa si voglia che verrà poi visualizzato sulla console.==  
Quindi print ti stampa una o più espressioni all'uscita standard (la console) e puoi farne quanti te ne pare.  
La funzione `print`  la si può usare per più azioni, sempre legate però allo stampare espressioni sulla console, che vanno riportate tra le callbacks.  
Le applicazioni più comuni di questo commando sono:

1. Stampare un semplice messaggio sulla console :  
  
```lua
 print( "Hello, World!")
```

2. Stampare variabili:  

```lua 
local message = ("Hello, World!")                                  
print (message)
```

3. Stampare un numero:  

```lua 
  print (123)
```
  
4. Stampare un valore booleano:    
Es:
```lua
 print (true)
```
 
5. Stampare espressioni multiple:  
 
```lua
print("Hello, World", 123, true)
```


6. Usare la formattazione delle stringhe con il _**`string.format`**_:  
 
```lua 
local name = "John Doe"                                     
local age = 35                                     
print (string.format("Name:%S, Age: %d, name, age))
```

7. Stampare il risultato di una funzione o espressione:  
```lua
local x = 5                                 
local y = 10                                  
print("The sum of", x,"and", y,"is", x + y)
```
 
8. Stampare gli elementi di un array o di una table:  
 
```lua
local tbl ={1, 2, 3, 4, 5}                                  
for i, v in ipars(tbl)do                                  print("Element", i,"has value", v)                                 
end
```


9. Stampare le chiavi e i valori di una table:  
```lua
 
local tbl = {a = 1, b =2, c = 3}                                   
for k, v in pairs(tbl) do                                 
print("Key", k,"has value",v)                                 
end
```


10. Usare il _**'print'**_ per scopi di debbugging, al fine di vedere il vlaore di una variabile in un certo punto nel programma:  

```lua
local x = 5                                  
print("The value of x is:", x)
```



Queste sono solo alcune delle applicazioni più comunemente usate della funzione print nel lua, poiché è una funzione versatile che può essere usata per un infinità di scopi che vanno dal visualizzare i messaggi, al debugging alle informazioni di logging.

Per quanto riguarda i commenti invece, si usano per commentare parti di codice e vengono utilizzati in vari modi:

1. Commentare per fare una to do list su cosa c'è ancora da fare, mettendo in conto che quando si finisce una lavorazione non sempre il giorno dopo ci si ricorda dei propositi fatti qualche ora prima
2. Per fare dei suggerimenti e/o note sul codice
3. Per usarli, ad esempio, come dei "segnalibri" all'interno del codice: ciò è utile per evitare di stare ore a capire cosa fa ogni singola funzione, array, tags(HTML) e riga di codice. Questa applicazione è molto utile quando si hanno tante righe compilate e si voglia tornare indietro per modificare una singola riga o più parti del codice ma non ci si ricorda a cosa serve e soprattutto (in alcuni casi) dove inizia e dove finisce quella parte interessata.
4. Un altra funzione è quella di disabilitare una sezione del codice

> [!info] N.B:
>  Queste applicazioni dei commenti non sono solo prerogativa del linguaggio lua ma anche di tutti gli altri linguaggi I commenti, nel linguaggio lua, vengono creati usando due trattini(--), o su VS tramite lo shortcut da tastiera `Ctrl+ù`, e come per ogni linguaggio non vengono letti quindi vengono ignorati dal programma.  
>   ![[Lua print text.png|2000*600]] 
> 
>
>Se decommentassimo il commento (`Ctrl+ù+k`) VS c'è lo sottilinerebbe in rosso, dandolo quindi come errore perchè non sa qual è il testo giusto, e se andassimo a visualizzarlo sulla console il risultato sarebbe il seguente:  
  >![[lua print text error.png]]
  
Ovviamente posso commentare tutte le sezioni di codice che voglio, ad esempio:  
  ![[lua screenshot.png]]
  
Questo è la parte di codice che usato per fare il primo esempio, ad ogni modo come si può vedere ho commentato anche la seconda riga dove c'è il "print",  
se andassimo a visualizzare il file sulla console il programma verrà eseguito senza alcun output perchè ho commentato quella riga e il programma l'ha saltata,  
questo perchè quando il programma vede un commento salta la riga e va a quella o quelle successiva/e.  
![[no output.png]]    
Ovviamente in questo caso si parla ancora di commenti _"single-line"_, difatto posso, ad esempio, commentare anche sulla stessa riga del commando  
  ![[Single Line comments.png|900]] 
Tuttavia esistono anche i commenti chiamati _"Block comments"_ che sono i commenti multi linea, cioè su più righe, ed si scrivono (--\[\[\]]):   
 ![[block comments.png|900]]  
Quindi ricapitolando, esistono 2 tipi di commenti nel lua:

1. Single-line comments: inziano con i due trattini e vengono eseguiti fino alla fine della riga
2. Block comments: Iniziano con --\[\[ ]\]e vengono eseguiti fino a dove sono state posizionate le ultime due square brackets (vedi esempio sopra)


Per fare un esempio pratico:

```lua
-- This is a single-line comment    
--[[This is a block comment--]]                             
--[[You can also use block comments to comment out a piece of code                             
--[[print(10) -- no action (comment)--]]                     --[[print  ( 10 )--> 10--]]                                  -- The following code will be executed                       print("Hello, World!" )
```

Ritornando alla funzione di print, ci sono alcune occassioni in cui è utile stampare sulla console più stringhe insieme, e no non basta fare  
  ![[print str concat.png|1000]]  perché verrà visualizzato sulla console come:  
  ![[print str concat output.png|1000]]  
e quindi come possiamo ben vedere la stringa viene giustamente visualizzata come due stringhe differenti perchè ho usato 2 volte la funzione print, quindi se volessi concatenare 2 stringhe tra loro, sulla stessa riga devo usare "..": questi due punti si usano nel lua per concatenare più stringhe tra loro.  
  ![[concat str with print fun.png|1000]]  
Di conseguenza tutto ciò verrà visualizzato come:  
![[concat str with print fun output.png|1000]] 
 !!N.B.!! da notare come, nell'esempio dove si vede l'interfaccia di VS, le virgolette abbiano tutte uno spazio dall'inizio della frase, questo perchè senno le concatenazione verrebbe visualizzata come:  
![[conc str with pr fun output .png|1000]]    
Posso fare la stessa cosa con le virgolette alla fine di ogni parola/frase ma se lo facessi sia con le virgolette ad inizio frase che con quelle alla fine il risultato sarebbe:  
  ![[conc str with pr fun output 2.png|1000]]
come possiamo notare ho creato troppo spazio tra le singole frasi facendole visualizzare come sono scritte tra l'argomento di print.