---
type: word
word: wo
lemma: wo
language: Proto-Vorathic
pos:
  - Noun
root: ""
ipa: wo
gloss: ""
definition:
  - (n.) something that is of limited size; of comparatively restricted dimensions; not big; little.
  - (n.) something that is not large as compared with others of the same kind.
  - (n.) something that is of low numerical value; denoted by a low number.
tags:
  - lexicon
---

# wo

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