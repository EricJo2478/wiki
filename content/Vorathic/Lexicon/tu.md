---
type: word
word: tu
lemma: tu
language: Vorathic
pos:
  - verb
  - postposition
root: ""
ipa: tu
gloss: ""
definition:
  - (v.) to have or keep in the hand; keep fast.
  - (v.) to bear, sustain, or support, as with the hands or arms, or by any other means.
  - (v.) to have the ownership or use of; keep as one's own.
  - (v.) to bind or make accountable to an obligation.
  - (post.) when following a noun this word indicates that the noun is an indirect object in the sentence
tags:
  - lexicon
---

# tu

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