---
type: word
word: bag
lemma: bag
language: Abyssal
pos:
  - noun
root: ""
ipa: bag
gloss: ""
definition:
  - (n.) something that makes things visible or affords illumination.
  - (n.) an illuminating agent or source, as the sun, a lamp, or a beacon.
  - (n.) warm, cheerful brightness.
  - (n.) radiant brightness or light.
tags:
  - lexicon
---

# bag

* **Pronunciation (IPA):** `=this.ipa`
* **Part of Speech:** `=this.pos`
* **Root:** `=this.root`

### Definitions
```dataviewjs
const page = dv.current();
if (page.definition) {
    const listHtml = "<ol>" + page.definition.map(item => `<li>${item}</li>`).join("") + "</ol>";
    dv.paragraph(listHtml);
}
```

---

## Etymology & Evolution
* **Proto-Form:** 
* **Historical Shift Notes:** 

## Usage & Examples
> **[Sample sentence]**
> *"[Translation]"*

## Related Words
```dataview
TABLE definition AS "Definition", pos AS "POS"
FROM #lexicon
WHERE root = this.root AND file.name != this.file.name AND root != ""