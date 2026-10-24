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
language: "<% defaultLang %>"
type: "phonology"
tags:
  - "phonology"
---

| Consonants (20) | Labial          | Dental | Alveolar            | Palatal | Velar                 | Uvular     | Glottal |
| --------------- | --------------- | ------ | ------------------- | ------- | --------------------- | ---------- | ------- |
| Stops           | p / b / p' / pʰ |        | t / d / t' / tʰ, ts |         | k / g / k' / kʰ / kʰʷ | q / ɢ / q' | ʔ       |
| Fricatives      | β, f / v        | θ / ð  | s / z               | ʃ       | x / ɣ                 | χ / ʁ      | h / ɦ   |
| Approximates    | ʍ / w           |        | l / ɹ / r           | j       |                       | ʀ          |         |
| Nasals          | m               |        | n                   | ɲ       | ŋ                     |            |         |

| Vowels (11) | Front       | Central | Back        |
| ----------- | ----------- | ------- | ----------- |
| High        | i, iː, y    | ɨ       | ɯ, u, uː, ʊ |
| Mid         | e, eː, ɛ, ø | ə       | o, oː, ɔ, ɤ |
| Low         | æ           | a, aː   | ɑ, ɑː       |

### Syllable Structure: ????
### Sound Changes (Proto: [[]])

# Sound Frequency
```dataviewjs
// 1. Automatically pull the language from the current note's YAML frontmatter
const currentNote = dv.current();
const targetLanguage = currentNote ? currentNote.language : null;

if (!targetLanguage) {
    dv.paragraph("⚠️ **Error:** No `language` property found in this note's YAML frontmatter. Please add `language: \"Abyssal\"` (or your target language) to this page.");
} else {
    // 2. Fetch pages tagged with #lexicon and filter by that language
    const pages = dv.pages("#lexicon").where(p => p.language === targetLanguage);

    const wordCounts = {};       
    const occurrenceCounts = {}; 

    function extractSounds(ipaString) {
        if (!ipaString) return [];
        let cleaned = ipaString.replace(/[\s.ˈˌ]/g, "");
        let sounds = [];
        let i = 0;
        while (i < cleaned.length) {
            let char = cleaned[i];
            let nextChar = cleaned[i + 1];
            let twoChar = char + (nextChar || "");
            
            if (nextChar === "'" || twoChar === "t͡s" || twoChar === "t͡ʃ" || twoChar === "d͡ʒ") {
                sounds.push(twoChar);
                i += twoChar.length;
            } else {
                sounds.push(char);
                i += 1;
            }
        }
        return sounds;
    }

    for (let p of pages) {
        if (p.ipa) {
            const sounds = extractSounds(p.ipa);
            
            for (let sound of sounds) {
                occurrenceCounts[sound] = (occurrenceCounts[sound] || 0) + 1;
            }
            
            const uniqueSoundsInWord = [...new Set(sounds)];
            for (let sound of uniqueSoundsInWord) {
                wordCounts[sound] = (wordCounts[sound] || 0) + 1;
            }
        }
    }

    const allSounds = [...new Set([...Object.keys(occurrenceCounts), ...Object.keys(wordCounts)])];
    allSounds.sort((a, b) => (occurrenceCounts[b] || 0) - (occurrenceCounts[a] || 0));

    const tableData = allSounds.map(sound => [
        `\`${sound}\``, 
        wordCounts[sound] || 0,
        occurrenceCounts[sound] || 0
    ]);

    dv.table([`Sound (${targetLanguage})`, "Word Count", "Total Occurrences"], tableData);
}
```
