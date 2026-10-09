# Lionel Messi · La storia del 10

Archivio editoriale indipendente, in italiano. Versione 9 ottobre 2026; orari mostrati in UTC+2.

## Pubblicazione — esattamente cinque file
Caricare insieme nella stessa cartella pubblica: `index.html`, `styles.css`, `app.js`, `media.js`, `README.md`. Nessuna compilazione, dipendenza npm, cartella di immagini o database. Aprire index.html oppure pubblicare su qualunque host statico HTTPS. L'apertura locale mantiene la lettura inclusa; gli aggiornamenti automatici partono su HTTP/HTTPS.

Le immagini sono incorporate come data URL in media.js, i font in styles.css. Non rimuovere media.js: contiene tutte le fotografie, gli stemmi e i trofei. Il pacchetto è ampiamente sotto 28 MB anche contando i dati Base64 non compressi.

## Design e funzioni
Tema esclusivamente scuro; menu mobile; filtri per squadra; aggiornamento statistiche; galleria di trofei con dialogo accessibile e fotografie di dettaglio; archivio fotografico con visualizzatore a schermo intero, tasti freccia e Escape; palmarès espandibile; cronologia; biografia; fonti e crediti. HTML semantico, navigazione da tastiera, focus visibile, testo alternativo, riduzione del movimento. Le fotografie storiche sono fotografie reali: la hero usa una fotografia originale con una composizione grafica dedicata, senza scene sintetiche.

## Statistiche ufficiali aggiornabili
Fonte primaria: https://messi.com/ e https://messi.com/estadisticas-totales/.
Lettura diretta del servizio WordPress pubblico di messi.com, verificato con CORS:
- https://messi.com/wp-json/wp/v2/pages/73?_fields=content,modified
- https://messi.com/wp-json/wp/v2/pages/3313?_fields=content,modified

app.js legge il contenuto pubblico, verifica lo schema, somma i quattro contesti per confrontarli con i totali e rifiuta letture inconsistenti o regressive. Il parser elimina la compensazione animata di 0,5 presente nei contatori ufficiali. La disponibilità futura e il formato del servizio dipendono da messi.com; non è un'API contrattualmente garantita.

Timeout 12 secondi; cache localStorage con durata 5 minuti; aggiornamento manuale; tentativo all'apertura e al ritorno della scheda dopo la scadenza. La data indica l'acquisizione effettiva, non l'aggiornamento editoriale del fornitore. In caso di errore resta il dato valido precedente con il suo timestamp, senza azzeramenti o dati inventati. Il conteggio degli assist può differire dagli archivi dei club. I titoli includono Under 20 e Olimpiadi secondo la fonte primaria.

## Partite live — configurazione facoltativa
Il pacchetto non contiene chiavi API né risultati simulati. Nel CONFIG di app.js, impostare `liveEndpoint` con l'URL HTTPS di un gateway esterno che autorizzi l'origine del sito via CORS. Le credenziali di API-Football, Sportmonks o altro provider devono risiedere esclusivamente sul gateway, mai nei cinque file pubblici. Il gateway non è incluso nel pacchetto statico.

Formato JSON previsto:
```json
{"source":"API-Football","acquiredAt":"2026-10-08T22:00:00Z","fixtures":[{"home":"Inter Miami","away":"Avversario","homeGoals":1,"awayGoals":0,"status":"Secondo tempo","elapsed":65}]}
```
Polling ogni 15 secondi con partite presenti, 60 secondi senza partite; sospensione quando la scheda è nascosta; cache dell'ultimo risultato valido. Verificare piano, quota, licenza e copertura del provider selezionato.
Documentazione: https://www.api-football.com/documentation-v3 ; https://docs.sportmonks.com/football ; https://www.thesportsdb.com/api.php . Nessun abbonamento o credenziale è stato attivato.

## Altre fonti
FIFA: https://inside.fifa.com/en/tournaments/mens/worldcup/qatar2022/news/triumphant-argentina-conclude-unprecedented-fifa-world-cup ; https://www.fifa.com/en/tournaments/mens/worldcup/articles/messi-final-farewell . Il dato di 26 presenze è esplicitamente riferito al 2022.
FC Barcelona: https://www.fcbarcelona.com/en/card/2214377/leo-messi .
Transfermarkt: https://www.transfermarkt.com/lionel-messi/profil/spieler/28003 . Collegamento per dettagli stagionali e mercato; valore non riprodotto perché non verificato.
Biografia, premi e fondazione: https://messi.com/biografia/ ; https://messi.com/palmares/ ; https://messi.com/fundacion-leo-messi/ .

## Crediti delle immagini e diritti
Archivio indipendente, non affiliato a Messi o ai club. Gli stemmi sono autentici e non ridisegnati. Marchi e materiali ufficiali restano dei titolari. Le immagini da messi.com non hanno una licenza pubblica di riuso verificata; l'attribuzione non equivale ad autorizzazione commerciale. Per una pubblicazione commerciale ottenere le autorizzazioni necessarie. Le fotografie Creative Commons conservano attribuzione e licenza; eventuali adattamenti delle immagini BY-SA seguono la stessa licenza. Tutte le fonti sono consultabili anche nel sito.

### Messi Logo
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2019/10/messi-logo-01.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Official Messi brand emblem; trademark rights remain.

### Newells Logo
//www.newellsoldboys.com.ar/ · Public domain

https://commons.wikimedia.org/wiki/File:Newell%27s_Old_Boys_Escudo.png

Licenza: https://commons.wikimedia.org/wiki/File:Newell%27s_Old_Boys_Escudo.png

Authentic club/federation mark; trademark rights remain with owner. Copyright status follows linked source; this does not grant a trademark license.

### Barcelona Logo
FC Barcelona · PD

https://en.wikipedia.org/wiki/File:FC_Barcelona_(crest).svg

Licenza: https://en.wikipedia.org/wiki/File:FC_Barcelona_(crest).svg

Authentic club/federation mark; trademark rights remain with owner. Copyright status follows linked source; this does not grant a trademark license. Public-domain claim is US-only; possibly non-free in source country.

### Psg Logo
Paris Saint-Germain Football Club · PD

https://en.wikipedia.org/wiki/File:Paris_Saint-Germain_F.C..svg

Licenza: https://en.wikipedia.org/wiki/File:Paris_Saint-Germain_F.C..svg

Authentic club/federation mark; trademark rights remain with owner. Copyright status follows linked source; this does not grant a trademark license. Public-domain claim is US-only; possibly non-free in source country.

### Miami Logo
Inter Miami CF · Fair use

https://en.wikipedia.org/wiki/File:Inter_Miami_CF_logo.svg

Licenza: https://en.wikipedia.org/wiki/File:Inter_Miami_CF_logo.svg

Authentic club/federation mark; trademark rights remain with owner. Copyright status follows linked source; this does not grant a trademark license. Wikipedia hosts under non-free fair-use rationale; no general reuse permission is supplied.

### Argentina Logo
Argentine Football Association · Public domain

https://commons.wikimedia.org/wiki/File:Argentine_Football_Association_logo.svg

Licenza: https://commons.wikimedia.org/wiki/File:Argentine_Football_Association_logo.svg

Authentic club/federation mark; trademark rights remain with owner. Copyright status follows linked source; this does not grant a trademark license.

### Messi Barcelona
www.realvalladolid.es · CC BY-SA 4.0

https://commons.wikimedia.org/wiki/File:Real_Valladolid_-_FC_Barcelona,_2018-08-25_(55).jpg

Licenza: https://creativecommons.org/licenses/by-sa/4.0

Original resized and compressed to WebP only. CSS cropping may be used. Attribution and linked license required for Creative Commons images.


### Messi Miami
Bryan Berlin · CC BY-SA 4.0

https://commons.wikimedia.org/wiki/File:Lionel_Messi_NYCFC_Miami_24_Sep_2025-096.jpg

Licenza: https://creativecommons.org/licenses/by-sa/4.0

Original resized and compressed to WebP only. CSS cropping may be used. Attribution and linked license required for Creative Commons images.

### Trophy Worldcup
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2020/03/mundial-futbol.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Transparent official trophy cutout at original small dimensions.

### Trophy Ballon
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2020/03/balon-de-oro.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Transparent official trophy cutout at original small dimensions.

### Trophy Champions
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2020/03/champions.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Transparent official trophy cutout at original small dimensions.

### Trophy Copa
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2021/07/Copa-america.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Transparent official trophy cutout at original small dimensions.

### Trophy Liga
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2020/03/liga.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Transparent official trophy cutout at original small dimensions.

### Trophy Boot
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2020/03/boat-d_or.png

Licenza: https://messi.com/

Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Transparent official trophy cutout at original small dimensions.

### Messi · Argentina a Qatar 2022
Hossein Zohrevand / Tasnim News Agency · CC BY 4.0

https://commons.wikimedia.org/wiki/File:Lionel-Messi-Argentina-2022-FIFA-World-Cup.jpg

Licenza: https://creativecommons.org/licenses/by/4.0/

Ridimensionamento e compressione WebP. Il layout può ritagliare la fotografia.

### Messi · Argentina a Qatar 2022
Hossein Zohrevand / Tasnim News Agency · CC BY 4.0

https://commons.wikimedia.org/wiki/File:Lionel_Messi_WC2022.jpg

Licenza: https://creativecommons.org/licenses/by/4.0/

Ridimensionamento e compressione WebP. Il layout può ritagliare la fotografia.

## Licenze dei font
Font locali Manrope e Oswald, SIL Open Font License 1.1.

### Manrope-OFL.txt

```text
Copyright 2018 The Manrope Project Authors (https://github.com/googlefonts/manrope)

This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is copied below, and is also available with a FAQ at:
http://scripts.sil.org/OFL


-----------------------------------------------------------
SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007
-----------------------------------------------------------

PREAMBLE
The goals of the Open Font License (OFL) are to stimulate worldwide
development of collaborative font projects, to support the font creation
efforts of academic and linguistic communities, and to provide a free and
open framework in which fonts may be shared and improved in partnership
with others.

The OFL allows the licensed fonts to be used, studied, modified and
redistributed freely as long as they are not sold by themselves. The
fonts, including any derivative works, can be bundled, embedded, 
redistributed and/or sold with any software provided that any reserved
names are not used by derivative works. The fonts and derivatives,
however, cannot be released under any other type of license. The
requirement for fonts to remain under this license does not apply
to any document created using the fonts or their derivatives.

DEFINITIONS
"Font Software" refers to the set of files released by the Copyright
Holder(s) under this license and clearly marked as such. This may
include source files, build scripts and documentation.

"Reserved Font Name" refers to any names specified as such after the
copyright statement(s).

"Original Version" refers to the collection of Font Software components as
distributed by the Copyright Holder(s).

"Modified Version" refers to any derivative made by adding to, deleting,
or substituting -- in part or in whole -- any of the components of the
Original Version, by changing formats or by porting the Font Software to a
new environment.

"Author" refers to any designer, engineer, programmer, technical
writer or other person who contributed to the Font Software.

PERMISSION & CONDITIONS
Permission is hereby granted, free of charge, to any person obtaining
a copy of the Font Software, to use, study, copy, merge, embed, modify,
redistribute, and sell modified and unmodified copies of the Font
Software, subject to the following conditions:

1) Neither the Font Software nor any of its individual components,
in Original or Modified Versions, may be sold by itself.

2) Original or Modified Versions of the Font Software may be bundled,
redistributed and/or sold with any software, provided that each copy
contains the above copyright notice and this license. These can be
included either as stand-alone text files, human-readable headers or
in the appropriate machine-readable metadata fields within text or
binary files as long as those fields can be easily viewed by the user.

3) No Modified Version of the Font Software may use the Reserved Font
Name(s) unless explicit written permission is granted by the corresponding
Copyright Holder. This restriction only applies to the primary font name as
presented to the users.

4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font
Software shall not be used to promote, endorse or advertise any
Modified Version, except to acknowledge the contribution(s) of the
Copyright Holder(s) and the Author(s) or with their explicit written
permission.

5) The Font Software, modified or unmodified, in part or in whole,
must be distributed entirely under this license, and must not be
distributed under any other license. The requirement for fonts to
remain under this license does not apply to any document created
using the Font Software.

TERMINATION
This license becomes null and void if any of the above conditions are
not met.

DISCLAIMER
THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE
COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL
DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM
OTHER DEALINGS IN THE FONT SOFTWARE.

```

### Oswald-OFL.txt

```text
Copyright 2016 The Oswald Project Authors (https://github.com/googlefonts/OswaldFont)

This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is copied below, and is also available with a FAQ at:
https://scripts.sil.org/OFL


-----------------------------------------------------------
SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007
-----------------------------------------------------------

PREAMBLE
The goals of the Open Font License (OFL) are to stimulate worldwide
development of collaborative font projects, to support the font creation
efforts of academic and linguistic communities, and to provide a free and
open framework in which fonts may be shared and improved in partnership
with others.

The OFL allows the licensed fonts to be used, studied, modified and
redistributed freely as long as they are not sold by themselves. The
fonts, including any derivative works, can be bundled, embedded, 
redistributed and/or sold with any software provided that any reserved
names are not used by derivative works. The fonts and derivatives,
however, cannot be released under any other type of license. The
requirement for fonts to remain under this license does not apply
to any document created using the fonts or their derivatives.

DEFINITIONS
"Font Software" refers to the set of files released by the Copyright
Holder(s) under this license and clearly marked as such. This may
include source files, build scripts and documentation.

"Reserved Font Name" refers to any names specified as such after the
copyright statement(s).

"Original Version" refers to the collection of Font Software components as
distributed by the Copyright Holder(s).

"Modified Version" refers to any derivative made by adding to, deleting,
or substituting -- in part or in whole -- any of the components of the
Original Version, by changing formats or by porting the Font Software to a
new environment.

"Author" refers to any designer, engineer, programmer, technical
writer or other person who contributed to the Font Software.

PERMISSION & CONDITIONS
Permission is hereby granted, free of charge, to any person obtaining
a copy of the Font Software, to use, study, copy, merge, embed, modify,
redistribute, and sell modified and unmodified copies of the Font
Software, subject to the following conditions:

1) Neither the Font Software nor any of its individual components,
in Original or Modified Versions, may be sold by itself.

2) Original or Modified Versions of the Font Software may be bundled,
redistributed and/or sold with any software, provided that each copy
contains the above copyright notice and this license. These can be
included either as stand-alone text files, human-readable headers or
in the appropriate machine-readable metadata fields within text or
binary files as long as those fields can be easily viewed by the user.

3) No Modified Version of the Font Software may use the Reserved Font
Name(s) unless explicit written permission is granted by the corresponding
Copyright Holder. This restriction only applies to the primary font name as
presented to the users.

4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font
Software shall not be used to promote, endorse or advertise any
Modified Version, except to acknowledge the contribution(s) of the
Copyright Holder(s) and the Author(s) or with their explicit written
permission.

5) The Font Software, modified or unmodified, in part or in whole,
must be distributed entirely under this license, and must not be
distributed under any other license. The requirement for fonts to
remain under this license does not apply to any document created
using the Font Software.

TERMINATION
This license becomes null and void if any of the above conditions are
not met.

DISCLAIMER
THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE
COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL
DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM
OTHER DEALINGS IN THE FONT SOFTWARE.

```

## Immagine del trionfo mondiale
Immagine ufficiale: https://static.messi.com/wp-content/uploads/2022/12/MESSI-Stats-COPA.jpg

Copyrighted official asset; no public reuse license stated. Authentic photographic asset from official Messi website. No Creative Commons or blanket reuse grant verified; rights remain with respective holders. Official website composition; resized/compressed only.

## Icone e nuova direzione visiva
Phosphor Icons, famiglia Regular, MIT. SVG incorporati come simboli nello stesso HTML, senza dipendenze esterne. Fonte: https://github.com/phosphor-icons/core .

Nessuna impostazione del tema è più letta o scritta. L’interfaccia è solo scura. La cache dei dati resta invariata.

### Fotografia del trofeo · trophy-champions-photo
David Flores · CC BY 2.0

https://commons.wikimedia.org/wiki/File:Trofeo_UEFA_Champions_League.jpg

https://creativecommons.org/licenses/by/2.0

Authentic photograph. Resized and compressed only; no crop, cutout or redraw. CSS crop possible with linked license/attribution retained.



### Licenza Phosphor Icons
```text
MIT License

Copyright (c) 2023 Phosphor Icons

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

```


## Selezione fotografica rivista — 9 ottobre 2026
11 fotografie selezionate. Rimosse foto mosse o deboli, soggetti troppo piccoli, fotografie senza rapporto con il passaggio narrativo e la Scarpa d’Oro di un altro giocatore. Il PSG utilizza un vero scatto ufficiale PSG–Nantes del 2021; il Pallone d’Oro mostra Messi con il suo premio del 2023; il saluto all’Argentina usa l’immagine dell’annuncio del 7 ottobre 2026. Dove manca una fotografia appropriata, la cronologia mantiene il testo senza un’immagine sostitutiva fuorviante. Il marchio LaLiga del 2023 è stato tolto dal racconto degli anni di Messi a Barcellona.

Le immagini ufficiali mantengono i watermark; nessuna licenza pubblica di riuso verificata, come indicato nei crediti. Nessun ingrandimento artificiale del file sorgente; i trofei piccoli sono presentati con dimensioni più contenute.

### New York City FC–Inter Miami — 24 settembre 2025
Bryan Berlin · CC BY-SA 4.0

https://commons.wikimedia.org/wiki/File:Lionel_Messi_NYCFC_Miami_24_Sep_2025-081.jpg

Licenza/diritti: https://creativecommons.org/licenses/by-sa/4.0/

### PSG–Nantes · 2021
Leo Messi official website; individual photographer not identified · Copyrighted official image; no public reuse license verified

https://messi.com/en/galeria/?mgi_45=16230%2Fpsg-v-nantes

Licenza/diritti: https://messi.com/terminos-y-condiciones/

### Ritratto di Messi con l’Argentina.
Hossein Zohrevand / Tasnim News Agency · CC BY 4.0

https://commons.wikimedia.org/wiki/File:Lionel_Messi_WC2022.jpg

Licenza/diritti: https://creativecommons.org/licenses/by/4.0/

### Ottavo Pallone d’Oro · Parigi, 2023
Leo Messi official website; individual photographer not identified · Copyrighted official image; no public reuse license verified

https://messi.com/leo-gana-su-octavo-balon-de-oro/

Licenza/diritti: https://messi.com/terminos-y-condiciones/

### Il capitolo americano, con Inter Miami.
Bryan Berlin · CC BY-SA 4.0

https://commons.wikimedia.org/wiki/File:Lionel_Messi_NYCFC_Miami_24_Sep_2025-096.jpg

Licenza/diritti: https://creativecommons.org/licenses/by-sa/4.0

### Composizione fotografica ufficiale pubblicata da messi.com.
Leo Messi official website; individual photographer/designer not specified · Copyrighted official asset; no public reuse license stated

https://static.messi.com/wp-content/uploads/2022/12/MESSI-Stats-COPA.jpg

Licenza/diritti: https://messi.com/

### PSG–Nantes · 2021
Leo Messi official website; individual photographer not identified · Copyrighted official image; no public reuse license verified

https://messi.com/en/galeria/?mgi_45=16230%2Fpsg-v-nantes

Licenza/diritti: https://messi.com/terminos-y-condiciones/

### Il saluto all’Argentina · fonte ufficiale, 7 ottobre 2026
Leo Messi official website; individual photographer not identified · Copyrighted official image; no public reuse license verified

https://messi.com/emotivo-adios-de-leo-con-la-seleccion-con-un-gol-y-doble-asistencia/

Licenza/diritti: https://messi.com/terminos-y-condiciones/

### New England Revolution–Inter Miami — 9 luglio 2025
Bryan Berlin · CC BY-SA 4.0

https://commons.wikimedia.org/wiki/File:Lionel_Messi_NE_Revolution_Inter_Miami_7.9.25-143.jpg

Licenza/diritti: https://creativecommons.org/licenses/by-sa/4.0/

### Messi in campo con il Barcellona.
www.realvalladolid.es · CC BY-SA 4.0

https://commons.wikimedia.org/wiki/File:Real_Valladolid_-_FC_Barcelona,_2018-08-25_(55).jpg

Licenza/diritti: https://creativecommons.org/licenses/by-sa/4.0

### Messi con l’Argentina a Qatar 2022.
Hossein Zohrevand / Tasnim News Agency · CC BY 4.0

https://commons.wikimedia.org/wiki/File:Lionel-Messi-Argentina-2022-FIFA-World-Cup.jpg

Licenza/diritti: https://creativecommons.org/licenses/by/4.0/
