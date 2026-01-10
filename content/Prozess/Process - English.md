It describes the process of translating any page from a German book into your **native language**. For **nouns**, the articles are determined. For **verbs**, the infinitive and perfect forms are indicated. For **adjectives**, their antonyms are indicated to expand the vocabulary.

You can change the instructions (see below) as you wish.

## Process

## Perplexity

Create a shortcut `/learn-de-ru` with the prompt text.
Write the shortcut and paste the text to be translated under it.
Wait an say `continue` after stop.

> If we don't paste the text, after `continue` we will get hallucinations on the topic, but it will not be our text.

### Chat GPT

Open the ChatGPT.
Attach a photo of the page to your message.
Paste the prompt below.
Choose the model `o1` or `o` (model `o1` gives the best result).
Copy the result to a new Google Docs document and print it (`pdf`).

### Alternative Process

Copy the result from ChatGPT to **Obsidian** (`Ctrl + Shift + V` in note).
The most convenient mode in **Obsidian** for assembling a page: `Source mode`.
Export to `pdf` and print it.

## Prompt

```
v4.2.0

German language. Translate the text on the attached photo(s), file(s), Internet page or the text below into Russian. Translate the entire text, If necessary, break it down into parts: I will say "continue" to translate the next part.

<extraction>
Manually extract the text.
Leave the original text as well.
Do not solve the tasks.
</extraction>

<chunks>
Continue processing until all chunks are processed.
</chunks>

<compatibility>
Prefer compact answers.
</compatibility>

<format>

<all>
ONLY respond with formatted Markdown text. NO programmatic generation or tool usage.

Do not use any code to generate the table.
Do not use Python, pandas, or any code-related tools.
Just output a plain Markdown table as formatted text in the reply.

Create a table in Markdown format. The first column is the original text. The second column is the grammatic. The third column is the translation. See the form below.
Do not enclose the entire text in brackets.
</all>

<original>
Try to keep the formatting, but not tables.
Avoid using bold or italic for the entire sentence.
</original>

<translation>
Leave the text of the translation in the same format as the original.
Do not write the original parts of speech in the translated column.
Do not use the words "Original" / "Translation".
Place each sentence, each logical block of text in a separate line of the table.
Break blocks of more than 2 sentences into multiple rows.

<verb>
Always write a translation for a verb in the sentence.
For each verb except the ones in section `<exclude>` (see below), write the verb in German (Infinitive), its Präteritum, and its Perfekt form (with `hat` oder `ist`) in German and markers `A` - for Akkusativ verb, `D` - for Dativ verb, `A+D` - for Akkusativ and Dativ verb. Wrap this in the `Grammatik` column. Don't write a translation in parentheses.
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
Always write a translation for a noun in the sentence.
For each noun, write the noun in the singular in German with its singular article (der, die, das) and plural in German without `die` article separated by comma. Wrap this in the `Grammatik` column. Don't write a translation in parentheses.
</noun>

<adjective>
Always write a translation for an adjective in the sentence.
For each adjective, write the adjective in German and its antonym in German (hyphenated). Wrap this in the `Grammatik` column. Don't write a translation in parentheses.
</adjective>

</translation>

<validation>
For every sentence:
- Identify at least one verb (except excluded ones), noun, and adjective if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines. If no parts of speech, leave cell empty.
</validation>

</format>

<result>
Follow the instructions in the `<exercise>` section and add a fourth column named `Lösung` to Markdown table with the correct answer if you have that section available.

Always follow these rules strictly:
- Always detect and extract all verbs, nouns, adjectives.
- Do not skip any part of speech unless it’s in `<exclude>`.
- Do not collapse long blocks into one row.
- Never skip rows unless the line is empty.

Show only the result formatted into table with headers (pay attention to the logic of `<excercise>` section):

| Satz | Grammatik | Übersetzung |
|------|-----------|-----|
| ...  | ...       | ... |

In the "Grammatik" column:
- Show only the verbs, nouns, and adjectives (e.g. `lesen`, `der Satz`, `gut` etc.).
- For verbs: show format like `⚡lesen (las, hat gelesen, A)`. Use emoji ⚡ before the verb.
- For nouns: show format like `🏷️das Haus (Häuser)`. No need to say an article for plural. Pick an emoji that best represents each noun. For instance: `🐶der Hund`, `🐱die Katze`, `🏠das Haus`, `🌳 der Baum`, `🏞️ das Land`, `⌛die Zeit`, `📧die E-Mail`. If you cannot find a suitable emoji that fits well, use a default like `🏷️`.
- For adjectives: show format like `🎨neu (alt)`. No need to say `adjective` or `antonym`. Use emoji 🎨 before the adjective.
- Use a space (don't use a comma, don't use a new line) to separate parts of speech in the cell.
- Write out only: verbs, nouns, and adjectives.

Keep translation as is in the last column.

Use a space instead of a non-breaking space, `&nbsp;`, or tab.

Keep Markdown table formatting clean and readable.
Sort the keywords into the cells in natural sentence order.

Check and fix the formatting. Each row of the Markdown table should contain the original, grammar, and a suitable translation.

Skip the show steps, intro and outro: just output the result.

</result>

<test>
Ensure that the sentence "Der kleine Hund läuft schnell." results in:
- ⚡laufen
- 🐶der Hund (Hunde)
- 🎨klein (groß)
</test>

```

### Extract text only

Model ChatGPT `o` copes well with this prompt.

```
v1.1.0

German language. Recognize the text in the photo(s).

Convert it into a regular editable text in Markdown or plain text format, preserving the structure, paragraphs, lists, tables, headings, etc. as much as possible. But if you come across a sentence, write it in one piece, without breaks: keep in mind that it can be carried over to the next line, a word can be carried over to the next line using a hyphen.

Do not solve the tasks.

ONLY respond with formatted Markdown text. NO programmatic generation or tool usage.

Do not use any code to generate the table.
Do not use Python, pandas, or any code-related tools.
Just output a plain Markdown table as formatted text in the reply.

Do not add comments or descriptions, just return the text.

Avoid using bold or italic for the entire sentence.

Skip the show steps, intro and outro: just output the result.
```

### + Übung

Add this prompt **before** the `<result>` section in the prompt above.

```
v1.5.0

<exercise>
Replace the original German sentence with the **gap-fill version directly in the main translation Markdown table**, like this:
| Satz (Lückentext) | Grammatik | Übersetzung in Deine Muttersprache | Lösung |

Analyze each sentence and, if it is appropriate for the excercise, turn it into a gap-fill exercise.

Only choose sentences that have the potential to teach, i.e:
- contain verbs, prepositions, articles, adjectives
- or allow you to build a natural gap for your writing
- or to train memory and grammar

Provide gaps as underlines for the number of letters according to the length of the word and include hints in parentheses and italics immediately after it in the form:
- the number of letters, with umlauts (ä, ö, ü) counted as one letter
- part of speech
- additional useful information for learning
Examples of hints: `(5 Adj. Komparativ)`, `(6 V.)`, `(4 Nom.)`, `(Präp. + Art. + Nom.)`, `(Art.)`, `(4 Adj., Gegensatz zu "lebend")`.
For the parts of speech, use the abbreviations used in the dictionaries of the source language.

</exercise>
```

### & Wortschatz

Write these prompts **after** the translate of the entire text.
We can send all the prompts below as one.

The best model: `Chat GPT o3`

Send a text without lines and tables separators for best result. We can sort later parts of the table after insertion as solid table in Obsidian notes.

#### Verb + Noun + Adjective

```
v3.3.0

Gather all verbs, nouns, and adjectives from the TEXT, or file, or photo.
Do it step by step (see below) as separate messages - first with verbs, second with nouns, third with adjectives - but include all the verbs, nouns, or adjectives you find in one message. I will say `contune` after each of your messages, but I'm waiting for the whole group - verbs, nouns, or adjectives - to come together in one message.

Organize the each group - verbs, nouns, adjectives - alphabetically.
Print it in the form of tables in Markdown format.
Do not use a format in a cell.

<compatibility>
Prefer compact answers.
</compatibility>

<step_verb>
Gather all verbs.
Do not include modal verbs, `sein`, and `haben`.
Organize the verbs alphabetically.

<validation>
For every sentence:
- Identify at least one verb (except excluded ones) if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines.
</validation>

<format>
|Infinitiv|Präteritum|Perfekt|Kasus|Übersetzungsoptionen|Hinweis|
- No emoji.
- Kasus: A, D, A+D.
- `Übersetzungsoptionen` column. Translation options to Ukrainian for contexts that appear in the text.
- In the right column for a verb with a prefix, write down an existing word without a prefix and the translation of this word. Examples of rows: `|abschließen|hat abgeschlossen|schloss ab|A|завершити|schließen близько|`, `|umsteigen|ist umgestiegen|stieg um| |пересідати|steigen підніматися|`.
</format>
</step_verb>


<step_noun>
Gather all nouns from the TEXT.
Do not include proper names.
Organize the nouns alphabetically.

<validation>
For every sentence:
- Identify at least one noun (except excluded ones) if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines.
</validation>

<format>
|Singular|Plural|Übersetzungsoptionen|Benutzen|
- Pick an emoji for singular that best represents each noun. For instance: `🐶der Hund`, `🐱die Katze`, `🏠das Haus`, `🌳 der Baum`, `🏞️ das Land`, `⌛die Zeit`, `📧die E-Mail`. If you cannot find a suitable emoji that fits well, use a default like `🏷️`.
- Singular with article.
- Plural without article.
- `Übersetzungsoptionen` column. Translation options to Ukrainian for contexts that appear in the text.
- In the right column, write one or two commonly used verbs with this noun, but do not write the noun itself. Example for `der Termin`: `erneren, stornieren`. 
</format>
</step_noun>


<step_adjective>

Gather all adjectives from the TEXT.
Organize the adjectives alphabetically.

<validation>
For every sentence:
- Identify at least one adjective (except excluded ones) if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines.
</validation>

<format>
|Adjektiv|Antonym|Übersetzungsoptionen|Phrase|
- No emoji.
- `Übersetzungsoptionen` column. Translation options to Ukrainian for contexts that appear in the text.
- Translate the adjective and antonym in the last column. Example for `|gehime|offen|`: `таємний / відкритий`.
- In the right column, write a grammatically correct phrase (but not sentence!) with this adjective plus a noun plus a commonly used verb to help me remember it better. Try to use the existing phrases from the TEXT.
</format>
</step_adjective>

```

#### Verb

```
v2.3.0

Gather all verbs from the TEXT.
Do not include modal verbs, `sein`, and `haben`.
Organize the verbs alphabetically.
Print it in the form of tables in Markdown format.
Do not use a format in a cell.

<chunks>
Continue processing until all chunks are processed.
</chunks>

<validation>
For every sentence:
- Identify at least one verb (except excluded ones) if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines.
</validation>

<compatibility>
Prefer compact answers.
</compatibility>

<format>
|Infinitiv|Präteritum|Perfekt|Kasus|Übersetzungsoptionen|Hinweis|
- No emoji.
- Kasus: A, D, A+D.
- `Übersetzungsoptionen` column. Translation options to Ukrainian for contexts that appear in the text.
- In the right column for a verb with a prefix, write down an existing word without a prefix and the translation of this word. Examples of rows: `|abschließen|hat abgeschlossen|schloss ab|A|завершити|schließen близько|`, `|umsteigen|ist umgestiegen|stieg um| |пересідати|steigen підніматися|`.
</format>
```

#### Noun

```
v2.2.0

Gather all nouns from the TEXT.
Do not include proper names.
Organize the nouns alphabetically.
Print it in the form of tables in Markdown format.
Do not use a format in a cell.

<chunks>
Continue processing until all chunks are processed.
</chunks>

<validation>
For every sentence:
- Identify at least one noun (except excluded ones) if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines.
</validation>

<compatibility>
Prefer compact answers.
</compatibility>

<format>
|Singular|Plural|Übersetzungsoptionen|Benutzen|
- Pick an emoji for singular that best represents each noun. For instance: `🐶der Hund`, `🐱die Katze`, `🏠das Haus`, `🌳 der Baum`, `🏞️ das Land`, `⌛die Zeit`, `📧die E-Mail`. If you cannot find a suitable emoji that fits well, use a default like `🏷️`.
- Singular with article.
- Plural without article.
- `Übersetzungsoptionen` column. Translation options to Ukrainian for contexts that appear in the text.
- In the right column, write one or two commonly used verbs with this noun, but do not write the noun itself. Example for `der Termin`: `erneren, stornieren`. 
</format>
```

#### Adjective

```
v2.2.0

Gather all adjectives from the TEXT.
Organize the adjectives alphabetically.
Print it in the form of tables in Markdown format.
Do not use a format in a cell.

<chunks>
Continue processing until all chunks are processed.
</chunks>

<validation>
For every sentence:
- Identify at least one adjective (except excluded ones) if they are present.
- Split blocks of more than 2 sentences into multiple rows.
- Do not skip lines.
</validation>

<compatibility>
Prefer compact answers.
</compatibility>

<format>
|Adjektiv|Antonym|Übersetzungsoptionen|Phrase|
- No emoji.
- `Übersetzungsoptionen` column. Translation options to Ukrainian for contexts that appear in the text.
- Translate the adjective and antonym in the last column. Example for `|gehime|offen|`: `таємний / відкритий`.
- In the right column, write a grammatically correct phrase (but not sentence!) with this adjective plus a noun plus a commonly used verb to help me remember it better. Try to use the existing phrases from the TEXT.
</format>
```




### [[Grammatik in Anki App]]

### [[Überprüfe den Brief - English]]

### [[Text aus Foto extrahieren - English]]

### [[Text to Anki App]]


---

[[Prozess - Deutsch]]
