   
# Il Linguaggio LUA

LUA è un linguaggio di programmazione facile, potente, efficiente, che pesa poco ed è un linguaggio di scripting incorporato. Per linguaggio di scripting incorporato si intende  

==un linguaggio di scripting (o più specificatamente un interprete per un linguaggio del genere) che può essere incorporato nelle applicazioni.== Pertanto, l'interprete ha un'API che puo essere utillizzata per integrarla nell' applicazione, consentendo agli script di controllare tutti o parti dell'applicazioni.  
 Il vantaggio di ciò è che gli svilluppatori di apllicazioni devono solo fornire l'interfacciamento con il linguagggio; non deovono implementare il linguaggio reale. Ciò Consente di utilizzare linguaggi più complessi e ricchi di funzionalità, poichè non c'è tempo di sviluppo(dal punto di vista dello svillupatore dell'applicazione). Per gli utenti, significa che conoscono i pro e i contro, le stranezze e i benefici del linguaggio di scripting, a condizione che stiamo parlando di uno comunemente usato.

 Quindi il Lua combina la semplice sintassi procedurale con potenti costrutti di descrizione dei dati basati su array associativi e semantica estensibile.  
 Lua è tipizzato dinamicamente, viene eseguito interpretando il bytecode con una macchina virtuale basata su registri e dispone di una gestione automatica della memoria con una garbage collection incrementale, che lo rende ideale per la configurazione, lo scripting e la prototipazione rapida.



> [!history] C'era una volta...il PUC-Rio
> 
> Lua è stato creato nel 1993 da Roberto Ierusalimschy, Luiz Henrique de Figueiredo e Waldemar Celes, tutti e tre membri del Tecgraf/PUC-RIO (Tecnologia em Computação Gráfica) della Pontificia Università Cattolica di Rio de Janeiro.  
> Fino alla versione 5.0 le licenze erano rilasciate sotto licenza simile alla licenza zlib, dalla versione 5.0 Lua è stato rilascaito sotto licenza MIT.  
> Ad oggi Lua viene usato al LabLua, un laboratorio del Department of Computer Science di PUC-RIO.
> 

> [!NOTE]
> 
> Prima di continuare è bene sapere che, per chiunque lo usi, Visual Studio Code non supporta di default il linguaggio Lua, se si vuole iniziare a programmare con il Lua bisogna andare sulle estensioni di Visual Studio Code e scaricare una delle estensioni Lua.  
> Oppure se, come in questo caso, si volesse scrivere i ReaScripts bisogna sempre andare sulle estensioni o sul marketplace di VS e cercare ["REAPER ReaScripts"](https://marketplace.visualstudio.com/items?itemName=AntoineBalaine.reascript-docs) o ["REAPER ReaScript Extension (Intellisense)"](https://marketplace.visualstudio.com/items?itemName=GavinRay.reascript) (perlomeno sono le due uniche estensioni su VS riguardanti i ReaScripts di Reaper).  
> Ovviamente se si scaricano queste una di queste due estensioni non è necessario scaricare le altre riguardanti il linguaggio in se, ne tanto meno scaricare il pacchetto Lua sul proprio sistema operativo,  
> poichè entrambe le estensioni sono progettate per fornire funzionalità e compatibilità per lo sviluppo di script Lua per Reaper in Visual Studio Code, mentre le estensioni generiche Lua offrono sì le funzionalità di base per lo sviluppo in Lua ma non potrebberio offrire le caratterisitiche specifiche di Reaper per lo svilluppo degli scripts.  
> N.B: di entrambe le estensioni assicurati di leggere la documentazione o le istruzioni fornite con ciascuna estensione per massimizzarne l'utilità e per affrontare eventuali configurazioni specifiche necessarie per il tuo ambiente di sviluppo.
> 

Il linguaggio Lua è un linguaggio procedurale per un uso generico, cioè può essere usato per tutto (giochi o semplici programmi), ad esempio alcuni Lua projects sono:

1. Adobe Photoshop Lightroom
2. Apache HTTP Server
3. Awesome WM
4. Roblox
5. Angry Birds
6. The Sims 2: Night Life
7. Mafia 2
8. World of Warcraft
9. Fable 2

# Come installare Lua 
Per installare Lua bisogna andare sul sito ufficiale [Lua.org](https://lua.org/) > andare alla sezione Download> Sotto la voce "Building", cliccare sul link [get a binary](https://luabinaries.sourceforge.net/) > in seguito andare su download (si trova sulla sinistra)> scegliere la versione di Lua da scaricare ed installare in base alla compatibilità con il proprio computer e sistema operativo. 
Per gli utilizzatori di Windows, [guardate questo video](https://www.youtube.com/watch?v=VyZfvnBLqIU&list=PLYBJzqz8zpWavt37pA6NANJTGStIHpybU&index=20&ab_channel=Steve%27steacher).




