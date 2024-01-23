# 00 - L'entorn de desenvolupament integrat Arduino (IDE)

[img01]: ./../imatges/ard/ard-00-01.png "IDE Arduino"
[img02]: ./../imatges/ard/ard-00-02.png "Barra d'eines"
[img03]: ./../imatges/ard/ard-00-03.png "Barra de menú"

Anem a presentar l'entorn de desenvolupament integrat Arduino (IDE, nom generat per la seua sigla en anglés). És el software que ens permet programar les plaques arduino i cal conèixer-lo per tal de treure tot el profit de la seua potència i característiques.

L'entorn de desenvolupament integrat Arduino (IDE) conté:

1. un editor de text per escriure codi,
2. una àrea de missatges,
3. una consola de text,
4. una barra d'eines amb botons per a funcions habituals
5. una sèrie de menús.

Es connecta a les plaques Arduino per carregar programes i comunicar-se amb ells.

![IDE Arduino][img01]

## Escriure esbossos (sketch)

Els programes escrits amb el programari Arduino (IDE) s'anomenen esbossos o «sketches». Aquests esbossos s'escriuen a l'editor de text i es guarden amb l'extensió de fitxer **.ino**. L'editor té funcions per copiar / enganxar i per cercar / substituir text.

L'àrea de missatges proporciona comentaris mentre es desa i s'exporta i també mostra errors. La consola mostra la sortida de text del programari Arduino (IDE), inclosos missatges d'error complets i altra informació.

A l'extrem inferior dret de la finestra es mostra la placa configurada i el port sèrie.

Els botons de la barra d'eines us permeten verificar i penjar programes, crear, obrir i desar esbossos i obrir el monitor sèrie.

### Els botons de la barra d'eines

![Barra d'eines][img02]

- **Verifica**. Comprova el codi per si hi han errors abans de compilar-lo.
- **Puja**. Compila el codi i el penja a la placa configurada.
- **Nou**. Crea un esbós nou.
- **Obre**. Presenta un menú amb tots els esbossos del sketchbook. Si feu clic a un, s'obrirà en una nova finestra.
- **Desa**. Guarda el vostre esbós.
- **Monitor sèrie**. Obre el monitor sèrie.

Es troben ordres addicionals als cinc menús: **Fitxer, Edita, Croquis, Eines, Ajuda**. Els menús són sensibles al context, cosa que significa que només hi ha disponibles els elements rellevants per al treball que s'està realitzant actualment.

![Barra de menú][img03]

### Fitxer

- **Nou.** Obre una nova finestra de l'editor, amb l'estructura mínima d'un esbós ja instal·lada.
- **Obre.** Permet carregar un fitxer d'esbós navegant per les unitats i carpetes de l'ordinador.
- **Obre Recent.** Ofereix una llista breu dels esbossos més recents, a punt per obrir-se.
- **Sketchbook.** Mostra els esbossos actuals dins de l'estructura del Sketchbook; en fer clic a qualsevol nom s'obrirà l'esbós corresponent en una nova finestra de l'editor.
- **Exemples.** Qualsevol exemple proporcionat pel programari Arduino (IDE) o la biblioteca pareix en aquest element del menú. Tots els exemples s'estructuren en un arbre que permet un fàcil accés per tema o biblioteca.
- **Tanca.** Tanca la finestra del programari Arduino des del qual es fa clic.
- **Desa.** Guarda l'esbós amb el nom actual. Si el fitxer no s'ha nomenat abans, es proporcionarà un nom a la finestra "Anomena i desa ...".
- **Anomena i desa ...** Permet desar l'esbós actual amb un nom diferent.
- **Configuració de la pàgina.** Mostra la finestra de configuració de la pàgina per imprimir.
- **Imprimeix.** Envia l'esbós actual a la impressora segons els paràmetres definits a Configuració de pàgina.
- **Preferències.** Obre la finestra Preferències, on es poden personalitzar alguns paràmetres de l'IDE, com a idioma de la interfície IDE.
- **Surt.** Tanca totes les finestres IDE. Els mateixos esbossos oberts quan es va triar _Surt_ es tornaran a obrir automàticament la propera vegada que inicieu l'IDE.

### Edita

- **Desfés / Refés.** Retrocedeix un o més passos que heu fet mentre editeu; quan torneu enrere, podeu avançar amb Refés.
- **Retalla.** Elimina el text seleccionat de l'editor i el col·loca al porta-retalls.
- **Copia.** Duplica el text seleccionat a l'editor i el col·loca al porta-retalls.
- **Copia per al fòrum.** Copia el codi del vostre esbós al porta-retalls en un formulari adequat per publicar-lo al fòrum, amb color de sintaxi.
- **Copia com a HTML.** Copia el codi del vostre esbós al porta-retalls com a HTML, adequat per inserir-lo a pàgines web.
- **Enganxa.** Posa el contingut del porta-retalls a la posició del cursor, a l'editor.
- **Selecciona-ho tot.** Selecciona i ressalta tot el contingut de l'editor.
- **Ves a la línia ...** Demana i posiciona el cursor a la línia indicada.
- **Comenta o descomenta.** Posa o suprimeix el marcador de comentaris **//** al començament de cada línia seleccionada.
- **Augmenta / Disminueix el sagnat.** Afegeix o resta un espai al principi de cada línia seleccionada, movent el text un espai a la dreta o eliminant un espai al principi.
- **Incrementa / Redueix la mida del tipus de lletra.** Fa més gran / menuda la mida de la lletra del sketch.
- **Cerca.** Obre la finestra _Cerca i reemplaça_ on podeu especificar text per buscar dins del sketch actual segons diverses opcions.
- **Cerca el següent.** Destaca la següent ocurrència (si n'hi ha) de la cadena especificada com a element de cerca a la finestra _Cerca_, en relació amb la posició del cursor.
- **Cerca l'anterior.** Destaca l'ocurrència anterior (si n'hi ha) de la cadena especificada com a element de cerca a la finestra Cerca en relació amb la posició del cursor.

### Esbós

- **Verifica / Compila.** Comprova el vostre esbós buscant errors en compilar-lo; informarà de l'ús de memòria per al codi i les variables a l'àrea de la consola.
- **Pujar.** Compila i carrega el fitxer binari a la placa configurada a través del port configurat.
- **Càrrega mitjançant Programador.** Això sobreescriurà el carregador d'arrencada a la placa; haureu d'utilitzar _Eines\> Grava_ el carregador d'arrencada per restaurar-lo i poder tornar a carregar al port sèrie USB. Tot i això, us permet utilitzar tota la capacitat de la memòria Flash per al vostre esbós. Tingueu en compte que aquesta ordre NO cremarà els fusibles. Per fer-ho, s'ha d'executar una ordre _Eines -\> Grava_ el carregador d'arrencada.
- **Exporta binari compilat.** Desa un fitxer **.hex** que es pot conservar com a arxiu o enviar-lo a la placa mitjançant altres eines.
- **Mostra la carpeta del Sketch.** Obre la carpeta d'esbossos actual.
- **Inclou la biblioteca.** Afegeix una biblioteca al vostre esbós inserint declaracions _\#include_ al començament del codi. A més, des d'aquest element de menú podeu accedir al gestor de biblioteques i importar biblioteques noves des de fitxers **.zip.**
- **Afegeix un fitxer \...** Afegeix un fitxer font a l'esbós (es copiarà des de la seva ubicació actual). El fitxer nou apareix en una nova pestanya a la finestra d'esbós. Els fitxers es poden esborrar de l'esbós mitjançant el menú de pestanyes accessible fent clic a la icona de triangle petit que hi ha a sota del monitor de sèrie al costat dret de la barra d'eines.

### Eines

- **Format automàtic.** Això formata molt bé el vostre codi: és a dir, sagnar-lo de manera que l'obertura i el tancament de les claus arrissades s'alineïn i que les declaracions dins de les claus queden més recorregudes.
- **Arxiva el programari.** Arxiva una còpia de l'esbós actual en format .**zip**. L'arxiu es col·loca al mateix directori que l'esbós.
- **Arregla la codificació i torna a carregar.** Corregeix possibles discrepàncies entre la codificació de mapes de caràcters de l'editor i altres mapes de sistemes de funcionament.
- **Monitor sèrie.** Obre la finestra del monitor sèrie i inicia l'intercanvi de dades amb qualsevol placa connectada al port seleccionat actualment. Normalment, es reinicia la placa, si la placa admet _Reinici per obertura del port sèrie._
- **Plotter sèrie.** Aplicació que ens permet dibuixar gràfiques.
- **Placa:** Seleccioneu el tauler que feu servir.
- **Port.** Aquest menú conté tots els dispositius en sèrie (reals o virtuals) del vostre equip. S'actualitzarà automàticament cada vegada que obriu el menú d'eines.
- **Informació de la placa.** Dona informació de la placa connectada.
- **Programador**. Per seleccionar un programador de placa quan es programa una placa o un xip i no s'utilitza la connexió sèrie USB integrada. Normalment no necessitareu això.
- **Enregistra el Bootloader**. Els elements d'aquest menú us permeten gravar un carregador d'arrencada al microcontrolador d'una placa Arduino. Això no és necessari per a l'ús normal d'una placa Arduino o Genuino, però és útil si adquiriu un microcontrolador ATmega nou (que normalment no inclou un carregador d'arrencada). Assegureu-vos que heu seleccionat la placa correcta al menú Placa abans de gravar el carregador d'arrencada a la placa de destinació. Aquesta ordre també estableix els fusibles adequats.

### Ajuda

Aquí trobareu fàcil accés a diversos documents que inclouen el
programari Arduino (IDE). Teniu accés a Introducció, Referència, una
guia de l'IDE i altres documents localment, sense connexió a Internet.
Els documents són una còpia local dels documents en línia i poden
enllaçar al nostre lloc web en línia.

**Cerca a la referència.** Aquesta és l'única funció interactiva del
menú Ajuda: selecciona directament la pàgina pertinent a la còpia local
de la referència per a la funció o l'ordre que hi ha sota el cursor.

## Veure també

- [Index](../Index.md)
- [README](../README.md)
