This prompt prepares material for learning German on a specific topic. See prepared materials in [[Thema]].

Good model: `ChatGPT o3`.

Use `Ctrl + Shift + V` to paste the result from AI 🤖 into an Obsidian note: this will preserve the formatting.

```
v1.10.0

I started learning German. Prepare materials for me on the topic in the given language. See below.

<topic>
The kitchen
</topic>


<language>
Russian
</language>


<aim>
Learn to understand texts (reading), listen and speak on a given topic.
</aim>


<structure_material>

<grammatic>
The 12 most commonly used verbs, 40 nouns and 20 adjectives on this topic.
Make it in the form of 3 tables.
</grammatic>

<dialog>
Several dialogues on this topic using these verbs, nouns and adjectives with translation to language.
</dialog>

</structure_material>


<compatibility>
Prefer compact answers.
</compatibility>

<format_table>

<all>
ONLY respond with formatted Markdown text. NO programmatic generation or tool usage.

Do not use any code to generate the table.
Do not use Python, pandas, or any code-related tools.
Just output a plain Markdown as formatted text in the reply.

Create a table in Markdown format. The first column is the original text. The second column is the grammatic. The third column is the translation. See the form below.
Do not enclose the entire text in brackets.
</all>

<verb>
Before the table, write a heading `## Verben`.
For each verb except the ones in section `<exclude>` (see below), write:
- the verb in German with conjugation `ich - du - man - wir - ihr - Sie` in Präsens; if the verb has a separable prefix, omit the prefix;
- its Präteritum with conjugation `ich - du - man - wir - ihr - Sie`; if the verb has a separable prefix, omit the prefix;
- its Perfekt form with one conugation for `man` (with `hat` oder `ist`) in German;
- markers `A` - for Akkusativ verb, `D` - for Dativ verb, `D+A` - for Dativ and Akkusativ verb;
- an example of a simple sentence with this verb.
Wrap this in the `Grammatik` column.
Use a new line as separator for groups.

Don't write:
- a translation in parentheses;
- any explanations like `Präsens`, `Präteritum`, `Perfekt`, `Kasus`, `Beispiel`, `Syn`, `Ant`, etc.

Omit pronouns `ich - du - man - wir - ihr - Sie` when writing down verb conjugations.

Add to `Translation` column also:
- a list of verbs without prefix (if the verb is prefixed with) with translation;
- a list of verbs with different prefixes (if the verb is used in the language with the following prefixes) with translation;
- a list of synonimous verbs with translation;
Use a new line as separator for groups.

Sort alphabetically by first column.

<exclude>
all modal verbs
habe, hast, hat, haben, habt
sehen
sein, bist, ist, sind, seid
war, warst, wart, waren
werde, werden
wurde, wurdst, wurden
</exclude>
</verb>

<noun>
Before the table, write a heading `## Nomen`.
For each noun except the ones in section `<exclude>` (see below), write:
- the noun in the singular in German with its singular article (der, die, das);
- its plural in German without `die` article separated by comma;
- an example of a simple sentence with this noun and verb.
Wrap this in the `Grammatik` column.
Use a new line as separator for groups.

Don't write:
- a translation in parentheses;
- any explanations like `Singular`, `Plural`, `Verben`, `Beispiel`, `Ant`, `Syn`, `Verben`, etc.

The article write in the `Grammatik` column only, omit the article in the first column.

Add to the `Translation` column also:
- a list of words that make up the noun (if the word is compound) with artikle `der-die-das` for noun, translation; or nothing if a whole word;
- 2-6 most frequently used verbs with this noun, but do not repeat verbs that you have already added to other nouns;
- a list of verbs that are derived from the noun, or the word itself is derived from them;
- a list of synonimous nouns with translation;
Use a new line as separator for groups.

Sort alphabetically by first column.
<exclude>
</exclude>
</noun>

<adjective>
Before the table, write a heading `## Adjektive`.
For each adjective except the ones in section `<exclude>` (see below), write:
- the adjective in German;
- its antonym in German.
Use a hyphen ` - ` as separator for groups.
Wrap this in the `Grammatik` column.

Don't write:
- a translation in parentheses;
- any explanations like `Original`, `Gegental`, `Syn`, `Ant` etc.

Add to the `Translation` column also:
- a translation with antonym in the column of translation (hyphenated);
- a list of synonimous adjective with translation;
Use a new line as separator for groups.

Sort alphabetically by first column.

<exclude>
dunkel
groß
klein
hell
</exclude>
</adjective>

<dialog>
Number the dialogs as `## 1, ## 2, ...`.
Each dialog write in the form of a table, as separated table. The first column in the table is the dialog, the second is the translation. Write each replica on a separate line.
</dialog>

</format_table>
```
