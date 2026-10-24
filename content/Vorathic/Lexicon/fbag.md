---
type: word
word: "fbag"
lemma: "fbag"
language: "Vorathic"
pos:
  - noun
root: ""
ipa: "fbag"
gloss: ""
definition:
  - (n.) the blanace between the engery/powers of light and dark
tags:
  - lexicon
---

# fbag

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
* **Historical Shift Notes:** this word was formed by combining the words for light and dark.

## Usage & Examples
> **[Sample sentence]**
> *"[Translation]"*

## Related Words
```dataview
TABLE definition AS "Definition", pos AS "POS"
FROM #lexicon
WHERE root = this.root AND file.name != this.file.name AND root != ""