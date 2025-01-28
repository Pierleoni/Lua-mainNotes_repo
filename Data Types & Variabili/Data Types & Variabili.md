## Data types & variables

Nel lua ci sono vari tipi di data types:

1. **Boolean:**  
    come in ogni linguaggio di programmazione, i booleani sono dei data types che hanno solo due valori possibili **`true`** e **`false`**.  
    questi due valori sono usati per rappresentare, rispettivamente, verità o falsità logiche
2. **number:**  
    Rappresenta qualsiasi numero reale
3. **Strings:**  
    Rappresenta una sequenza di caratteri (vedi esempio concatenazione delle stringhe nell'argomento di print)
4. **nil:** 
   denota una variabile senza valore (equivalente al null di JS)
5. **functions:** 
   un valore richiamabile
6. **Userdata:** 
   Un valore che rappresenta una parte arbitraria di dati C
7. **Thread:** 
   Valore che rappresenta un nuovo thread di esecuzione
8. **Table:** 
   Una raccolta di coppie chiave-valore, simile a un dizionario o a una hashmap.  
> [!info] Nel Lua sono fondamentalmente dei loop.


### Dichiarare le variabili 
Per dichiarare una variabile  esistono 2 modi differenti: 
1.  `local`:  
   La variabile è visibile solo all'interno del blocco (funzione, ciclo, ecc.) in cui è stata dichiarata 
```lua
local x = 10
print(x) -- Visibile solo in questo blocco 
```

2. Globale (dichiarazione senza `local`): 
   La variabile diventa accessibile globalmente in tutto il programma, a meno che non sia sovrascritta 
```lua 
x = 10 -- Variabile globale
print(x) -- Accessibile ovunque
```

> [!Warning] `local` o non `local`
> In assenza di `local`, Lua considera la variabile come globale **per default**, quindi tecnicamente basta scrivere il nome della variabile per crearla come globale.

> [!info] N.B.
> i caratteri speciali che si possono utilizzare con le lettere sono ovviamente il maiuscolo, underscore ma non i trattini ).  

Una variabile è solo un contenitore, la variabile può contenere un valore numerico, una stringa, un array, etc. 
Quindi quando assegni un valore ad una variabile, quel valore viene copiato (per i tipi base come numeri o stringhe). Questo significa che, quando cambi il valore di una variabile, non influenzi altre variabili che contengono lo stesso valore.
```lua 
a = 10
b = a
b = 20
print(a,b) -- 10 e 20 perché a e b sono contenitori indipendenti.

```
Una volta digitato "local" bisogna dare un nome alla variabile ed un valore: per fare ciò  
 ![[declare variable in Lua.png|1000]]   
Come possiamo vedere dall'esempio alla variabile "a" è stato assegnato il valore "15"  

> [!beware]
>il segno del uguale (`=`) serve per assegnare un valore alla variabile, ciò significa che la variabile `a` ha un valore di 15  non che `a` equivale a `15` 

Ovviamente il valore da assegnare ad una variabile non per forza deve essere un valore numerico, può essere anche una stringa o una booleano:  

```lua 
local int = 3 
local float = 3.14
local str = "Hello", 'World'
local bln = True 
```

> [!NOTE] Concatenare le stringhe in lua 
> 
> ![[varStrValue.png|1000]]  
> Come possiamo vedere ho preso il mio nome e la parte della frase dove dico la mia provenienza dall'argomento del commando di print di prima e li ho trasformati in delle variabili, dopodiché ho inserito i nomi delle variabili nell'argomento di print, cosi facendo ho dato un valore alle variabili `myName` e `b` che sono due stringhe.  
> Di fatto l'output risulterà:  
> ![[outputStr.png|1000]]    
>
> >[!example] P.S.: 
> > questo metodo torna utile quando dobbiamo ripetere lo stesso valore in una stringa o tot linee di codice, così facendo evitiamo di riscriverlo tot volte riga per riga.  
> > In lua se si vuole scrivere una stringa multi linea si deve scriverla tra due parentesi quadre ( \[\[\]\] ):  
>>```lua
> > local description = [[ "Hey" 
> > "Hey There"
> >"Hey folk" ]]  
> >print(description)
>>```
>>L'output sarà:
>>```lua
>>"Hey"
"Hey There"
"Hey folk"
>>```
>>> [!beware]- Occhio all'indentazione!!
>>> Con questo metodo viene stampata anche l'indentazione, per ciò se io scrivessi 
>>>```lua
>>> local description = [[ 
>>> 	"Hey" 
> > "Hey There"
> >"Hey folk" ]]  
> >print(description)
>>>```
>>>L'output sarà: 
>>>```lua 
>>>        "Hey"
"Hey There"
"Hey folk"
>>>```
>>>

## I valori booleani delle variabili 
In lua, come in altri linguaggi di programmazione esistono due valori: `True` e `False` e `nil`. 
Questi valori sono valori booleani e servono in contesti come le condizioni:


```lua 
local isActive = true
local isComplete = false

if isActive then
    print("Attivo")
else
    print("Non attivo")
end

if isComplete then
    print("Completato")
else
    print("Non completato")
end

```
^ex-bln


In Lua, i valori che sono considerati "falsy" (equivalenti a `false` nelle condizioni) sono solo `nil` e `false`. 
Qualsiasi altro valore (compreso `0` o stringhe non vuote) è considerato "truthy" e sarà valutato come `true`. ^d94193


> [!info] Differenza tra `nil` e `false` 
> Come detto poco sopra sia `false` che `nil` sono considerati valori `falsy`, tuttavia hanno significati e usi diversi:
> 1. `false`: 
>     - È un valore booleano, specificatamente rappresentante il concetto di "falso". 
>      -  Viene usato esplicitamente nelle operazioni logiche o [[#^ex-bln |nei controlli di flusso  ]]
>      - È un valore definito e ha un significato ben preciso di "falso".
>```lua
>  local flag = false
if not flag then
 >   print("La flag è falsa")
>end
>```
>2. `nil`:
>   - Rappresenta l'assenza di valore o l'inizializzazione di una variabile non assegnata.
>   - Può essere usato per indicare che una variabile non contiene alcun valore (è "vuota").
>    - È spesso utilizzato per segnare l'assenza di un oggetto o per indicare che una funzione non ha restituito alcun valore.
>```lua 
>local value = nil
>if value == nil then
>    print("La variabile è nil, cioè non ha valore")
>end 
>```
>
>
>> [!example]+ Per ricapitolare 
> >- **Significato**:
 >>   - `false` rappresenta una condizione di falsità, mentre `nil` indica che non c'è alcun valore (è vuoto o non inizializzato).
>>- **Contesti di utilizzo**:
 >>   - `false` è usato per esprimere una condizione logica falsa.
 >>   - `nil` è usato per esprimere l'assenza di valore o come valore di ritorno di funzioni che non restituiscono nulla.
>>> [!example]- Esempio Pratico
>>>```lua
>  >> local a = nil
>>>local b = false
>>>if a then
 >>>   print("a è vero")
>>>else
>>>    print("a è falso (nil)")  -- Questo verrà stampato
>>>end
>>>
>>>if b then
 >>>   print("b è vero")
>>>else
 >>>   print("b è falso (false)")  -- Questo verrà stampato
>>>end
>>>``` 

Quindi, sebbene entrambi vengano trattati come "falsy" nelle condizioni, `false` è un valore booleano esplicito, mentre `nil` è un valore che rappresenta l'assenza di valore.

## Lo scope in Lua 
Lo [[Scope]] in Lua è strettamente legato a come dichiari le [[Data Types & Variabili#Dichiarare le variabili|variabili]].
#### Local Scope e Global Scope
 1. [[Scope#^localScope|Local Scope]]: 
	Quando dichiari le variabili con la keyword `local`, questa esista solo nel blocco (scope) in cui è stata dichiarata, come una funzione, un ciclo o un file. 
	Una variabile locale non è accessibile al di fuori di questo ambito. 
```lua 
local x = 10 
print(x) -- Funziona, x è accessibile
end
print(x) -- Errore, x non è definita 
```

2. [[Scope#^globalScope|Global Scope]]: 
  Se non si utilizza `local` per dichiarare una variabile, essa diventa **globale** per impostazione predefinita. 
  Le variabili globali sono accessibili ovunque all'interno dello stesso ambiente globale (o "namespace"), il che può causare conflitti se due variabili con lo stesso nome vengono dichiarate in contesti diversi.
```lua
y = 20  -- Variabile globale
print(y)  -- Funziona ovunque
```

Questo la possiamo pensare come una scatola, se si usano molteplici file Lua nel programma, mentre nelle variabili locali posso accedervi solo nei rispettivi file, ma con le variabili con lo scope globale posso accedervi al di fuori del file, ciò significa che i nomi delle tue variabili possono sovrascrivere il nome di una o più variabili dentro un altro file. 
Si può pensare  a ogni file Lua come a un'unità separata di codice, che ha il proprio ambiente di esecuzione. Le variabili locali definite in un file non possono essere viste o usate in un altro file, come se fossero "confinate" in una scatola.
Quindi le variabili locali sono **private** rispetto al file in cui vengono definite. Se definisci una variabile `local myVar` in un file, questa non sarà accessibile in un altro file Lua.
Al contrario, le variabili globali (senza `local`) sono condivise tra tutti i file che fanno parte dello stesso programma Lua. Questo significa che se due file definiscono una variabile globale con lo stesso nome, l'ultima dichiarazione sovrascriverà la precedente.
```lua
-- File1.lua
myGlobal = "Hello"
```

```lua
-- File2.lua
myGlobal = "World"  -- Sovrascrive la variabile globale del File1
```

Ovviamente ciò porta a conflitti,  comportamenti inaspettati  o errori nel programma proprio perché le variabile globali sono accessibili ovunque, e quindi quando accade quando due file utilizzano lo stesso nome di una o più variabili presenti nei due file. 


> [!hint] Consigli per gestire lo Scope in Lua
> - Usa sempre `local` quando possibile, specialmente in programmi complessi con più file, per evitare conflitti di nomi e migliorare la leggibilità e la sicurezza del codice. 
>- Per condividere variabili o funzioni tra file, utilizza tabelle o il sistema dei moduli Lua:
>```lua
>  -- File1.lua
>local myModule = {}
>myModule.value = "Hello"
>return myModule
>
>-- File2.lua
local importedModule = require("File1")
print(importedModule.value)  -- Stampa "Hello"
>
>```


