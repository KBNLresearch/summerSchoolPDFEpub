## PDF en EPUB ontrafeld

Achtergrondinformatie en verdiepende materialen bij het KB Summerschool onderdeel "PDF en EPUB ontrafeld".

### [PDF](https://en.wikipedia.org/wiki/PDF)

#### Geschiedenis

[The History of the PDF: Timeline](https://www.adobe.com/acrobat/resources/pdf-timeline.html)

####  Opbouw en structuur

[Inside PDF](https://news.speedata.de/2024/03/19/insidepdf-01/) is een serie artikelen over hoe het PDF formaat in elkaar zit. Erg technisch, dus vooral voor de echte die-hards!

#### Problemen PDF tekstextractie

- [What's so hard about PDF text extraction?](http://archive.today/2020.09.14-092557/https://filingdb.com/b/pdf-text-extraction). Dit artikel geeft een goed overzicht van de vele problemen die kunnen optreden bij de extractie van tekst uit PDF bestanden.

- [Brief Overview of the Portable Document Format and Some Challenges for Text Extraction](https://irsg.bcs.org/informer/wp-content/uploads/OverviewOfTextExtractionFromPDFs.pdf)

- [Why extracting data from PDFs is still a nightmare for data experts](https://arstechnica.com/ai/2025/03/why-extracting-data-from-pdfs-is-still-a-nightmare-for-data-experts/). Dit artikel gaat in op machine learning technieken, en waarom ook die niet perfect zijn.

### [EPUB](https://en.wikipedia.org/wiki/EPUB)

#### Geschiedenis

[EPUB History and Future](https://en.wikipedia.org/wiki/EPUB)

####  Opbouw en structuur

[A look inside an EPUB file](https://opensource.com/article/22/8/epub-file) - een EPUB bestand is eigenlijk gewoon een [ZIP](https://en.wikipedia.org/wiki/ZIP_(file_format)) container, met daarin [XML](https://en.wikipedia.org/wiki/XML) metadata en [XHTML](https://en.wikipedia.org/wiki/XHTML) content.

#### Problemen EPUB tekstextractie

[Valid, but not accessible: crazy fixed EPUB layouts](https://www.bitsgalore.org/2016/04/04/valid-but-not-accessible-epub-crazy-fixed-layouts) gaat in op problemen die kunnen optreden met "fixed layout" EPUB bestanden. Tekstextractie op dergelijke bestanden kan ook onverwachte resultaten opleveren. Niet genoemd hier: EPUBs die uit alleen maar afbeeldingen bestaan (dit zie je vaak bij geïllustreerde kinderboeken).

### Tekstextractie met Apache Tika

[Apache Tika](https://tika.apache.org/) is open-source software voor het herkennen en extraheren van metadata en tekst. Tika ondersteunt een groot aantal bestandsformaten, waaronder PDF en EPUB.

[Tika-python](https://github.com/chrismattmann/tika-python) is een Python wrapper waarmee je Apache Tika binnen Pythonprojecten kunt gebruiken.

#### Tika-python instalatie

```
pip install tika
```

#### Tika-python voorbeeld

Onderstaande code leest een input PDF bestand uit, extraheert de tekst met Tika-python, en schrijft de geëxtraheerde tekst weg naar een output tekstbestand:  

```python
#! /usr/bin/env python3

import tika
from tika import parser

# Define input, output
fileIn = "whatever.pdf"
fileOut = "whatever.txt"

# Parse input file
parsed = parser.from_file(fileIn, service='text')

# Get text
content = parsed["content"]

# Write text to output file 
with open(fileOut, 'w', encoding='utf-8') as fout:
    fout.write(content)
```

### Vergelijking tekstextractietools voor EPUB

- Blogpost [Extracting text from EPUB files in Python](https://www.bitsgalore.org/2023/03/09/extracting-text-from-epub-files-in-python)

- [Github repository met Python demoscripts uit blogpost](https://github.com/KBNLresearch/textExtractDemo)

### Meer PDF tools

- [Working with batches of PDF files](http://programminghistorian.org/en/lessons/working-with-batches-of-pdf-files) - o.a. extractie van tekst, afbeeldingen, en optische tekenherkenning met open-source command-line tools.
- [PDF processing and analysis with open-source tools](https://www.bitsgalore.org/2021/09/06/pdf-processing-and-analysis-with-open-source-tools) - nog meer PDF manipulatie met open-source command-line tools.

