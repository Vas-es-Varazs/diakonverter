# Canva → PowerPoint

[English version below](#english)

Canva prezentációból PowerPoint (.pptx) fájl, pontosan úgy, ahogy Canvában kinéz.

A Canva saját PowerPoint exportja gyakran elrontja a betűtípusokat és az elrendezést. Ez az eszköz minden diát képként tesz bele a PowerPoint fájlba, így semmi sem csúszik el.

## Használat

1. Canvában: **Share → Download → File type: PDF Standard → Download**.
2. Nyisd meg ezt az oldalt: **https://vas-es-varazs.github.io/diakonverter/**
3. Húzd a letöltött PDF-et az oldalon lévő mezőbe.
4. Pár másodperc múlva letöltődik a kész fájl. A neve ugyanaz lesz, mint az eredetié, a végén „converted” szóval.

A fájlod nem kerül feltöltésre sehova: az átalakítás teljesen a böngésződben történik.

## Jó tudni

- **PDF-et használj.** PNG képek ZIP-jét is elfogadja, de abból homályosabb lesz a szöveg.
- **A diák szövege nem szerkeszthető** PowerPointban, mert minden dia egy kép. Ha módosítani kell valamit, javítsd Canvában, és alakítsd át újra.

---

<a id="english"></a>

# Canva → PowerPoint (English)

Turn a Canva presentation into a PowerPoint (.pptx) file that looks exactly like it does in Canva.

Canva's own PowerPoint export often breaks fonts and layout. This tool puts each slide into the PowerPoint file as an image, so nothing can shift.

## How to use it

1. In Canva: **Share → Download → File type: PDF Standard → Download**.
2. Open this page: **https://vas-es-varazs.github.io/diakonverter/**
3. Drop the downloaded PDF onto the box on the page.
4. After a few seconds the finished file downloads. It has the same name as the original, with "converted" added to the end.

Your file is never uploaded anywhere: the conversion happens entirely in your browser.

## Good to know

- **Use a PDF.** A ZIP of PNG images also works, but the text comes out blurrier.
- **Slide text can't be edited** in PowerPoint, because each slide is an image. To change something, fix it in Canva and convert again.

## For developers

The page is static HTML ([index.html](index.html)) served by GitHub Pages. It renders PDF pages with [pdf.js](https://mozilla.github.io/pdf.js/) at 3840 px wide (JPEG, quality 95) and builds the .pptx with [PptxGenJS](https://gitbrent.github.io/PptxGenJS/). Both libraries are vendored in [vendor/](vendor/), so conversion works without any other site; only the fonts load from Google Fonts. The page has a `noindex` tag to keep it out of search results.

ZIP images are used as-is, in the order they are stored in the ZIP. Canva names titled pages by their title instead of their number, so sorting by filename would scramble the order.

[script/diakonverter.py](script/diakonverter.py) does the same from the command line:

```bash
pip3 install python-pptx pymupdf
python3 script/diakonverter.py "My deck.pdf"
```

To preview the page locally (it doesn't work when opened as a file):

```bash
python3 -m http.server
```

Then open http://localhost:8000.
