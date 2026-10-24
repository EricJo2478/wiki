---
type: word
word: t'a'ovebeg
lemma: t'a'ovebeg
language: Infernal
pos:
  - noun
root: ""
ipa: t'aʔovebeg
gloss: ""
definition:
  - (n.) a cherished being who brings one balance
  - (n.) a soulmate
tags:
  - lexicon
---

# t'a'ovebeg

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
* **Historical Shift Notes:** This word was formed by referring to a cherished thing and balance. Overtime this word came to more specifically mean a soulmate not simply a loved one.

## Usage & Examples
> **[Sample sentence]**
> *"[Translation]"*

## Related Words
```dataview
TABLE definition AS "Definition", pos AS "POS"
FROM #lexicon
WHERE root = this.root AND file.name != this.file.name AND root != ""