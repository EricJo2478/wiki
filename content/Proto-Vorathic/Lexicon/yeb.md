---
type: word
word: yeb
lemma: yeb
language: Proto-Vorathic
pos:
  - Noun
  - Postposition
root: ""
ipa: jeb
gloss: ""
definition:
  - (n.) a fundamental entity of nature that is transferred between parts of a system in the production of physical change within the system and usually regarded as the capacity for doing work
  - (n.) the most significant element, quality, or aspect of a thing or person
  - (n.) the quality or state of having existence
  - (n.) conscious existence 
  - (n.) the qualities that constitute an existent thing
  - (post.) The preceding noun is the subject of the sentence
tags:
  - lexicon
---

# yeb

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
```