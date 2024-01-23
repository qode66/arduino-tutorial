# 01 - El nostre primer programa

[img1]: ./../imatges/ard/ard_01_01.jpg "Compilador"
[img2]: ./../imatges/ard/ard_01_02.png "Entrades i eixides"
[img3]: ./../imatges/ard/ard_01_03.png "Verifica"
[img4]: ./../imatges/ard/ard_01_04.png "Puja"

## Objectius

La idea d'aquesta lliçó és fixar algunes idees bàsiques sobre
programació. Tenim que comprendre l'estructura d'un programa arduino
(sketch), hem de definir les estructures de blocs i conèixer les
primeres instruccions.

## Algunes idees bàsiques sobre programació

Un **programa d'ordinador** és bàsicament l'equivalent a una _recepta
de cuina_... però destinat a un públic diferent.

Mentre que les persones som raonablement bones _interpretant_ les
instruccions, generalment vagues, d'una recepta de cuina, quan
programem qui ha d'entendre'ns és un ordinador que espera instruccions
precises respecte al que ha de fer i que a més manca per complet de la
imaginació o capacitat d'improvisació humana.

Per això es desenvolupen els llenguatges d'ordinador, per a donar
instruccions a una màquina de forma:

- Precisa: Sense ambigüitats inherents a la comunicació humana.
- Unívoca: Només es pot interpretar d'una manera.
- Concisa: Preferiblement órdens curtes.

El IDE de Arduino es programa en una variant de C++ , que és un
llenguatge molt estés per les seues característiques, encara que no és
un llenguatge senzill. C++, que fixa regles estrictes de com escriure
aquestes instruccions.

Un programa és una sèrie d'instruccions que s'executen en seqüència (
llevat que indiquem expressament condicions precises en les quals
aquesta seqüència s'altera).

Un programa intern comprova que la sintaxi del nostre programa és
conforme a la norma de C++, i si hi ha qualsevol cosa que no li convenç
donarà un error i finalitzarà la comprovació obligant-nos a revisar el
que hem escrit.

Quan el comprovador accepta el nostre programa, invoca un altre programa
que tradueix el que hem escrit a instruccions comprensibles per al
processador del nostre Arduino. A aquest nou programa se'n diu
compilador.

![Compilador][img1]

El compilador converteix les nostres instruccions (codi font) en
instruccions del processador (codi executable).

## Estructura d'un programa Arduino

Un programa o Sketch de Arduino consisteix en dues seccions o funcions
bàsiques:

- _Setup: Les seues instruccions s'executen només una vegada, quan
  s'arranca el programa en encendre Arduino o quan premem el botó de
  reset. Generalment inclou definicions i inicialitzacions d'ací el
  seu nom._
- _Loop: Les seues instruccions es van executant en seqüència fins al
  final.... I quan acaba, torna a començar des del principi fent un
  cicle sense fi._

Quan obrim el **IDE de Arduino** (o fem Menú\Arxiu\nou) ell ens escriu ja aquestes dues funcions (en color cobre):

Note's que el principi de cada funció és indicat per l'obertura de
clau " { " i la fi de la mateixa correspon al símbol de tancar claus " }
".

De fet el conjunt d'instruccions contingudes entre una obertura i
tancament de claus es diu **bloc** i és de cabdal importància a l'hora
que el nostre **Arduino** interprete de l'una o l'altra manera les
instruccions que li donem.

És imperatiu que a cada obertura d'una clau corresponga un tancament de
clau. En successius capítols ampliarem aquest concepte.

Ara com ara ressaltar les línies que apareixen dins dels blocs
principals:

// put your setup code here, to run once

// put your main code here, to run repeatedly

Qualsevol cosa que escriguem precedit per " // " son comentaris, i seran
ignorats. És a dir podem deixar-nos missatges dins del codi, (que d'una
altra manera donarien errors). El compilador ignorarà qualsevol cosa
entre // i la fi de línia.

## Primeres instruccions en Arduino C++

Sembla obligat en el món **Arduino**, que el primer programa que fem
siga el blinking LED, i està bé perquè il·lustra algunes idees
interessants quant a les seues possibilitats:

- La capacitat de Arduino per a interactuar amb el món extern. Una
  cosa bastant inusitada per als qui estiguen acostumats a la
  informàtica tradicional, on la potència de càlcul ha crescut de
  manera espectacular, però continua sent impossible (o quasi),
  influir en el món exterior.
- La senzillesa de l'entorn de treball. En contraposició a un sistema
  tradicional d'editor/compilador/linker.

Arduino pot relacionar-se de diferents maneres amb el món que li
envolta, Començarem pels pins digitals que poden usar-se com:

- Entrades: Per a llegir informació digital del món exterior.
- Eixides: Per a activar un senyal al món exterior.

![Entrades i eixides][img2]

Arduino disposa de 14 pins que poden ser usats d'aquesta manera,
numerats del 0 al 13.

En la lliçó anterior carregarem un programa d'exemple que fa
parpellejar un LED en la placa amb una cadència definida. Vegem com
programar això.

Demanarem a Arduino que active el seu pin 13 com d'eixida digital i
després encendrem i apagarem aquest senyal el que farà que el LED que té
connectat de sèrie s'encenga o apague al ritme que marquem.

Per a indicar al sistema que desitgem usar el pin 13 com a eixida
digital utilitzem la instrucció:

```Arduino
pinMode ( 13, OUTPUT ) ;
```

El primer paràmetre indica el pin a usar i "OUTPUT" és per a usar-lo com
a eixida, i també podria usar-se el valor "INPUT" per a indicar que
llegirem d'aquest pin.

Aquestes definicions es faran només una vegada al principi, en la funció
setup(). La nostra quedarà, amb una única instrucció que declara que
usarem el pin 13 com a eixida digital:

```Arduino
void setup()
{
// inicialitza el pin 13 com eixida digital
pinMode( 13, OUTPUT) ;
}
```

- És important fixar-se en què malgrat ser una única instrucció, hem
  delimitat el bloc d'aquesta funció mitjançant obrir i tancar claus.
- Observe's que la instrucció finalitza en " ;" . C++ obliga a
  acabar les instruccions amb un punt i coma que delimite l'ordre. Si
  s'omet generarà un error.

Per a encendre el LED usarem la instrucció:

```Arduino
digitalWrite( 13 , HIGH) ;
```

I una altra instrucció similar que li ordena apagar-ho:

```Arduino
digitalWrite( 13 , LOW) ;
```

El 13 indica el pin a utilitzar i HIGH, LOW indiquen el valor que
desitgem posar en aqueixa eixida, que en Arduino corresponen a 5V per a
HIGH i 0V per a LOW.

- Si en la funció loop() escriguérem aquestes dues instruccions
  seguides, Arduino canviaria aquests valors tan de pressa que no
  percebríem canvis, així que necessitem frenar-li una mica perquè
  puguem percebre el canvi.

Per a fer aquest retard de, diguem, un segon, utilitzarem:

```Arduino
delay(1000) ; //delay(n) "congela" Arduino n mil·lisegons
```

Per tant per a programar una llum que s'encén i s'apaga, hauríem de
generar una seqüència d'ordres (_Com en una recepta e cuina_) que
feren:

1. Informar a Arduino que utilitzarem el pin13 per a escriure valors(en el setup).
2. Encendre el LED : Posar valor alt ( 5V) en aquest pin.
3. Esperar un segon.
4. Apagar el LED: Posar valor baix (0V) en aquest pin.
5. Tornar a esperar un segon.

   - _Si ometérem aquest segon retard, apagaria la llum i tornaria a començar trobant-se l'ordre de tornar a encendre. No apreciaríem que s'havia apagat.(No espere que em cregueu. Comproveu-ho)._
   - _El processador de Arduino UNO és molt lent des del punt de vista electrònic, però és capaç de commutar la llum (passar d'encesa a apagat i volta a encendre) unes 15.000 vegades per segon._

El primer concepte que heu de fixar, és que els ordinadors processen les
ordenes en seqüència, una instrucció després d'una altra i en l'ordre
en què li les doneu. _El nostre programa instrueix a l'ordinador perquè
execute aqueixes instruccions i fixa l'ordre en el qual s'executen._

La manera d'escriure un programa en Arduino C++ que faça
l'anteriorment descrit és alguna cosa semblança a això :

```Arduino
//Codi: ARD_01.ino

void setup()
{
    pinMode( 13 , OUTPUT); // Usarem el pin 13 com a eixida
}

void loop()
{
    digitalWrite(13 , HIGH); // Encén el LED
    delay(1000); // Esperar un segon
    digitalWrite(13 , LOW); // Apagar el LED
    delay(1000); // Esperar un altre segon
}
```

- Note's el sagnat de les línies per a destacar els blocs de codi. Això es considera bona pràctica i us ho recomanem encaridament, perquè facilita molt la comprensió del programa.
- Quan us equivoqueu ( i creeu-me, us equivocareu) el sagnat ajuda,i molt, a visualitzar el programa.
- Només hi ha dos tipus de programadors. Els que s'equivoquen i els que s'equivocaran

Només ens falta ja, comprovar si hi ha errors i per a això premem la icona en blanc:

![Verifica][img3]
Si
tot va bé, ( si no hi ha errors en roig) podem compilar i bolcar amb la
següent fletxa, En cas contrari ( i creieu-me que us passarà amb
freqüència) caldrà revisar els possibles errors i corregir-los. Tornarem
sobre això en el futur.

![Puja][img4]

La fletxa en blanc bolcara el nostre programa al Arduino i podrem
comprovar que la llum del pin 13 parpelleja amb un retard d'un segon
entre encesa i apagat.

- Suggeriment: Si modifiquem els valors del delay, modificarem la
  cadència del parpelleig.
- Nota: Això no funcionara amb cap altre Pin del Arduino UNO, perquè
  només el 13 té un LED connectat.

## Resum de la lliçó

En aquesta lliçó hem aprés diverses coses importants:

- El concepte clau d'un programa, com a seqüència d'instruccions que s'executa en l'ordre marcat.
- Hi ha dues funcions bàsiques en tot programa Arduino: setup() i loop()..
- Per a delimitar un bloc d'instruccions usem obertura i tancament de claus.
- Totes les instruccions acaben en punt i coma (Encara que hi ha excepcions).
- Podem usar comentaris usant //
- Hem aprés algunes instruccions inicials del Arduino C++.

## Veure també

- [Index](../Index.md)
- [README](../README.md)
