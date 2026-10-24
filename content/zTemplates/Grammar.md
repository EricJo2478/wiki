<%*
// Prompt for the word name
let title = await tp.system.prompt("Enter a part of grammar (Adj, Noun, Verb, Adv, Case, Class, Coord, Dem, Num, Pro, Que, Rel):");
let abr = ["adj", "noun", "verb", "adv", "case", "class", "coord", "dem", "num", "pro", "que", "rel"]
let titles = ["Adjectives", "Nouns", "Verbs", "Adverbs", "Cases", "Classes", "Coordination", "Demonstratives", "Numbers", "Pronouns", "Questions", "Relative Clauses"]
let aliases = [
["adjective", "adjectives", "Adjective"], 
["noun", "nouns", "Noun"], 
["verb", "verbs", "Verb"], 
["adverb", "adverbs", "Adverb"], 
["case", "cases", "Case"], 
["class", "classes", "Class"], 
["coordination"], 
["demonstrative", "demonstratives", "Demonstrative"],
["number", "numbers", "Number"], 
["pronoun", "pronouns", "Pronoun"], 
["question", "questions", "Question"], 
["relative clause", "relative clauses", "Relative Clause", "Relative clause", "Releative clauses"]]
let index = abr.indexOf(title.toLowerCase())
if (index > -1) {
	title = titles[index]
}

let folder = tp.file.folder(true); let defaultLang = "Proto-Vorathic"; 
if (folder.includes("Vorathic") && !folder.includes("Proto")) { 
	defaultLang = "Vorathic"; 
} else if (folder.includes("Abyssal")) { 
	defaultLang = "Abyssal"; 
} else if (folder.includes("Infernal")) { 
	defaultLang = "Infernal"; 
}

// If the user entered a name, rename the file to that name
if (title) {
	await tp.file.rename(title);
} else {
    // Fallback to title if prompt is canceled
    title = "Grammar";
}

if (index > -1) {
	tp.hooks.on_all_templates_executed(async () => { 
		// Locate the current active file 
		const file = tp.file.find_tfile(tp.file.path(true)); 
		// Process and update the frontmatter 
		if (file) {
			await app.fileManager.processFrontMatter(file, (frontmatter) => { 
				frontmatter['aliases'] = aliases[index]; 
				frontmatter['tags'] = ['grammar', aliases[index][0].replaceAll(" ", "-")];
			});
		}
	});
}
-%>
---
language: "<% defaultLang %>"
type: grammar
---
# <% title %>