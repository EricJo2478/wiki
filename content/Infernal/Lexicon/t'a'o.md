---
type: word
word: t'a'o
lemma: t'a'o
language: Infernal
pos:
  - noun
root: ""
ipa: t'aʔo
gloss: ""
definition:
  - (n.) an animal, especially a nondemon
  - (n.) an animate being.
tags:
  - lexicon
---

# t'a'o

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
* **Historical Shift Notes:** word comes from combing small and power to mean a creature. Over time it lost the *small* part of it's meaning and shifted to simply mean a being, typically a nondemon but not exclusively.

## Usage & Examples
> **[Sample sentence]**
> *"[Translation]"*

## Related Words
```dataview
TABLE definition AS "Definition", pos AS "POS"
FROM #lexicon
WHERE root = this.root AND file.name != this.file.name AND root != ""