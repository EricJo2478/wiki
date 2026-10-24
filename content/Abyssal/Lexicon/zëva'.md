---
type: word
word: zëva'
lemma: zëva'
language: Abyssal
pos:
  - noun
root: ""
ipa: zəvaʔ
gloss: ""
definition:
  - (n.) the act or condition of flickering, twinkling, or shining intermittently
  - (n.) an indefinitely short period of time
  - (n.) Usually the moment the present time or any other particular time.
tags:
  - lexicon
---

# zëva'

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