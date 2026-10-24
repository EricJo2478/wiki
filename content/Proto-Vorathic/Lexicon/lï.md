---
type: word
word: "lï"
lemma: "lï"
language: "Proto-Vorathic"
pos:
  - verb
  - postposition
root: ""
ipa: "lɨ"
gloss: ""
definition:
  - (v.) to perceive through one or more of the senses
  - (v.) to apprehend or detect without or in advance of the evidence of the senses
  - (v.) to understand
  - (post.) when following a noun this word indicates that the noun is a direct object in the sentence
tags:
  - lexicon
---

# lï

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