---
language: Vorathic
tags:
  - phonology
type: phonology
aliases:
  - phonology
---

| Consonants (22) | Labial     | Dental | Alveolar       | Palatal | Velar      | Uvular | Glottal |
| --------------- | ---------- | ------ | -------------- | ------- | ---------- | ------ | ------- |
| Stops           | p / b / p' |        | t / d / t', ts |         | k / g / k' |        | ʔ       |
| Fricatives      | f / v      |        | s / z          |         |            |        |         |
| Approximates    | w          |        | l / ɹ          |         |            | ʀ      |         |
| Nasals          | m          |        | n              |         | ŋ          |        |         |

| Vowels (3) | Front | Central | Back |
| ---------- | ----- | ------- | ---- |
| High       |       |         | u    |
| Mid        |       |         | o    |
| Low        |       | a       |      |

### Syllable Structure: (C)(C)(C)V(C)(C)
### Sound Changes (Proto: [[Proto-Vorathic/Phonology|Proto-Vorathic]])  

| Name                                                    | Change                                                                                          |
| ---                                                     | ---                                                                                             |
| Initial Vowel Loss                                      | vowels are lost word initially when surounded by voicless stops/fricatives                      |
| Ejectives                                               | `p`, `t`, and `k` becomes `p'`, `t'`, `k'` when followed by `h` and the `h` is lost             |
| Glottal Stop                                            | `ɦ` becomes `ʔ` intervocalically                                                                |
| Glottal Devoicing                                       | `ɦ` becomes `h` universally                                                                     |
| Glide Initially                                         | `h` becomes `w` word initially                                                                  |
| H Loss                                                  | `h` is lost universally                                                                         |
| Front Vowel Collapse                                    | front vowels are lost when preceded by a fricative and followed by a stop                       |
| Final Vowel Loss                                        | word final vowels are lost when preceded by a stop or fricative                                 |
| Rhotic Backing                                          | `ɹ` becomes `ʀ` when followed by `u`, `o`, or `ɑ`                                               |
| Ts Development                                          | `t` and `s` become `ts` when followed by `y` or `i` or `j`, the `j` is lost in this case        |
| J Fricativiation                                        | `j` becomes `z` universally                                                                     |
| A Squoosh                                               | `ɑ`, `æ`, and `ə` becomes `a` universally                                                       |
| U Squoosh                                               | `y`, `i`, and `ɨ` becomes `u` universally                                                       |
| O Squoosh                                               | `e`, `ɛ`, and `ø` becomes `o` universally                                                       |
| Nasal Backing                                           | `ɲ` becomes `ŋ` when followed by `o` or `u`                                                     |
| Nasal Palatal Loss                                      | `ɲ` becomes `n` universally                                                                     |
| Glottal Stop Shrinkage                                  | `ʔ` is lost when not intervocalic                                                               |
| Bilablial Simplification                                | when a bilabial stop and fricative are beside eachother the stop is absorbed into the fricative |


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
