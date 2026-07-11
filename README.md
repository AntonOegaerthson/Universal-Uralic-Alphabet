# Universal-Uralic-Alphabet
A unified, hyper-phonetic Latin-script orthography and keyboard layout mapping system designed to replace forced Cyrillic uniformity across the Uralic language family.
This is my first project on this website, so I apologize if anything is incorrect. I created this after Google AI suggested that I do this! The code was provided by Google AI as well, so I also apologize for any mistakes there too!
# Universal Uralic Alphabet (UUA) Keyboard Specification

A unified, hyper-phonetic Latin-script orthography and keyboard layout mapping system designed to replace forced Cyrillic uniformity across the Uralic language family. 

The Universal Uralic Alphabet (UUA) provides a 1:1 relationship between spelling and pronunciation, taming complex sound environments across Baltic-Finnic, Volgaic, Permic, Ugric, and Samoyedic branches. By standardizing typography, it reveals deep ancestral connections and brings digital sovereignty to minority languages.

---

## 🗺️ Architectural Philosophy

1. **Phonetic Stability:** One character represents one unshifting sound. Vowels hold pure values; consonants isolate secondary qualities.
2. **Diacritic Real-Estate Segregation:** Top-side diacritics represent palatalization; bottom-side diacritics represent voicelessness. They never collide.
3. **Nordic-Ugric Aesthetic:** The system rejects Slavic-style single affricates (`c`, `č`, `ć`) in favor of horizontal, vowel-and-consonant-heavy digraph layout rules (`ts`, `tš`, `t́ś`) matching Finnish, Estonian, and Hungarian.
4. **Zero Custom Fonts Required:** The entire engine runs on standard, native Unicode characters and combining diacritical marks.

---

## 🔣 Unicode Core Character Mapping

### 1. Pure Vowels & Quantity
Length is represented universally by **doubling the character** (`aa`, `ää`, `əə`). In Ob-Ugric (Khanty/Mansi) systems, a vowel with a breve diacritic represents a reduced vowel, and a diacriticless letter represents a full vowel.

| Vowel | IPA | Unicode Name | Hex Code | Regional / Language Context |
| :---: | :---: | :--- | :---: | :--- |
| **ä** | [æ] | LATIN SMALL LETTER A WITH DIAERESIS | `U+00E4` | Near-open front unrounded (Finnish, Moksha, Nenets, ) |
| **ö** | [ø] | LATIN SMALL LETTER O WITH DIAERESIS | `U+00F6` | Mid-front rounded (Finnish, Estonian, Hungarian, Mari `ö`, Permic `ö` (Value varies for Permic `ö`, but can be [ɘ] or [ɵ], and the rounded/weakly rounded and close-mid nature is best represented by ö)) |
| **ü** | [y] | LATIN SMALL LETTER U WITH DIAERESIS | `U+00FC` | Close front rounded (Estonian, Hungarian, Mari El `ü`, can be represented by the letter `y` if preferred, since Finnish uses `y`) |
| **ə** | [ə] | LATIN SMALL LETTER SCHWA | `U+019F` | Central schwa (Mari El `y`, Khanty,  Nenets) |
| **õ** | [ɯ] or [ɤ] | LATIN SMALL LETTER O WITH TILDE | `U+00F5` | Close back unrounded (Permic `y`, Estonian, Livonian) |
| **e** | [e] | LATIN SMALL LETTER E | `U+0065` | Close-mid front unrounded (All Uralic languages) |
| **i** | [i] | LATIN SMALL LETTER I | `U+0069` | Close front unrounded (All Uralic languages) |
| **ɛ** | [ɛ] | LATIN SMALL LETTER OPEN E | `U+025B` | Open-mid front unrounded (Khanty `є`, Enets `ԑ`) |
| **ꞷ** | [ɔ] | LATIN SMALL LETTER OMEGA | `U+A7B7` | Open-mid back rounded (Enets `o`) |
| **a** | [a] or [ɑ] | LATIN SMALL LETTER A | `U+0061` | Open central unrounded or Open back unrounded (All Uralic Languages) |
| **o** | [o] | LATIN SMALL LETTER O | `U+006F` | Close-mid back unrounded (All Uralic Languages, Enets `ô`) |
| **u** | [u] | LATIN SMALL LETTER U | `U+0075` | Close back unrounded (All Uralic Languages) |
| **ө** | [ɤ̹̈] | LATIN SMALL LETTER BARRED O | `U+0275` | CLose-mid back slightly centralized weakly rounded (Komi-Yazva) Used as the "central counterpart" to a present "ö", appearing between ö and o.) |

### 2. Consonants & Fricative Stability
*   **`h`** (`U+0068`): Strictly the breathy *voiceless glottal fricative* [h] (Hungarian *haaz*).
*   **`x`** (`U+0078`): Strictly the scraping *voiceless velar fricative* [x] (Khanty *xoot*, Moksha *koxva*).
*   **`ł`** (`U+0142`): Strictly the *voiceless alveolar lateral fricative* [ɬ] (Forest Nenets `*r` mutation).
### 3. Combining Diacritics (The Stacking Engine)
Diacritics are stacked sequentially *after* the base consonant letter.

*   **Palatalization (Top-Side):** `COMBINING ACUTE ACCENT` ──> **`U+0301`**
*   **Voicelessness (Bottom-Side):** `COMBINING RING BELOW` ──> **`U+0325`**
*   **Nasalized Glottal Element (Top-Side):** `COMBINING TILDE` ──> **`U+0303`**

*Keystroke Stacking Example (Moksha Voiceless-Palatalized Lateral):*
`L` + `U+0325` (Ring) + `U+0301` (Acute) = **`ĺ̥`**

### 4. The Samoyedic Glottal Stops
*   **`ɂ`** (`U+0242`): Plain Glottal Stop [ʔ] (Replaces Forest Enets, Tundra Enets, Forest Nenets, and Tundra Nenets Cyrillic `ˮ`).
*   **`ɂ̃`** (`U+0242` + `U+0303`): Nasalized Glottal Stop [ʔⁿ] (Replaces Tundra Nenets and Forest Nenets Cyrillic `ʼ`).

---

## 📱 Mobile Keyboard Interaction Layout (iOS / Android)

Built to maximize touch real estate using a highly intuitive **Long-Press (Hold)** pop-up strategy based on standard Latin base character keys.


## 💻 Desktop Hardware Dead-Key Layout (Windows / macOS / Linux)

Turns the underutilized Semicolon (**`;`**) and Backtick (**`` ` ``**) into "Dead Keys" to dynamically modify the following keystroke.

| Initial Modifier | Next Key Pressed | Unified Output | Phonetic Function |
| :---: | :---: | :---: | :--- |
| **`;`** *(Palatalization)* | `s` | **`ś`** | Palatalized Consonant |
| **`;`** *(Palatalization)* | `t` | **`t́`** | Palatalized Consonant |
| **`` ` ``** *(Voicelessness)* | `l` | **`l̥`** | Voiceless Sonorant |
| **`` ` ``** *(Voicelessness)* | `r` | **`r̥`** | Voiceless Sonorant |
| **`;`** then **`` ` ``** | `l` | **`ĺ̥`** | Voiceless-Palatalized Sonorant |
| **`;`** *(Palatalization)* | `'` | **`ɂ̃`** | Nasalized Glottal Stop |
---
### Affricate Matrix Macros (Makes it easier to understand affricates, undoes Slavic c being used for ts, removes the Slavic element, making it uniquely Uralic)
*   Type `ts` ──> **`ts`** | Type `tss` ──> **`tss`** (Geminated)
*   Type `tš` ──> **`tš`** | Type `tšš` ──> **`tšš`** (Geminated)
*   Type `t;s` ──> **`t́ś`** | Type `t;ss` ──> **`t́śś`** (Geminated)

---
# 🧪 Universal Diagnostic Cross-Test

Proof of structural clarity across families using the UUA standard.

### Concept: Eye (Proto-Uralic *śilmä*)

| Language | Traditional / Cyrillic Script | Universal Uralic Alphabet (UUA) | IPA | Notes |
| :--- | :--- | :--- | :--- |
| **Proto-Uralic** | *śilmä* | `śilmä` | `ˈɕilmæ` or `sʲilmæ` |
| **Proto-Finnic** | *silmä* | `silmä` | `ˈsilmæ` |
| **Finnish** | *silmä* | `silmä` | `ˈsilmæ` |
| **Estonian** | *silm* | `silm` | `ˈsilm` |
| **Ingrian (Ala-Laukaa)** | *silmä* | `silmä` | `ˈsilmæ` |
| **Ingrian (Soikkola)** | *silmä* | `siĺmä` | `ˈsilʲmæ` |
| **North Karelian** | *šilmä* | `šilmä` | `ˈʃilmæ` |
| **South Karelian** | *šilmä* | `šilmä` | `ˈʃilmæ` |
| **Livonian** | *sīlma* | `siilma` | `ˈsiːlmɑ` |
| **Livvi** | *silmy* or *silmü* | `silmy` or `silmü` | `ˈsilmy` |
| **Ludian (Mundärv)** | *šilm* / *silʹm* | `šilm` / `siĺm` | `ˈʃilm` |
| **Veps** | *silʹm* | `siĺm` | `ˈsilʲm` |
| **Võro** | *silm* | `silm` | `ˈsilm` |
| **Votic** | *silme* | `śilmä` or `silmä` | `ˈsʲilmæ` or `ˈsilmæ` |
| — | — | — | — | — |
| **Proto-Sami** | *čëlmē* | `tšɘlmee` | `ˈt͡ʃɘlmeː` |
| **Northern Sami** | *čalbmi* | `tšalbmi` | `ˈt͡ʃalbmi` |
| **Northern Sami (Kautokeino)** | *čalbmi* | `tšallpmii` | `ˈt͡ʃalːpmiː` |
| **Southern Sami** | *tjelmie* | `tšelmie` | — |
| **Ume Sami** | *tjalbmie* | `tšalbmie` | — |
| **Pite Sami** | *tjalbme* | `tšalbme` | — |
| **Lule Sami** | *tjalmme* | `tšalmme` | — |
| **Inari Sami** | *čalme* | `tšalme` | — |
| **Skolt Sami** | *čâʹlmm* | `tšȧĺmm` | — |
| **Akkala Sami** | чилльм or челльм | `tšiĺĺm` or `tšeĺĺm` | — |
| **Kildin Sami** | чалльм or ча̄лльм | `tšaĺĺm` or `tšaaĺĺm` | — |
| **Ter Sami** | чалльмэ | `tšaĺĺme` | — |
| — | — | — | — | — |
| **Proto-Mari** | *šĭńća* | `šeńt́śa` | `ˈʃenʲtʲsʲa` |  ĭ is close-mid front unrounded vowel in Proto-Mari for Wiktionary |
| **Eastern-Mari** | шинча | `šint́śa` | `ʃinˈt͡ɕɑ` |
| **North-Western Mari** | шӹнцӓ | `šə̈ntsä` | `ʃə̈ntsä` |
| **Western Mari** | сӹнзӓ | `sə̈nzä` | — |
| — | — | — | — | — |
| **Proto-Permic** | *śin* | `śin` | — |
| **Komi-Zyrian** | син | `śin` | `ˈɕin` |
| **Komi-Permyak** | син | `śin` | `ˈɕin` |
| **Komi-Yazva** | син | `śin` | `ˈɕin` |
| **Udmurt** | син | `śin` | `ˈɕin` |
| — | — | — | — | — |
| **Proto-Mordvinic** | *śeľmə* | `śeľmə` | — |
| **Moksha** | сельме  | `Śeĺmä` | — |
| **Erzya** | сельме  or сӓльме | `Śeĺme` or `Śäĺme` | — |
| — | — | — | — | — |
| **Hungarian** | *szem* | `sem` | — |
| **Proto-Khanty** | säm | `säm` | `ˈsäm` | 
| **Northern-Khanty (Kazym)** | сєм | `sɛm` | `ˈsɛm` |
| **Eastern-Khanty (Surgut)** | сӓм | `sɛm` | `ˈsɛm` |
| **Eastern-Khanty (Vakh)** | сeм | `sem` | `ˈsem` |
| **Eastern-Khanty (Vasyugan)** | сeм | `śem` | `ˈsʲem` |
| **Northern Mansi** | сeм | `sam` | `ˈsam` |
| **Eastern Mansi (Upper Konda)** | сям | `śam` | — |
| **Eastern Mansi (Yukonda)** | сӓм | `säm` | — |
| **Western Mansi** | *šäм* | `šäm` | `ˈʃæm` |
| **Southern Mansi (Tavda)** | *šäм* | `šäm` | `ˈʃæm` |
| — | — | — | — | — |
| **Proto-Samoyedic** | *səjmä* | `səjmä` | — |
| **Nganasan** | сеймы | `śejmɨ` | — |
| **Forest Enets** | сэй | `sej` | — |
| **Tundra Enets** | сэи | `sei` | — |
| **Forest Nenets** | хӭм | `xäm` | — |
| **Tundra Nenets** | сэв | `säwə` | — |
| **Proto-Selkup** | sajə | `sajə` | — |
| **Northern Selkup** | сайы | `sajɨ` | — |
| **Southern Selkup (Narym)** | хай | `xaj` | — |
| **Southern Selkup (Upper Ob)** | сэй | `sej` | — |
| **Kamassian** | сима | `sima` | — |
| **Mator** | сима | `sima` | — |
### Concept: Heart & Grammar (Proto-Uralic *śüdäme*)
| Language | Traditional / Cyrillic Script | Universal Uralic Alphabet (UUA) | IPA | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Proto-Uralic** | *śüdäme* | `śüdäme` | `ˈsʲydæme` or `ˈɕydæme` | Ancestral reconstruction |
| Finnic | — | — | — | — |
| **Proto-Finnic** | *südän* | `südän` |  `ˈsydæn` | Ancestral Reconstruction |
| **Finnish** | *sydän*  | `südän` | `ˈsydæn` | (stem: *sydäme-*) | 
| **Estonian** | *süda*  | `süda` | `ˈsydæ` | (stem: *südame-*)  |
| **Ingrian** | *syän* | `süän` | `ˈsyæn` | |
| **North Karelian** | *šyväin* or *šytän* | `šüväin` or `šütän` |
| **South Karelian** | *šiämi* | `šiämi` | `ˈʃiæmi`| |
| **Livonian** | *sidām* | `sidaam` |  `ˈsidaːm` | |
| **Livvi** | *syväin* | `süväin` | `ˈsyvæin` | |
| **Ludian** | *südäm* | `südäm` | `ˈsydæm` | |
| **Veps** | *südäin* | `südäin` | `ˈsydæin` | |
| **Võro** | *süä* | `süä` | `ˈsyæ` | |
| **Votic** | *süä* | `süä` | `ˈsyæ` | |
| Samic | — | — | — | — |
| **Proto-Samic** | *čëδēm* | `tšõðeem` | `ˈtʃɤðeem` | Proto-Saamic ë has value of [ɤ] |
| **Skolt Sami** | — | — | — | — |
| **Proto-Mordvinic** | *śeďəj* | `śed́əj` | `ˈsʲedʲəj` | `` | 
| **Moksha** | седи | `śed́i` | `ˈsʲedʲi` |
| **Erzya** | седей  | `śed́ej` | `ˈsʲedʲej` |
| **Erzya** | седеҥ  | `śed́eŋ` | `ˈsʲedʲeŋ` |
| **Erzya** | сӓдей   | `säd́ej` | `ˈsädʲej` |
| Permic | — | — | — | — |
| **Proto-Permic** | śɔ̈läm  | `śꞷ̈läm` or `śɔ̈läm` | `ˈɕœlæm`  | |
| **Komi-Zyryan** | сьӧлӧм | `śölöm` | `ˈɕɵlɵm` or `ˈɕɘlɘm` |
| **Komi-Permyak** | сьӧлӧм | `śölöm` | `ˈɕɵlɵm` or `ˈɕɘlɘm` |
| **Komi-Yazva** | сьӧлөм | `śölɵm` | `ˈɕɵlɤ̹̈m` |
| **Udmurt** | сюлэм | `śulem` | `ɕulem` |
| Mari | — | — | — | — |
| **Proto-Mari** | *šü̆m* | `šöm` | `ˈʃøm` | ü̆ is close-mid front rounded vowel in Proto-Mari for Wiktionary |
| **Eastern Mari** | шӱм | `šüm` | `ˈʃym` |
| **Western Mari** | шӱм | `šüm` | `ˈʃym` |
| Ugric | — | — | — | — |
| **Hungarian** | *szív* | `siiv` | `ˈsiːv` | Long vowel via UUA doubling |
| **Proto-Khanty** | *sĭm* | — | — | — |
| **Northern Khanty** | сӑм | `săm` | — | Kazym |
| **Northern Khanty** | сӑм | `săm` | — | Middle Ob |
| **Northern Khanty** | сам | `sam` | — | Shuryshkar |
| **Eastern Khanty** | сәм | | | Surgut |
| **Eastern Khanty** | сӛм |  | | Vakh |
| **Eastern Khanty** |  | | | Yugan |
| — | — | — | — | — |

---

## 📱 Mobile Keyboard Interaction Layout (iOS / Android)

Built to maximize touch real estate using a highly intuitive **Long-Press (Hold)** pop-up strategy based on standard Latin base character keys.

```text
[A] ──>  [ a ] [ aa ] [ ä ] [ ää ]
[E] ──>  [ e ] [ ee ] [ ə ] [ əə ] [ ə̈ ] [ ə̈ə̈ ]
[O] ──>  [ ö ] [ öö ] [ õ ] [ õõ ] [ ]
[U] ──>  [ u ] [ uu ] [ ü ] [ üü ]
[L] ──>  [ ĺ ] [ l̥ ]  [ ĺ̥ ] [ ł ] [ ł́ ]
[R] ──>  [ ŕ ] [ r̥ ]  [ ŕ̥ ]
[N] ──>  [ ń ] [ n̥ ]  [ ń̥ ]
['] ──>  [ ɂ ] [ ɂ̃ ]
```

---

## 🛠️ Installation & Building

This repository contains raw layouts and configuration mapping files for integration into open-source input frameworks:

### For Keyman Engine (Mobile & Cross-Platform)
See the source files inside the `/keyman` directory. Compile using the Keyman Developer suite:
```bash
kmcomp uua_layout.kmn -o uua_layout.kmx
```

### For XKB (Linux / X11)
Append the contents of `/linux/uua_xkb` directly to your local symbols file:
```bash
cat linux/uua_xkb >> /usr/share/X11/xkb/symbols/us
```

## ⚖️ License & Open Sovereignty
This layout and its linguistic mapping documentation are released entirely open-source under the **MIT License**. Use it to communicate freely, archive texts, build applications, and bypass arbitrary typographic borders. 
