---
type: word
word: "tïhà"
lemma: "tïhà"
language: "Proto-Vorathic"
pos:
  - Noun
root: ""
ipa: "tɨhɑ"
gloss: ""
definition:
  - (n.) something that is large, as in size, height, width, or amount.
  - (n.) something this is important, as in influence, standing, or wealth.
  - (n.) ability to do or act; capability of doing or accomplishing something.
  - (n.) political or national strength.
  - (n.) great or marked ability to do or act;
  - (n.) the possession of control or command over people
  - (n.) a person or thing that possesses or exercises authority or influence.
tags:
  - lexicon
---

# tïhà

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