---
language: Abyssal
type: grammar
tags:
  - verb
  - grammar
aliases:
  - Verb
  - verb
  - verbs
---
# Verbs
Verbs in `=this.language` to a lot of heavy lifting. They agree with noun [[Abyssal/Grammar/Classes|class]], both the subject and direct object (if present). The conjugate for voice (passive/active), polarity (positive/negative), mood (generic/imperative/refusal/indifference), and tense (past/present/future).
### Transitivity
Verbs in `=this.language` have 3 different sets of infection: Intransitive, Active Transitive, Passive Transitive. Each of these transitivity types takes a different set of verbal suffixes (containing tense, polarity and mood), which come from old auxiliaries. Between these inflections and the verb root agreement suffixes also form, see those below. Examples of intransitive verb constructions:

- SUBJECT"demon" VERB"attack"-SUB-INF"pos-present"    "the demon is attacking"
### Agreement
In the above example SUB is agreement for class I, since intransitive verbs agree with their subjects. Transitive verbs agree with their subject followed by their object. 
### Polarity/Mood
Polarity and mood are handled the same in `=this.language`. In the positive there is the Generic or the Imperative. In the negative we distinguish between Generic, Refusal or Indifference. All of the forms for the different transitivities are in the tables at the end of this note.
### Tense
Tense is handled similarly to polarity and mood. As seen in the tables below the suffix changes based on tense. The imperative mood can ONLY take a present tense. 
### Copula
`=this.language` uses a zero copula. For the present tense the verb is omitted entirely in the Positive Generic. For other tenses use the Intransitive suffix alone with no verb root as the copular verb.

| Intransitive | <            | Past | Present | Future |
| ---          | ---          | ---  | ---     | ---    |
| Pos          | Generic      |      |         |        |
| ^            | Imperative   |      | <       | <      |
| Neg          | Generic      |      |         |        |
| ^            | Refusal      |      |         |        |
| ^            | Indifference |      |         |        |


| Transitive Active | <           | Past | Present | Future |
| ---          | ---          | ---  | ---     | ---    |
| Pos          | Generic      |      |         |        |
| ^           | Imperative   |      | <      | <     |
| Neg          | Generic      |      |         |        |
| ^           | Refusal      |      |         |        |
| ^           | Indifference |      |         |        |

| Transitive Passive | <            | Past | Present | Future |
| ---                | ---          | ---  | ---     | ---    |
| Pos                | Generic      |      |         |        |
| ^                  | Imperative   |      | <       | <      |
| Neg                | Generic      |      |         |        |
| ^                  | Refusal      |      |         |        |
| ^                  | Indifference |      |         |        |
