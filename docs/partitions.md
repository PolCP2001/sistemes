## Particions

Quan executem la màquina virtual per primera vegada apareixerem a la configuració inicial d'Ubuntu. Durant aquest procediment podrem configurar les particions.


### Configuració inicial pas a pas


Comencem per seleccionar l'idioma amb que treballarà el nostre *SO*. En aquest cas nosaltres seleccionem **català**.

![Lang](Imatges/particions/01.png)


Deixarem la distribució del teclat en **espanyol** i amb la variant **Espanyol - Català** que apareix predefinida al seleccionar el llenguatge català.

![Keyboard](Imatges/particions/02.png)


Deixarem la connexió a internet establerta segons el nostre cas.

![IntCon](Imatges/particions/03.png)


Sel·leccionarem que volem **instal·lar el sistema Ubuntu**.

![Inst](Imatges/particions/04.png)


Deixarem seleccionada la **instal·lació interactiva**.

![IntInst](Imatges/particions/05.png)


Per aquesta màquina demanarem que ens instal·li la **sel·leció per defecte** de programari.

![Prog](Imatges/particions/06.png)


Per optimitzar el la nostra màquina **seleccionarem les dos opcions** a la part de *Install recommended propietary software?*.

![PropSoft](Imatges/particions/07.png)


### Configuració de les particions


Per a començar en essència amb la part de configurar les particions, al tipus d'instal·lació seleccionarem aquest cop  **'alguna altra cosa'**.

![InstType](Imatges/particions/09.png)


Clicarem sobre l'icona blanca del disc dur i ens dirigirem baix a l'esquerra i clicarem sobre l'icona de **+** per afegir una nova partició. En aquest cas, la nostra màquina disposa de 26.84 GB. així que farem les següents particions, clicant sobre *Espai lliure* i l'icona **+** cada cop que acabem de crear-ne una de nova.
 
> **Primera**:	Espai: 1.00 GB	Tipus: Swap	Punt de muntatge: '-'
>
> **Segona**:	Espai: 17.50 GB	Tipus: Ext4	Punt de muntatge: /home 
>
> **Tercera**:	Espai: 6.70 GB	Tipus: Ext4	Punt de muntatge: /
>
> **Quarta**:	Espai: 1.64 GB	Tipus: '-'	Punt de muntatge: '-'

![ManPart](Imatges/particions/11.png)


Registrarem el nostre usuari i nom de l'ordinador. En aquest moment crearem també una contrasenya per a l'usuari i deixarem activa la selecció **fes que calgui una contrasenya per entrar**.

![UserLog](Imatges/particions/12.png)


Seleccionarem al mapa la nostra franja horaria.

![FuseMap](Imatges/particions/13.png)


Després de confirmar les nostres configuracions a la taula que se'ns proporcionarà finalitzarem fent clic sobre **comença a instal·lar**.

![ConfEnd](Imatges/particions/14.png)
