# Documentació dels informes per distribuidores

## Resum per tarifes

Resum de facturació per tarifes amb el desglosament dels consums segons els
periodes i energia. L'informe inclou el resum en kWh, potència total, euros
facturats i nombre de clients afectats

## Resum per distribuïdora i tarifa

Resum de facturació per distribuïdora i tarifa amb el desglosament dels consums
segons els periodes i energia. L'informe inclou el resum en kWh, potència total,
euros facturats i nombre de clients afectats

## Resum per grup cobratori

Resum per grup de cobrament. Inclou el nombre de factures i el total facturat

## Resum per municipi i tarifa

Resum de facturació per municipi i tarifa. Inclou el desglosament dels consums
segons els periodes i energia. L'informe inclou el resum en kWh, potència total,
euros facturats i nombre de clients afectats

## Detall per període i tarifa de peatge

Resum de facturació per tarifes que inclou el detall de l'energia facturada,
potència facturada i potència contractada per periode

## Resum per impostos i distribuïdora

Resum de facturació per distribuïdora. Detalla base, impostos i total en
euros facturats.

## Detall d'altres conceptes

Resum de facturació per distribuïdora que inclou únicament els productes de
tipus 'Altres'. El resum mostra els totals facturats.

## Resum Factures (CSV)

Resum de les factures en CSV.

## Resum factures Excel

Resum de les factures en Excel.

## ESCILA

Informe ESCILA

## Model 606

En la ubicació que es mostra en la següent imatge es troba el menú per a la
realizació de l'informe de preus de consumidors, model 606 que es detalla
en el BOE n. 69  Sec. I. Pàg. 30271.

![Figura 1](../_static/informes/model_606/menu_wiz.png)

El wizard de realització de l'informe es mostra en la següent imatge:

![Figura 2](../_static/informes/model_606/wizard.png)

Tal i com s'especifica en l'annex I del BOE esmentat anteriorment
l'informe, que s'entregarà dos cops l'any,  ha de recollir la informació
dels darrers 6 mesos. El període en qüestió s'especificarà en els apartats
'Data d'inici' i 'Data final'. La opció 'Extrapolar el consum anual', es
sel·leccionarà únicament en el cas de no existir històric d'un any (12 mesos
faturats complets), cas en que caldrà especificar el factor de correcció
a aplicar al resultat. Per exemple, en el cas de tenir històric dels darrers
6 mesos, s'indicarà a l'ERP que extrapoli el conum i en el factor de correcció
es sel·leccionarà 2. Si diposéssim de 12 mesos facturats únicament caldria
[Exemples de configuració](#exemples-de-configuracio)

En finalitzar l'informe, es mostrarà el següent missatge:

![Figura 3](../_static/informes/model_606/accept.png)

En acceptar-se ens llistarà l'informe.

![Figura 4](../_static/informes/model_606/inf_llist.png)

Únicament cal prémer fent doble-click al damunt de l'informe per veure'n
el resultat. La següent imatge mostra el resultat d'un informe.

![Figura 5](../_static/informes/model_606/linies_informe.png)

Finalment podem mostrar tots els informes generats anant al sub-menú
que s'indica a continuació

![Figura 6](../_static/informes/model_606/menu_llist.png)

Que resulta en el llistat de la següent imatge:

![Figura 7](../_static/informes/model_606/tot_llist.png)

Únicament caldria fer doble-click al damunt de l'informe escollit
per veure'n la seva informació.

### Exemples de configuració

Cas 1: Hem facturat des de 01/01/2012 a 30/06/2012 (6 mesos)

 * Extrapolar consum: Sí
 * Factor de correcció: 2 (**2** x 6 mesos = 12 mesos)

Cas 2: Tenim factures de 01/04/2012 a 30/06/2012 (3 mesos)

 * Extrapolar el consum: Sí
 * Factor de correcció: 4 (**4** x 3 mesos = 12 mesos)

Cas 3: Tenim 12 mesos d'històric de facturació:

 * Extrapolar el consum: No
 * Factor de correcció: 1

## Model 159

En la ubicació que es mostra en la següent imatge:

![Figura 8](../_static/informes/model_159/menu.png)

Es troba el menú per a la generació de l'informe del model 159,
tal i com es detalla en el BOE n. 182 Sec. I. Pàg. 64838.

La següent imatge mostra el wizard de generació de l'informe:

![Figura 9](../_static/informes/model_159/wiz_generar.png)

Es generarà un nou informe amb la data final indicada en prémer 'Generar informe'.

En finalitzar el procés de realització de l'informe es mostren els errors trobats:

![Figura 10](../_static/informes/model_159/wiz_mostrar.png)

Prement 'Veure Informe' es llista l'informe generat:

![Figura 11](../_static/informes/model_159/imp_inf.png)

Finalment, fent doble click en l'informe generat, veurem les línies de l'informe:

![Figura 12](../_static/informes/model_159/linia_tree.png)

I tindrem la possibilitat d'exportar-lo prement 'Exportar document'.

En exportar el document, es sol·licita informació relativa a la
persona de contacte, informació relativa al suport que s'utilitzarà
per la transmissió del document i el número d'informe que es correspon. El
número d'informe és un número seqüencial relatiu a cada informe entregat.

### Valors per defecte

Per tal que el resultat de la validació sigui correcte, hi ha una sèrie de
camps als quals se'ls assigna un valor per defecte en cas de no tenir valor
a l'ERP. La següent taula en detalla el nom del camp, la posició
en la línia del registre de tipus 2 i el valor assignat per defecte.

 Camp               |  Posició   |  Valor
:-------------------|:----------:|:------------------------------------------------------------------------------------------------
 NIF del titular    |  18        | 12345678Z
 Tipus de via       |  76        | CL
 Tipus de numeració |  131       | NUM o S/N (en funció de si hi ha número)
 Codi postal        |  264       | 12321
 Data d'alta        |  367       | 01/07/2009 (data d'inici del règim de lliure competència) en el cas de ser anterior a l'any 1930

### Errors de validació


El programa de validació del model 159, en la versió [v1.0 de 2011](http://www.agenciatributaria.es/static_files/AEAT/Contenidos_Comunes/La_Agencia_Tributaria/Descarga_Programas/Descarga/prevalid/2011/CobolWindows/Prevalidacion_159_2011_v10.exe)
, genera una sèrie d'errors pels quals no hi ha sol·lució. Es llisten a continuació:

  Codi d'error  |  Camp                                                 | Motiu
:--------------:|:------------------------------------------------------|:------------------------------------------------------------
   2 0801       |  Tipus de via (Direcció del subministre)              | Certs tipus de via proporcionats pel catastre.
   2 0701       |  Cognoms i nom, raó social o denominació del titular  | Noms que contenen nombres. També noms amb una única paraula.


##### Figura 13: Wizard per exportar l'informe.

![](../_static/informes/model_159/wiz_exportar.png)

##### Figura 14: Llistat de tots els informes generats.

![](../_static/informes/model_159/imp_tree.png)