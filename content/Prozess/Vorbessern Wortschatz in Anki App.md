We can refine the all part of speech from Anki Desktop to Anki Desktop - https://apps.ankiweb.net

Attach the exported notes from Anki Desktop to this prompt.

Good models: `Claude 3.7`, `ChatGPT`.

Use this prompt to the end of processing:
```
Next. Process as many words as possible.
```

See also [[Grammatik in Anki App]], [[Organisieren von Sprachlerndecks in Anki - Ukrainisch]], and [[Text to Anki App]].

```
v1.9.0

You have a FILE or TEXT in CSV format with German words with column:
`Front` The face of card. The German word, phrase, or sentence.
`Back` The back card. Now it is empty.
`Tags` The list of tags, space separated.

I need this for learn German. I know Ukrainian.

Refine this.
The result should be improved and supplemented as follows for each part of speech.


<compatibility>
Prefer compact answers.
</compatibility>

<all>
ONLY respond with formatted codeblock Markdown text. NO programmatic generation or tool usage.

Ignore the parts of speech that are not explicitly specified to be processed below. Don't include them in the result.

Do not use any code to generate the result.
Do not use Python, pandas, or any code-related tools.
Just output a plain Markdown as formatted text in the reply.
</all>


<verb>

The verbs.

<data_in_column_front>
Transform a reflexive verb without preposition to format like `sich verb`.
Transform a reflexive verb with preposition to format like `sich verb preposition`.

If a verb changes its meaning depending on the preposition and such a verb with a preposition is not in the word list, add the verb with the missing preposition to the list. Example: `sich unterhalten mit`, `sich unterhalten über`.

If a verb can be used without a preposition and has a different meaning, add it to the list as well.
</data_in_column_front>


<data_in_column_back>
In this column, create training materials.

For each verb write:
- the verb in German with conjugation `ich - du - man - wir - ihr - Sie` in Präsens; if the verb has a separable prefix, omit the prefix;
- its Präteritum with conjugation `ich - du - man - wir - ihr - Sie`; if the verb has a separable prefix, omit the prefix;
- its Perfekt form with one conugation for `man` (with `hat` oder `ist`) in German;
- markers `A` - for Akkusativ verb, `D` - for Dativ verb, `D+A` - for Dativ and Akkusativ verb;
- a translation this verb to my native language;
- an example of a simple sentence with this verb with `ich`, `wir`, or `Sie/sie` with translation;
- a list of verbs without prefix (if the verb is prefixed with) with translation; each is separated by `<br>`;
- a list of verbs with different prefixes (if the verb is used in the language with the following prefixes) with translation; each is separated by `<br>`;
- a list of synonimous verbs with translation; each is separated by `<br>`;
- use an HTML separator `<br><br>` for each group above.

Don't write:
- a translation in parentheses;
- any explanations like `Präsens`, `Präteritum`, `Perfekt`, `Kasus`, `Beispiel`, `Syn`, `Ant`, etc.

Exclude an unprefixed verb if it is always used exclusively with a prefix.

Omit pronouns `ich - du - man - wir - ihr - Sie` when writing down verb conjugations.
</data_in_column_back>


<data_in_column_tags>
Preserve tags. No changes.
</data_in_column_tags>

</verb>


<noun>

The nouns.

<data_in_column_front>
Preserve data. No changes.
</data_in_column_front>


<data_in_column_back>
In this column, create training materials.

For each noun write:
- the noun in the singular in German with its singular article (der, die, das);
- its plural in German without `die` article separated by comma;
- a translation this noun to my native language;
- an example of a simple sentence with this noun with translation;
- a list of words that make up the noun (if the word is compound) with artikle `der-die-das` for noun, translation; or nothing if a whole word;
- 2-6 most frequently used verbs with this noun, but do not repeat verbs that you have already added to other nouns with translation;
- a list of verbs that are derived from the noun, or the word itself is derived from them with translation;
- a list of synonimous nouns with translation;
- use an HTML separator `<br><br>` for each group above.

Don't write:
- a translation in parentheses;
- any explanations like `Singular`, `Plural`, `Verben`, `Beispiel`, `Ant`, `Syn`, etc.

</data_in_column_back>


<data_in_column_tags>
Preserve tags. No changes.
</data_in_column_tags>

</noun>


<adjective>

The adjectives.

<data_in_column_front>
Preserve data. No changes.
</data_in_column_front>


<data_in_column_back>
In this column, create training materials.

For each adjective write:
- a translation this adjective to my native language;
- an antonym this adjective and its translation to my native language;
- an example of a simple sentence with this adjective with translation;
- a list of synonimous adjectives with translation;
- 2-6 most frequently used nouns with this adjective in the singular in German with its singular article (der, die, das), but do not repeat nouns that you have already added to other nouns with translation;
- use an HTML separator `<br><br>` for each group above.

Don't write:
- a translation in parentheses;
- any explanations like `Singular`, `Plural`, `Verben`, `Beispiel`, `Ant`, `Syn`, `Adj`, etc.

</data_in_column_back>


<data_in_column_tags>
Preserve tags. No changes.
</data_in_column_tags>

</adjective>


<postprocess>
Remove duplicates.
</postprocess>

```
