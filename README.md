![Version](https://img.shields.io/github/v/release/DCMLab/couperin_concerts?display_name=tag)
[![DOI](https://zenodo.org/badge/388404044.svg)](https://doi.org/10.5281/zenodo.15027239)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/couperin_concerts)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/couperin_concerts](https://github.com/DCMLab/couperin_concerts) and the corresponding
* documentation page [https://dcmlab.github.io/couperin_concerts](https://dcmlab.github.io/couperin_concerts)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/couperin_concerts/introduction).

When you use (parts of) this dataset in your work, please read and cite the accompanying data report:

_Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the 
empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z_

# François Couperin – Concerts Royaux (A corpus of annotated scores)

This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards).
It represents 14 concerts composed by François Couperin (1668-1733) and the trio sonata Apothéose
de Corelli. In the 1710s Couperin started to compose a series of Concerts which were performed first 1714/15 at Sunday
concerts for king Louis XIV. Later he published four of them as Concerts Royaux together with the Troisième livre of the
Pièces de Clavecin in 1722, whereas the concerts nos. 5–14 were published as Les Goûts-réünis ou Nouveaux Concerts
together with the Apothéose de Corelli in 1724. The concerts are written for a melody instrument and figured bass but
can also be performed as Harpsichord pieces or with added middle voices; some of those were given by the composer. The
detailed basso continuo figures (except nos. 12 and 13) allow a quite exact harmonic annotation considering some
research about French basso continuo practice. These annotations will provide considerable support to future
quantitative study of Baroque harmony, major-minor tonality, the use of the rule of the octave, cadences and schemata.

-- _Prof. Johannes Menke_

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/couperin_concerts/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [couperin_concerts.zip](https://github.com/DCMLab/couperin_concerts/releases/latest/download/couperin_concerts.zip)
  * [couperin_concerts.datapackage.json](https://github.com/DCMLab/couperin_concerts/releases/latest/download/couperin_concerts.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/couperin_concerts.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first *Prélude* of the first concert has the following files:

* `MS3/c01n01_prelude.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/c01n01_prelude.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/c01n01_prelude.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/c01n01_prelude.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/c01n01_prelude.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/c01n01_prelude.harmonies.tsv")
notes = ms3.load_tsv("notes/c01n01_prelude.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/couperin_concerts/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/couperin_concerts/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Scores

### Concerts Royaux

Figures added by Tom Schreyer who also corrected the scores typeset by Gouin.

### Nouveaux Concerts, ou Les Goûts-Réunis

Typeset by Tom Schreyer

Concerts 12 & 13 not annotated

## File naming convention

Example: `c01n01_prelude`.

The filenames follow the pattern `c<##>n<##>_<movement>` where

* `c` = concert number (01-14)
* `n` = movement number (01-11)
* `movement` = beginning of the movement title in lowercase and without diacritics

The seven movements of _Le Parnasse, ou L'Apothéose de Corelli_ form an exception and have
the pattern `parnasse_<##>`.

The regular expression for parsing all filenames is 
`(?P<concert>c\d{2}|parnasse)[_n](?P<movementNumber>\d{2})(?:_(?<movementName>.+))?`.

where `concert` can either take the value `c<##>` or `parnasse`. In the latter case, 
the `movementName` group remains empty.

## Overview
|         file_name          |measures|labels|standard|                   annotators                    |      reviewers       |
|----------------------------|-------:|-----:|--------|-------------------------------------------------|----------------------|
|c01n01_prelude              |      23|    94|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c01n02_allemande            |      18|    78|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c01n03_sarabande            |      28|    68|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c01n04_gavotte              |      14|    54|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c01n05_gigue                |      30|   139|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c01n06_menuet_en_trio       |      24|    47|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c02n01_prelude              |      37|    88|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c02n02_allemande_fuguee     |      24|   121|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c02n03_air_tendre           |      40|    86|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c02n04_air_contrefugue      |      62|   154|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c02n05_echos                |      85|   148|2.3.0   |Eva-Maria Hamberger (2.1.0), Hanné Becker (2.3.0)|Johannes Menke (2.1.0)|
|c03n01_prelude              |      18|    83|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n02_allemande            |      17|   111|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n03_courante             |      25|   105|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n04_sarabande_grave      |      32|    72|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n05_gavotte              |      25|    85|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n06_musette_1            |      28|    28|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n07_musette_2            |      27|    34|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c03n08_chaconne_legere      |     128|   287|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n01_prelude              |      14|    86|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n02_allemande            |      14|    77|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n03_courante_francoise   |      21|    85|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n04_courante_a_litalienne|      73|   145|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n05_sarabande            |      24|    48|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n06_rigaudon             |      41|    62|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c04n07_forlane              |      55|   149|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c05n01_prelude              |      52|    99|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c05n02_allemande            |      43|   154|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c05n03_sarabande            |      24|    54|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c05n04_gavote               |      32|   104|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c05n05_musete               |      54|   118|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c06n01_grave                |      24|   111|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c06n02_allemande            |      31|   130|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c06n03_sarabande            |      44|   115|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c06n04_air_diable           |      44|   105|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c06n05_siciliene            |      21|   129|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c07n01_grave                |      14|    85|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c07n02_allemande            |      28|   139|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c07n03_sarabande            |      33|    74|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c07n04_fuguete              |      50|   142|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c07n05_gavote               |      28|    57|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c07n06_siciliene            |      18|   105|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n01_ouverture            |      89|   155|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n02_ritournele           |      61|   126|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n03_air                  |      31|    68|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n04_air_tendre           |      24|    54|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n05_air_leger            |      38|    75|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n06_Loure                |      32|   113|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n07_air                  |      28|    74|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n08_sarabande            |      24|    64|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n09_air_leger            |      29|    49|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n10_air_lentement        |      46|   102|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c08n11_air_baccantes        |      18|    59|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c09n01_charme               |      20|   129|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker           |Johannes Menke (2.1.0)|
|c09n02_lenjouement          |      34|   184|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c09n03_graces               |      22|    93|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c09n04_Lejene               |      52|   113|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c09n05_vivacite             |      35|   173|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c09n06_Sarabande            |      24|    50|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c09n07_douceur              |      42|   102|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c09n08_caetera              |      23|    75|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c10n01_gravement            |      14|    74|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c10n02_air                  |      32|   124|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c10n03_plainte              |      36|    92|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c10n04_tromba               |      42|    74|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n01_majestueusement      |      38|    88|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n02_allemande            |      22|   124|2.3.0   |Tobias Drewelius (2.1.0), Hanné (2.3.0)          |Johannes Menke (2.1.0)|
|c11n03_seconde_allemande    |      20|   117|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n04_courante             |      18|    83|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n05_seconde_courante     |      21|    84|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n06_sarabande            |      36|    70|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n07_gigue                |      43|   158|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c11n08_Rondeau              |      56|   131|2.3.0   |Tobias Drewelius (2.1.0), Hanné Becker (2.3.0)   |Johannes Menke (2.1.0)|
|c12n01_pointe               |      41|     0|        |                                                 |                      |
|c12n02_badinage             |      59|     0|        |                                                 |                      |
|c12n03_air                  |      58|     0|        |                                                 |                      |
|c13n01_unisson              |      18|     0|        |                                                 |                      |
|c13n02_air                  |      24|     0|        |                                                 |                      |
|c13n03_sarabande            |      29|     0|        |                                                 |                      |
|c13n04_chaconne             |      93|     0|        |                                                 |                      |
|c14n01_gravement            |      15|    87|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c14n02_allemande            |      23|    99|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c14n03_sarabande            |      28|    55|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|c14n04_fuguete              |      56|   225|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|parnasse_01                 |      18|    82|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|parnasse_02                 |      62|   251|2.3.0   |Johannes Menke(2.1.0), Hanné Becker (2.3.0)      |                      |
|parnasse_03                 |      58|   116|2.3.0   |Johannes Menke (2.1.0) , Hanné Becker (2.3.0)    |                      |
|parnasse_04                 |      57|   105|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|parnasse_05                 |      26|   106|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|parnasse_06                 |      32|    62|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |
|parnasse_07                 |      53|   235|2.3.0   |Johannes Menke (2.1.0), Hanné Becker (2.3.0)     |                      |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
