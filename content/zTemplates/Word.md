<%*
// Prompt for the word name
let wordName = await tp.system.prompt("Enter the conlang word / title:");

let folder = tp.file.folder(true); let defaultLang = "Proto-Vorathic"; 
if (folder.includes("Vorathic") && !folder.includes("Proto")) { 
	defaultLang = "Vorathic"; 
} else if (folder.includes("Abyssal")) { 
	defaultLang = "Abyssal"; 
} else if (folder.includes("Infernal")) { 
	defaultLang = "Infernal"; 
}

// If the user entered a name, rename the file to that name
if (wordName) {
    await tp.file.rename(wordName);
} else {
    // Fallback to title if prompt is canceled
    wordName = tp.file.title;
}
-%>
---
type: word
word: "<% wordName %>"
language: "<% defaultLang %>"
pos:
  -
class: ""
root: ""
derivation_type: ""
noun_class: ""
transitivity: ""
stative: false
ipa: ""
gloss: ""
translation:
  -
tags:
  - lexicon
  - word
---

# <% wordName %>

* **Pronunciation (IPA):** `=this.ipa`
* **Part of Speech:** `=this.pos`
* **Root:** `=this.root`

### Definitions
* 

---

## Etymology & Evolution
* **Derivational Process:** `=this.derivation_type`
* **Proto-Form:** 
* **Historical Shift Notes:** 

## Usage & Examples
> **[Sample sentence]**
> *"[Translation]"*

## Related Words (same root)
```dataview
TABLE pos AS "POS", translation AS "Meaning"
FROM #lexicon
WHERE root = this.root AND file.name != this.file.name AND derivation_type != "root"
```