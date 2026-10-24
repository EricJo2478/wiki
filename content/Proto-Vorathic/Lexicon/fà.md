---
type: word
word: "fà"
lemma: "fà"
language: "Proto-Vorathic"
pos:
  - noun
root: ""
ipa: "fɑ"
gloss: ""
definition:
  - (n.) absence or deficiency of light.
  - (n.) obscurity; concealment.
  - (n.) lack of sight; blindness.
  - (n.) the state or quality of being dark
  - (n.) the comparative darkness caused by the interception or screening of rays of light from an object, place, or area.
  - (n.) a place or an area of comparative darkness, such as one sheltered from the sun.
  - (n.) a thing that is a color that lacks hue and brightness and absorbs light without reflecting any of the rays composing it.
tags:
  - lexicon
---

# fà

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