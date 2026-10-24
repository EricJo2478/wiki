---
type: word
word: "mïp"
lemma: "mïp"
language: "Proto-Vorathic"
pos:
  - verb
  - postposition
root: ""
ipa: "mɨp"
gloss: ""
definition:
  - (v.) to take in and utilize.
  - (v.) to occupy or fill.
  - (v.) to swallow up the identity or individuality of; incorporate.
  - (v.) to suck up or drink in (a liquid); soak up.
  - (post.) when found between 2 nouns turns the second noun into an adjective.
tags:
  - lexicon
---

# mïp

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