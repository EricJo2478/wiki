---
type: word
word: pat
lemma: pat
language: Abyssal
pos:
  - noun
root: ""
ipa: pat
gloss: ""
definition:
  - (n.) the act, process, or result of moving.
  - (n.) a series of actions or activities intended or tending toward a particular end.
tags:
  - lexicon
---

# pat

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