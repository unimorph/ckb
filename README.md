# Central Kurdish (Sorani - `ckb`)
### *Kurdîy Nawendî* - کوردیی ناوەندی - کوردیی سۆرانی

---

This repository contains inflected forms of words in Central Kurdish. The provided dataset can be used for evaluation and training of morphological analyzers and are included in the [SIGMORPHON shared tasks](https://sigmorphon.github.io/) as well.

The older data on the repository (**before July 2023**) was initially created with paradigms taken from the [Alexina Project](https://almanach.inria.fr/software_and_resources/Alexina-en.html). However, as discussed in the SIGMORPHON 2023 paper entitled [Revisiting and Amending Central Kurdish Data on UniMorph 4.0](https://sinaahmadi.github.io/docs/articles/ahmadi2023sigmorphon.pdf), the previous dataset contained morphological errors which made it impractical for real-world applications.

## Data 

This repository provides the following datasets in the two common scripts of Kurdish, the Perso-Arabic and Latin scripts:


| Dataset                 | # Inflections | Kurdish Perso-Arabic script | Kurdish Latin script  |
|-------------------------|-----------------------------|---------------------------------|---------|
| Gold-standard           |  997   | [ckb-arab](arab/ckb-arab.tsv) ([train](arab/ckb-arab.train) / [dev](arab/ckb-arab.dev) / [test](arab/ckb-arab.test))     | [ckb-latn](latn/ckb-latn.tsv) ([train](latn/ckb-latn.train) / [dev](latn/ckb-latn.dev) / [test](latn/ckb-latn.test)) |
| Silver-standard   	   |   110,880  | [ckb-arab-large](arab/ckb-arab-large.tsv) ([train](arab/ckb-arab-large.train) / [dev](arab/ckb-arab-large.dev) / [test](arab/ckb-arab-large.test)) |    [ckb-latn-large](latn/ckb-latn-large.tsv) ([train](latn/ckb-latn-large.train) / [dev](latn/ckb-latn-large.dev) / [test](latn/ckb-latn-large.test))    |

**For evaluation purposes, we recommend using the gold-standard dataset in either scripts.** You can use the larger dataset (silver-standard) for training purposes as well.

The train-dev-test split has the proportions of 70-10-20 based on the `tsv` files. The inflections in the two scripts are provided in the same order in the files. For instance, line 92 in the gold-standard dataset in the Perso-Arabic script corresponds to the same word form in the Latin script:

Line 92 in [ckb-arab.tsv](arab/ckb-arab.tsv):

`چوون	چووە	V;PST;IND;ARGNO3S;LGSPEC2`

Line 92 in [ckb-latn.tsv](latn/ckb-latn.tsv):

`çûn	çuwe	V;PST;IND;ARGNO3S;LGSPEC2`

Given the issues with the previous dataset, we don't recommend using it. However, if you'd need the old UniMorph 2.0 data, you can find it at [UniMorph2.tsv](UniMorph2/UniMorph2.tsv).



## Tags

The gold-standard dataset is created based on a corpus. To provide the context of each word form in the corpus, we additionally provide another dataset called [ckb-context-complete.tsv](ckb-context-complete.tsv). To further clarify language-specific tags (`lgspec`), we use our tags in that dataset. 

The UniMorph tags used for Central Kurdish data are as follows:

| Type | Function                                                        | Ours                     | UniMorph  |
|--------|-------------------------------------------------------------------|----------------------------|----------------------|
| Affix  | Izafe                                                             | `[izafe]`           | `lgspec1`  |
| Affix  | postverb adpositions                                              | `[e]` `[ee]` | `lgspec2`  |
| Affix  | postverb adverbial /ewe/                                          | `[ewe1]`            | `lgspec3`  |
| Affix  | disc. adpositions                                                 | `[da],[ra], [ewe2]` | `lgspec4`  |
| Clitic | adverbial clitic                                                  | `[ish]`             | `lgspec5`  |
| Clitic | demonstrative                                                     | `[dem]`             | `lgspec6`  |
| Clitic | copula                                                            | `[cop]`             | `lgspec7`  |
| Clitic | pronominal markers (argument/possessive) on transitive past verbs | `[pm]`              | `lgspec8`  |
| Clitic | argument markers on noun/adjectives                               | `[am]`              | `lgspec9`  |

## Annotators
- Sina Ahmadi (updated dataset)
- Aso Mahmudi (updated dataset)
- Ali Salehi (UniMorph 2.0)
- Géraldine Walther (UniMorph 2.0)

## Paradigm Samples

In Kurdish Perso-Arabic script:

```
لە	لە	ADP
وڵات	وڵاتانی	N;PL;LGSPEC1
ماکۆ	ماکۆ	PROPN
یان	یان	CONJ
چوارچێوە	چوارچێوەی	N;LGSPEC1
دهۆک	دهۆک	PROPN
ناوچە	ناوچەی	N;LGSPEC1
کاسیاس	کاسیاسی	PROPN;LGSPEC1
کۆمەڵکوژی	کۆمەڵکوژی	ADJ
لەئێرە	لێرەدا	ADP;N;LGSPEC4(DA)
لە+ئەو	لەو	ADP + ADJ
پەرلەمان	پەرلەمانی	N;LGSPEC9(3S)
ئەو	ئەوەی	PRO;LGSPEC6;LGSPEC1
کردن	دەکەنەوە	V;PRS;IND;ARGNO3P;LGSPEC3
ڕانیە	ڕانیە	PROPN
سەرۆک	سەرۆک	N
زانکۆ	زانکۆی	N;LGSPEC1
هەبوون	هەبێت	V;PRS;SBJV;ARGAC3S
دان	دابوو	V;PST;PRF;IND;LGSPEC8(3S)
```

The same forms in the Kurdish Latin script:

```
le	le	ADP
wiłat	wiłatanî	N;PL;LGSPEC1
mako	mako	PROPN
yan	yan	CONJ
çwarçêwe	çwarçêwey	N;LGSPEC1
dihok	dihok	PROPN
nawçe	nawçey	N;LGSPEC1
kasyas	kasyasî	PROPN;LGSPEC1
komełkujî	komełkujî	ADJ
le’êre	lêreda	ADP;N;LGSPEC4(DA)
le+ew	lew	ADP + ADJ
perleman	perlemanî	N;LGSPEC9(3S)
ew	ewey	PRO;LGSPEC6;LGSPEC1
kirdin	dekenewe	V;PRS;IND;ARGNO3P;LGSPEC3
řanye	řanye	PROPN
serok	serok	N
zanko	zankoy	N;LGSPEC1
hebûn	hebêt	V;PRS;SBJV;ARGAC3S
dan	dabû	V;PST;PRF;IND;LGSPEC8(3S)
```


## Shared Tasks

2021: [SIGMORPHON 2021 Shared Task on Morphological Reinflection: Generalization Across Languages](https://aclanthology.org/2021.sigmorphon-1.25/)

## References

```
@inproceedings{ahmadi2023sigmorphon,
    title = "Revisiting and Amending {C}entral {K}urdish Data on {U}ni{M}orph 4.0",
    author = "Ahmadi, Sina  and Mahmudi, Aso",
    booktitle = "Proceedings of the 20th SIGMORPHON workshop on Computational Research in Phonetics, Phonology, and Morphology",
    month = jul,
    year = "2023",
    address = "Toronto, Canada",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.sigmorphon-1.5",
    pages = "38--48"
}

```

```
@inproceedings{pimentel-ryskina-etal-2021-sigmorphon,
    title = "SIGMORPHON 2021 Shared Task on Morphological Reinflection: Generalization Across Languages",
    author = "Pimentel, Tiago  and
      Ryskina, Maria  and
      Mielke, Sabrina J.  and
      Wu, Shijie  and
      Chodroff, Eleanor  and
      Leonard, Brian  and
      Nicolai, Garrett  and
      Ghanggo Ate, Yustinus  and
      Khalifa, Salam  and
      Habash, Nizar  and
      El-Khaissi, Charbel  and
      Goldman, Omer  and
      Gasser, Michael  and
      Lane, William  and
      Coler, Matt  and
      Oncevay, Arturo  and
      Montoya Samame, Jaime Rafael  and
      Silva Villegas, Gema Celeste  and
      Ek, Adam  and
      Bernardy, Jean-Philippe  and
      Shcherbakov, Andrey  and
      Bayyr-ool, Aziyana  and
      Sheifer, Karina  and
      Ganieva, Sofya  and
      Plugaryov, Matvey  and
      Klyachko, Elena  and
      Salehi, Ali  and
      Krizhanovsky, Andrew  and
      Krizhanovsky, Natalia  and
      Vania, Clara  and
      Ivanova, Sardana  and
      Salchak, Aelita  and
      Straughn, Christopher  and
      Liu, Zoey  and
      Washington, Jonathan North  and
      Ataman, Duygu  and
      Kiera{\'s}, Witold  and
      Woli{\'n}ski, Marcin  and
      Suhardijanto, Totok  and
      Stoehr, Niklas  and
      Nuriah, Zahroh  and
      Ratan, Shyam  and
      Tyers, Francis M.  and
      Ponti, Edoardo M.  and
      Aiton, Grant  and
      Hatcher, Richard J.  and
      Prud'hommeaux, Emily  and
      Kumar, Ritesh  and
      Hulden, Mans  and
      Barta, Botond  and
      Lakatos, Dorina  and
      Szolnok, G{\'a}bor  and
      {\'A}cs, Judit  and
      Raj, Mohit  and
      Yarowsky, David  and
      Cotterell, Ryan  and
      Ambridge, Ben  and
      Vylomova, Ekaterina",
    booktitle = "Proceedings of the 18th SIGMORPHON Workshop on Computational Research in Phonetics, Phonology, and Morphology",
    month = aug,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.sigmorphon-1.25",
    doi = "10.18653/v1/2021.sigmorphon-1.25",
    pages = "229--259"
}

```

## License: 
 [Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/)

