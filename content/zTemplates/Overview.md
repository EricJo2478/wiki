<%*
let folder = tp.file.folder(true); let defaultLang = "Proto-Vorathic"; 
if (folder.includes("Vorathic") && !folder.includes("Proto")) { 
	defaultLang = "Vorathic"; 
} else if (folder.includes("Abyssal")) { 
	defaultLang = "Abyssal"; 
} else if (folder.includes("Infernal")) { 
	defaultLang = "Infernal"; 
}
-%>
---
proto: ""
family: ""
language: "<% defaultLang %>"
type: "overview"
tags: 
- "overview"
---
description
# Spoken by
- Creatures