# Gestió de pòlisses/contractes

## Tarifes d'accés

Les tarifes d'accés que venen definides amb l'ERP són les que marca la legislació
vigent.

- 2.0TD (0 - 15 kW)
- 3.0TD (més de 15 kW) 
- 6.1TD (tensió entre 1 kV i 30 kV)
- 6.2TD (tensió entre 30 kV i 72,5 kV)
- 6.3TD (tensió entre 72,5 kV kV i 145 kV)
- 6.4TD (tensió igual o superiors a 145 kV)

## Pòlisses/contractes

En el model de la pòlissa es troben els camps que indiquen a quin client pertany, quina tarifa té actualment,
comercialitzadora, poténcia contractada, tipus de facturació, data de la próxima facturació, históric de comptadors,
les seves lectures, etc.

En el menú principal podem trobar el llistat de pólisses a **Menú → Gestió de Pólisses**.

![](_static/polizas/menu.png)

### Donar d'Alta una pòlissa

Per donar d'alta una pòlissa s'ha d'emplenar una sèrie de camps amb el fi que la facturació funcioni correctament.

Es selecciona el botó **Nou** de la barra de botons i es procedeix a completar les dades de les diferents pestanyes.

#### Pestanya General

![](_static/polizas/polissa_general.png)

* Client: Nom del client.    
  Es pot buscar un client ja existent i si no existeix es [dona d'alta un nou
  client](partners.md#donar-dalta-un-clientempresa).
* Comercialitzadora: Nom de la Comercialitzadora.
    * La Comercialitzadora es sel·leccionarà de la llista d'empreses amb el botó
      _lupa_. Si no existeix la comercialitzadora s'haurà de [donar d'alta una nova
      empresa](partners.md#donar-dalta-un-clientempresa).
    * Requeriments imprescindibles per que la comercialitzadora estigui correctament
      entrada: (destacat visualment en les imatges següents)
        * A la pestanya _General_: Nom de l'empresa, ID de l'empresa i Direcció de
          contacte amb "Tipus Direcció: Factura".
        * A la pestanya _Informació Extra_: Actiu sí, NIF.
        * A la pestanya _Propietats_: Tot introduït correctament
        * Tipo de Pago introduït.

![](_static/polizas/polissa_facturacio.png)

![](_static/polizas/polissa_contacte.png)

!!! Info "Nota"
    En l'apartat _Tipo de pago_ es pot introduïr uns valors com els que es mostren
    en l'última imatge de la sèrie.

!!! Warning "Atenció"
    A la fitxa de la comercialitzadora, recorda que el camp _Empresa ID_ es el
    **codi de comercialitzadora de REE**.

* Pòlissa: Codi de la nova pòlissa
* CNAE: S'ha d'escollir un codi de CNAE de la taula existent que conté tots els
  codis CNAE actualitzats en el INE
* CUPS: S'ha d'assignar un CUPS existent o crear un de nou. Si el CUPS es
  existent, es pot buscar amb la _lupa_, amb l'ajuda de filtres per municipi,
  població, carrer i número. La direcció del CUPS s'ha de connectar a la pòlissa
  que s'està creant.   

    * Si l'escomesa es nova, s'haurà de [crear un nou CUPS].

    !!! Warning "Atenció"
        Abans de crear un nou CUPS comproba que realment no existeix un en la
        direcció que busques. Comproba també que no estigui desactivat.

* Data d'alta: S'ha de sel·leccionar la data d'alta de la pòlissa amb el
  calendari que hi ha a la dreta del camp.
* Activa: La pòlissa per defecte està activa i només es desactivarà quan s'hagi
  donat de baixa i s'hagi realitzat la última facturació.

    !!! Info "Nota"
        No es pot desactivar una pòlissa fins que s'hagi realitzat la última
        facturació. Veure l'apartat [Donar de baixa una pòlissa].

* Data de Baixa: S'indicarà a nivell informatiu la data de baixa de la pòlissa,
  que hauria de coincidir amb la data de baixa del últim comptador associat.
* Baixa: Es marcarà la casella baixa en el moment de posar la data de baixa.
  I es mantindrà la casella activa marcada fins que s'hagi realitzat l'última
  factura d'aquesta pòlissa.
* Estat: Camp informatiu per indicar si la pòlissa està en tràmit, pendent de
  documentació...
* Tarifa: S'ha de sel·leccionar, utilitzant el botó _lupa_, una de les tarifes
  vigents en el moment de fer l'alta.

    ![](_static/polizas/tarifes.png)

    !!! Info "Nota"
        Una vegada sel·leccionada la tarifa, i **després de guardar el registre**,
        en la part inferior aparaixeràn els periodes de la tarifa, que s'haurà
        d'emplenar amb la potenca contractada en cadascún d'ells.

    !!! Warning "Atenció"
        Al sel·leccionar una tarifa 3.1, s'ha d'observar que la tarifa amb la
        descripció **"Tarifa 3.1A LB"** indica que la lectura es realitza en baixa
        tensió.

* Facturació: S'ha de sel·leccionar en el camp combinat un dels dos tipus de
  facturació: "mensual" o "bimestral"
* Pròxima facturació: Amb el calendari de la part dreta del camp, s'ha de
  sel·leccionar la data de la pròxima facturació perquè entri al cicle de
  facturació de forma correcte.
* Tensió: S'indicarà la tensió del subministre (230, 400)
* Potencia: En aquest camp s'indicarà la potència màxima contractada dels
  diferents periodes. El camp de _Potencia_ en els filtres de sel·lecció de les
  pòlisses fa referencia a aquest camp. Veure [normalització potencia](#ajuda-normalitzacio-de-potencia)
* Facturació Potencia: En aquest camp s'indicarà el tipus de facturació de la
  pòlissa sel·leccionant si es fa per ICP o per la regla del maxímetre.
* ICP: S'indicarà la intensitat del ICP instal·lat i/o marca del mateix.
* Consum anual: No s'hi ha d'indicar cap valor.
* Trafo kVA: Aquest camp només s'ha de cumplimentar amb la potència del
  transformador en el cas d'un subministre en AT amb mesura en baixa
  (_Tarifa 3.1A con medida BT_).   
  El valor d'aquest camp s'utilitzarà per al càlcul de la facturació de les
  tarifes: _3.1A con medida BT_
* Pot máx instalador: Es la potència màxima autoritzada en el boletí del
  instal·lador.
* Potencia Acta: Es la potència del acta del instal·lador (camp informatiu)

#### Ajuda normalització de potència

Al costat de la potència contractada hi ha el botó de **Normalitzar**.

![](_static/polizas/pot_norm_1.png)

Aquest botó llança un assistent que ens ajuda a seleccionar una potència normalitzada nova o a normalitzar la potència contractada actual. S'utilitza la **tensió normalitzada** i la **tarifa d'accés** per a llistar les potències normalitzades possibles.

Quan es llança l'assistent selecciona la potència normalitzada **més pròxima a l'actual**.

![](_static/polizas/pot_norm_2.png)

I amb el botó d'assignar s'actualitza la potència contractada amb la normalitzada

![](_static/polizas/pot_norm_3.png)

#### Pestanya de Comptadors

En la pestanya de Comptadors es troba l'històric dels comptadors que han estat
relacionats amb la pòlissa. Apareixen tots els que han passat per la pòlissa que
es troben en estat _"No Actiu"_ i únicament el que es troba actualment
instal·lat està _"Actiu"_.

!!! Info "Nota"
    Recorda que el campo _N. comptador_ ha de contenir el mateix **número de
    serie** del comptador actiu de la llista de la part inferior del formulari.   
    Les cerques a les pòlisses del número de comptador, són les del camp _N.
    comptador_

En cas de necessitar donar d'alta un comptador, cal seguir el [procediment per
donar d'alta un comptador](../distri/contadores.md#donar-dalta-un-comptador)

![](_static/polizas/polissa_comptadors.png)

### Donar de Baixa una pòlissa

Per donar de baixa una pòlissa en una data determinada s'han de tenir en compte
els següents punts.

**A la pestanya General:**

* El camp _Data de Baixa_: S'hi indicarà la data en que es farà efectiva la
  data de baixa de la pòlissa i ha de coincidir amb la data de baixa de
  comptador associat.
* La casella _Baixa_: Es marcarà la casella _Baixa_ en el moment de posar la
  _data de baixa_.   
  Es mantindrà la casella _Activa_ fins que s'hagi realitzat l'última factura
  d'aquesta pòlissa.
* La casella _Activa_: Es desactivarà quan s'hagi realitzar l'última factura
  d'aquesta pòlissa.   
  Dependrà de si es "mensual" o "bimestral".

!!! Warning "Atenció"
    No es pot desactivar la pòlissa fins haver realitzat l'última facturació.

**A la pestanya Comptadors:**

Al comptador actiu s'han de completar els següents camps:

* El camp _Data Baixa_: S'hi indicarà la data en la que es retira el comptador.   
  Coincidirà amb la _Data Baixa_ de la pòlissa.   
  Aquesta data s'utilitzarà per facturar el terme de potencia de la última
  factura i només tindrà en compte els dies des de l'última facturació fins la
  data.
* La casella _Activa_: Es desactivarà quan s'hagi realitzat l'última facturació
  de la pòlissa.   
  Dependrà de si es "mensual" o "bimestral".

!!! Warning "Atenció"
    No es pot desactivar la pòlissa fins haver realitzat l'última facturació.

### Realitzar canvi de titularitat

Un canvi de titularitat d'una pòlissa suposa [donar de baixa una
pòlissa](#donar-de-baixa-una-polissa) i [donar d'alta una
pòlissa](#donar-dalta-una-polissa) nova amb les dades del nou titular.

### Canvi de la potencia contractada

Per realitzar el canvi de potencia contractada ha de realitzar-se al inici del
periode de facturació de la pòlissa.   
Si s'ha de realitzar el canvi enmig d'un periode de facturació s'haurà de fer
[una baixa de la pòlissa](#donar-de-baixa-una-polissa) i [donar d'alta una
pòlissa](#donar-dalta-una-polissa) perquè es poguin facturar correctament els
termes de potència de cada un dels contractes.

### Canvi de la tarifa

Si el canvi de potencia, que es faci a l'inici d'un periode de facturació,
suposi un canvi de tarifa de peatge, s'haurà de fer un canvi de comptador. Per
realitzar-ho cal [donar de baixa el comptador] i [donar d'alta un nou comptador]
inicialitzat amb les lectures dels diferents periodes de la nova tarifa.

!!! Info "Nota"
    Sempre s'ha d'inicialitzar un nou comptador amb les lectures dels periodes
    de la nova tarifa.   
    Recorda que cada peruide d'una tarifa es un producte diferent. (p.e. P1(2.0)
    es un producte i P1(2.1) es un altre producte)

## Formulari d'una pòlissa/contracte

### Secció general

* **Pòlissa**
* **Auto**
* **Data firma contracte**
* **Activa**
* **Renovació automàtica**
* **Distribuidora**
* **Referència distribuidora**
* **Titular**
* **CNAE**
* **Data alta**
* **Data baixa**

### Pestanya general

* **CUPS**
* **Direcció CUPS**
* **Tarifa d'accés**
* **Potència contractada**
* **Tensió**
* **Potències contractades per període**
* **Tipus de vivenda**

### Contactes

* **NIF Titular**

### Modificacions contractuals

* **Modificació contractual actual**
* **Llistat de modificacions contractuals**

### Observacions

* **Observacions**

## Estats de les pòlisses

Les pòlisses tenen certs estats en els que es troben en un moment donat:
esborrany, activa, baixa, etc, i aquests estats governen el comportament i el
paper d'aquesta. Es tracta d'una dinàmica que segueix cada pòlissa i que forma
un recorregut lògic.

![Descripció dels \label{workflows}](_static/polizas/workflows.svg)
*Fluxograma dels estat de les pòlisses i les transicions*

![](_static/polizas/indicador_estat_polissa.png)
*Vista general de la pòlissa amb el camp "estat" indicat*

Al crear una pòlissa, aquesta per defecte s'estableix en un estat de
**Esborrany**. Una pòlissa en Esborrany permet canviar les dades abans de
confirmar-les.

Després de prémer el botó de "Validar", l'estat de la pòlissa serà **Validar**.
Aquest estat es l'anterior al de activa, en el que l'ERP t'informa de quines
dades no compleixen els requeriments.

Quan les dades estàn validades i són correctes, l'estat de la pòlissa passa a
ser **Activa**. Com indica el nom, l'estat de Activa indica que una pòlissa
està en vigor; que s'hi poden fer modificacions contractuals, i passar a altres
estats com Impagament.

Des de **Impagament** es podrà o bé donar de baixa la pòlissa, passar en estat
de **Tall**, o bé reactivar-la.

Des de Activa, també es poden fer **Modificacions Contractuals**. Per una
explicació més detallada d'aquestes, consultar
[aquesta](#modificacions-contractuals_1) pàgina.

També es podrà donar de **Baixa** una pòlissa o **Cancel·lar-la**.

## Històric de canvis en els estats d'una pòlissa

En el formulari principal de la pòlissa, hi ha una pestanya que és **Històric**,
on pots veure per tots els estats que ha passat la pòlissa, quan han estat
canviats i quin usuari els ha canviat. Això permet tenir un control sobre el
flux d'aquesta.

![](_static/polizas/historic_estats.png)

## Contractes de tipus eventual

Un contracte eventual és un tipus de contracte amb una duració determinada,
aquests es solen realitzar per events de curta duració, com poden ser
fires, certàmens, etc.

Dins d'aquests contractes en podem distingir dos tipus:

* **Contracte eventual sense comptador**: aquests són contractes d'una duració
màxima de dos mesos en els quals per llei no fa falta un comptador, el consum es
calcularà a partir d'una fórmula (Potència contractada * dies de contracte * hores diaries).

* **Contracte eventual amb comptador**: a diferencia del contracte anterior aquest
sí que disposa de comptador per poder calcular el consum.

### Càlcul del consum total per contractes eventuals sense comptador

Aquest tipus de contractes es caracteritzen per no tenir comptador, per tant no
es pot tenir una mesura exacte del consum total, per calcular-ho s'utilitzarà la
següent fórmula:


`Consum total = Potència contractada * dies de contracte * hores d'ús diàries`

### Assistent per calcular el consum total

Per tal de facilitar aquest càlcul s'ha afegit un assistent dins el menú de
gestió de pòlisses.


Dins el menú de gestió de pòlissa, en cas de que el tipus de contracte sigui
eventual sense comptador ens apareixerà la opció per calcular-ne el consum total:

![](_static/polizas/assistent_consum_eventual/cat/polissa_cat.png)

Per iniciar l'assistent premerem el botó calcular:

| Assistent amb camp sense precalcular                               | Assistent amb camp precalculat                         |
|--------------------------------------------------------------------|--------------------------------------------------------|
| ![](_static/polizas/assistent_consum_eventual/cat/wiz_no_pre_cat.png) |![](_static/polizas/assistent_consum_eventual/cat/wiz_pre_cat.png)|

Un cop comprovat que les dades son correctes premem el botó calcular.

!!! Info "Nota"
        L'opció precalcular és opcional, serveix per comprovar els càlculs
        abans de calcular-los i apareixeran al camp consum de l'assistent.

Finalment, un cop calculat el camp ja apareixarà al menú de gestió de pòlissa.

![](_static/polizas/assistent_consum_eventual/cat/polissa_calc_cat.png)


En el cas que hi hagi una modificació contractual el camp del consum apareixerà
a la pestanya de facturació de la modificació.

![](_static/polizas/assistent_consum_eventual/cat/mod_contract_cat.png)

## Visualització deute d'una pòlissa/contracte

Podem visualitzar el deute d'una pòlissa/contracte a través del seu formulari,
tenim els camps **Estat pendent**, **Quantitat pendent** i **Quantitat deute**.

![](_static/polizas/pending_amount_form.png)

* **Quantitat pendent**: Indica els euros que aquesta pòlissa està pendent de
  pagar. Ja sigui perquè és d'una devolució o perquè encara no s'ha remesat.

* **Quantitat deute**: Indica els euros que deu aquesta pòlissa que són d'impagament.
  Agafa la quantitat residual de totes les factures que el seu estat pendent no
  sigui **Correcte**.

* **Estat pendent**: Mostra el *pitjor* estat de totes les pòlisses que no estiguin
  en estat correcte.

També podem llistar **totes** les pòlisses/contractes que tinguin algun deute a
través del menú: **Gestió de pòlisses > Pòlisses amb deute** on es pot veure en
cada contracte quin estat i deute tenen i un sumatori de tot deute del llistat.

![](_static/polizas/pending_amount_list.png)

Per més informació es pot llegir la seccció de [gestió d'impagats](/comer/gestion_impago.md) en comercialització.


## Subministrament no tallable

Podem marcar una pòlissa com a **subministrament no tallable**. Existeixen
dos tipus de motius per fer-ho: els que vénen definits en el BOE
([24/2013 Article 52 punt 4](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2013-13645)),
o els que anem creant nosaltres mateixos

!!! Info "Nota"
    En el cas de les distribuidores un subministrament no tallable, hauria
    de venir definit pel BOE (que ja venen pre-carregats)
    En el cas de les comercialitzadores un subministrament no tallable pot ser
    també per motiu comercial.

### Marcar una pòlissa com a no tallable

Des d'una pòlissa, podem seleccionar un dels motius no
tallables. Si tenim la pòlissa marcada com a activa ho haurem de fer mitjançant
una modificació contractual.

![](_static/polizas/BotoSubministramentNoTallable.png)

Aquí podem seleccionar el motiu, i també podem filtrar: per nom del motiu,
per si és un motiu definit al BOE o no, i per descripció.

![](_static/polizas/FormulariMotius.png)

![](_static/polizas/FiltrarMotius.png)

### Crear nous motius

També podem definir motius de no tallable des del mateix formulari que acabem
de veure, o des del menú de **Gestió de Pòlisses > Configuració > Motius no
tallables**.
En el dos casos farem clic sobre el botó nou. En el cas del formulari, el
trobarem a la barra d'eines inferior (veure imatge anterior). I en el cas
d'estar a l'apartat de configuració de pòlisses, el trobarem a la barra d'eines
del menú superior, tal com veiem a la següent imatge

![](_static/polizas/NouMotiu.png)

Per definir el motiu emplenem els camps de nom, descripció i BOE si és el cas.
Guardem els canvis, i es crea el motiu, i s'afegeix a motius de subministrament
no tallable.

### Llistar les pòlisses no tallables

Per llistar totes les pòlisses no tallables, accedirem al menù: **Configuració
de Pòlisses > Pòlisses > Pòlisses no tallables**

![](_static/polizas/RutaNoTallables.png)

I ens llistarà totes les pòlisses que tenen assignat un motiu de
subministrament no tallable

### Permisos

Aquesta funcionalitat està reservada pels usuaris que siguin del grup
**GISCEDATA Pòlissa /CutOff**, per tant que tinguin permisos específics per
interactuar amb els motius de subministrament no tallable.    
La resta d'usuaris podran llistar totes les pòlisses que tenen un motiu de
subministrament no tallable, i veure el motiu de no tall. Però no podran crear
ni assignar motius.

## Canvi data firma contracte

En un contracte podem actualitzar la data de firma de contracte sense la
necessitat de fer una modificació contractual mitjançant un assistent creat
expresament

Des de una pólissa o des del botó acció del llistat de pólisses podem prèmer
sobre el botó **Actualitzar data firma contracte**. Ens apareixerà el formulari
següent, on podrem veure la pólissa seleccionada i la data de firma
de contracte actual (si en té). Prement en el botó continuar, actualitzarà la
data de firma de contracte de la **pólissa** i la **modificació contractual
activa**.

!!! Warning "Atenció"
    No es farà cap tipus de validació sobre la data introduïda. Si és una data
    vàlida es modificarà la data actual sense tenir en compte cap altra
    consideració com la data d'alta i de baixa de la pòlissa o la data actual

![](_static/polizas/WizardDataFirmaContracte.png)

## Modificacions contractuals

### Desfer una modificació contractual

Per desfer una modificació contractual, cal seleccionar d'entre la llista de
modificacions contractuals la que està **activa**.

Un cop seleccionada es pot veure com apareix un botó per desfer la modificació
contractual:

![](_static/polizas/boto_undo.png)

Al fer click al botó apareixerà un avís per pantalla el qual informa que l'acció
no es pot desfer.

Si es confirma, la modificació contractual activa serà eliminada i la
modificació contractual anterior es reactivarà. Altrament, la modificació
contractual es mantindrà sense canvis.

!!! Info "Nota"
    No es podrà desfer cap modificació contractual si la pòlissa no es troba
    en estat **actiu**

## Gestió del dipòsit de garantia (fiança)

La gestió del dipòsit de garantia va integrada amb el mòdul de facturació,
tant en distribuïdora com en comercialitzadora. En aquest aparat s'explica
l'aspecte general de la gestió.

En la fitxa del contracte s'afegeix un camp **Dipòsit**.

![](_static/polizas/deposit_camp.png)

Aquest camp sempre és el **saldo** del dipòsit que tenim en aquests moments.
Funciona igual que la comptabilitat, però només tenint en compte els
moviments del producte que tinguem configurat com a diposit de garantia.

Amb l'avantatge que tenim una **traçabilitat completa** i un **històric** de tots
els moviments de fiances que hi ha hagut. Per tant es poden generar els informes
necessaris per l'administració sense que afecti el dia a dia.

![](_static/polizas/deposit_conf.png)

Quan es factura un producte fiança s'increment aquest saldo i quan es retorna
es redueix.

### Devolució del dipòsit de garantia

Es disposa d'un assistent per tal de fer la devolució de la fiança, està en
el marge dret a la llista d'assistents disponibles d'un contracte.

![](_static/polizas/deposit_devolucio.png)

Aquest assistent agafa com a valors predeterminats:

  * A qui es retorna la fiança: **el titular**.
  * La quanitat a retornar: **saldo actual**
  * El número de compte: **el compte associat al contracte** (En el cas que es
    vulgui afegir a una remesa.)

![](_static/polizas/deposit_assistent_devolucio.png)

## CNAE

El CNAE (Clasificación Nacional de Actividades Económicas) és un codi de 4
xifres amb una estructura en forma d'arbre.

Per exemple, el codi 61 pertany a _"Telecomunicaciones"_ mentre que el 061
pertany a _"Extracción de crudo de petróleo"_. Conforme es van afegint dígits
es va concretant de forma més exacte l'activitat de l'abonat.

Per això és necessari concretar un CNAE de **4 dígits** que descrigui
**l'activitat concreta de l'abonat**.

Per fer-ho cal fer click al botó de la lupa a l'apartat **CNAE** al **crear **
**una nova pòlissa**:

![](_static/polizas/cnae.png)

Llavors apareix la llista de CNAEs a escollir:

![](_static/polizas/llista_cnae.png)


## Autoconsum

El camp _"autoconsumo"_ ens indica el tipus de consum que te el client, segons aquest camp seran requerits uns tipus de comptadors els quals estan definits a la següent taula:

|Tipus | PF | G | C |
|-|-|-|-|
|**Sense Autoconsum**|x | | |
|**Tipus 1**|x |x | |
|**Tipus 2 a)**| |x |x|
|**Tipus 2 b)**|x|x| |
|**Serveis Auxiliars**|x | | | |
