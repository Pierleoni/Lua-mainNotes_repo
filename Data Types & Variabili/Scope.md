# Definizione di scope
 in programmazione si intende il **contesto o ambito** in cui una variabile o una funzione è **visibile** e **accessibile**. In altre parole, lo **scope** determina dove nel codice puoi "vedere" e usare una determinata variabile o funzione.
 Per essere più precisi la sua definizione è:
 ==Lo **scope** è l'insieme di regole che determinano **dove** (in quale parte del codice) una variabile, una funzione o un altro identificatore è **visibile** e **accessibile**.== 
In altre parole, ==è il **contesto logico** o **spaziale** del programma in cui una variabile o funzione può essere utilizzata.== 

### Componenti chiave della definizione:

1. **Visibilità**: Determina dove puoi "vedere" una variabile o funzione nel codice.
    - Se una variabile è visibile, puoi accedervi direttamente.
    - Se non è visibile, non puoi né leggerla né modificarla.
2. **Accessibilità**: Riguarda il permesso di utilizzare una variabile o funzione, in base alle regole del linguaggio e dello scope (ad esempio, locale o globale).
3. **Contesto**: Lo scope è sempre definito in relazione a un contesto, che può essere:
    - Un intero programma.
    - Una funzione.
    - Un blocco di codice specifico.

### Scope nei linguaggi di programmazione

Ogni linguaggio di programmazione definisce le proprie regole per lo scope, ma i tipi principali sono:

1. **Global Scope**:  
   ==L'identificatore è accessibile da ogni parte del programma.== ^globalScope
```lua
y = 20 -- Variabile globale
function example()
    print(y) -- y è visibile dentro la funzione
end
example()   -- Stampa 20
print(y)    -- Stampa 20
```
^globalScope-codeBlock


2. **Local Scope**:  
   ==L'identificatore è accessibile solo all'interno di un blocco, funzione o modulo specifico.== ^localScope
```lua
function example()
    local x = 10 -- x è locale alla funzione
    print(x)     -- Funziona
end
print(x)         -- Errore: x non è visibile qui   
```
^localScope-codeBlock


3. **Block Scope**: 
   ==L'identificatore è accessibile solo dentro un blocco delimitato (es. `{ }` o `do ... end`).== 
```lua 
do
    local z = 30 -- z è locale a questo blocco
    print(z)     -- Funziona qui
end
print(z)         -- Errore: z non è visibile fuori dal blocco
```
4. **Lexical Scope (o Static Scope)**: 
   ==Lo scope è determinato durante la scrittura del codice, in base alla struttura nidificata.==
   Questo tipo di Scope è integrato in Lua, anzi lo usa prevalentemente a causa della sua prevedibilità, poiché Lua è un tipo di linguaggio che si concentra sulla semplicità e performance. 
```lua
function outer ()
	local x = 10  --[[ Variabile locale visibile solo dentro outer() e                         le sue funzioni annidate]]-- 
function inner ()
	print(x)        --[[Può accedere a x perché inner() è diciharata dentro outer()]]--
	end
	inner() --Stampa 10 
	end
outer()  --print(x) --Errore: x non è visibile fuori da outer
```
Qui `inner` può accedere a `x` perché è definita nello scope lessicale di `outer`. 

> [!info] Esempio di linguaggi in cui il lexical scope (o static scope) è integrato.
>  - Lua
>  - Python
>  - Jacascript
>  - C
>  - Java
>  - Rust
>  E molti altri linguaggi moderni.

    
1. **Dynamic Scope**: 
   ==Lo scope dipende dal percorso di esecuzione del programma e da come le funzioni vengono chiamate.== 
   Quindi questo scope dipende dinamicamente dalla sequenza di chiamate alle funzioni durante l'esecuzione del programma. 
   Le variabili vengono risolte guardando la stack delle chiamate (call Stack), non la struttura del codice. 
```Lisp
(setq x 10) ; Variabile globale
(defun outer()
	let ((x 20)) ; Variabile dinamica
		(inner))) ;Chiama una funzione che usa "x" 
(defun inner()
	print(x)) ;Risolve "x" guardando la call stack
 (outer) ;Stampa 20, perché usa "x" definita in outer
 (inner) ;Stampa 10, perché non c'è "x" nella call stack, quindi usa quella globale
```
- Qui, inner risolve il valore di `x` in base al contesto dinamico (la funzione chiamante) e non in base alla struttura del codice. 
  
> [!info] Esempio di linguaggi che usano il Dynamic Scope
> - Emacs Lisp
> - Shell Scripting (parzialmente)
> - Perl (in modalità particolari) e alcuni linguaggi meno moderni


> [!NOTE]  La macro differenze tra questi due tipi di scope sono:
> - Lo static scope è più prevedibile e facile da gestire poiché è basato dalla scrittura del codice ed è determinato al momento della sua scrittura. Inoltre è più facile da prevedere e da fare il debug
> - Il Dynamic Scope è più imprevedibile e può portare a risultati difficili da prevedere (specialmente in programmi complessi), proprio perché è basato sul runtime e sulla call stack ed è determinato al momento dell'esecuzione del codice.


> [!example] La buona novella dello Scope
> Per usare una metafora, possiamo pensare allo scope come a una stanza in una casa:
>  all'interno di questa stanza c'è un oggetto, che possiamo vedere come una variabile, che puoi vedere e usare solo nella stanza in cui si trova. Di conseguenza: 
>- Se è "locale", l'oggetto è visibile solo nella sua stanza.
>- Se è "globale", l'oggetto può essere visto e usato da chiunque, in qualunque stanza della casa.
