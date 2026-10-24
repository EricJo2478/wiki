---
language: Proto-Vorathic
tags:
  - phonology
type: phonology
aliases:
  - phonology
---

| Consonants (20) | Labial | Dental | Alveolar | Palatal | Velar | Uvular | Glottal |
| --------------- | ------ | ------ | -------- | ------- | ----- | ------ | ------- |
| Stops           | p / b  |        | t / d    |         | k / g |        |         |
| Fricatives      | f / v  |        | s / z    |         |       |        | h / ɦ   |
| Approximates    | w      |        | l / ɹ    | j       |       |        |         |
| Nasals          | m      |        | n        | ɲ       | ŋ     |        |         |

| Vowels (11) | Front   | Central | Back |
| ----------- | ------- | ------- | ---- |
| High        | i, y    | ɨ       | u    |
| Mid         | e, ɛ, ø | ə       | o    |
| Low         | æ       |         | ɑ    |

### Syllable Structure: CV(C)

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
