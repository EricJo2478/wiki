---
language: Proto-Vorathic
type: grammar
aliases:
  - verb
  - verbs
  - Verb
tags:
  - grammar
  - verb
---
# Verbs
Verbs in `=this.language` do a lot less heavy lifting than in Vorathic since they don't take any direct inflection. However there is a word order for the post verb auxiliaries. Seen below.
ROOT SUBJECT-CLASSIFIER OBJECT-CLASSIFIER VOICE POLARITY TENSE
### Transitivity
Verbs in `=this.language` do not inflect. Though there are intransitive and transitive verbs. They are treated the same. 
# Voice
If a verb is in the passive voice then a modifier auxiliary follows the verb. In the event that no passive auxiliary is present then the verb is assumed to be in the active voice. See an example below:

- SUBJECT"demon" CLASSFIER"power" VERB"attack" CLASSIFIER"power" VOCE"passive" > "something attacks the demon"
### Polarity
Polarity is simply an auxiliary that follows the verb to mark negation. The positive is assumed when no negation is marked.
### Tense
Tense is handled similarly to polarity. Present tense is assumed when no tense auxiliary is present.
### Copula
`=this.language` uses a zero copula. For the present tense the verb is omitted entirely in the Positive. For other tenses use the auxiliary verbs alone with no base verb.
