We can import the grammatic from any text to Anki Desktop - https://apps.ankiweb.net

Attach the text (see `txt` folders) to this prompt.
Good model: `ChatGPT o3`.

Use `Ctrl + Shift + V` to paste the result from AI 🤖 into an Obsidian note: this will preserve the formatting.

See also [[Vorbessern Wortschatz in Anki App]], [[Organisieren von Sprachlerndecks in Anki - Ukrainisch]], and [[Grammatik in Anki App]].

```
v1.12.0

The German language. Gather all parts of speech and Funktionsverbgefüge (Nomen-Verb-Verbindung) from the TEXT.

<all>
Processing the whole text, regardless of formatting, sections, and tables. 

Respond with HTML-tagged-text in Markdown code block following to examples (see here and below):
'''txt
Face card on German;Back card with grammatic, examples, and translations
'''

Accepted HTML-tag is `<br>` only.

NO programmatic generation or tool usage.
Do not use any code to generate the table.
Do not use Python, pandas, or any code-related tools.
Just output a plain Markdown table as formatted text in the reply.
Do not enclose the entire text in brackets.
Avoid using bold or italic for the entire sentence.
Avoid using the `;` character in sentences.
Use a space instead of a non-breaking space, `&nbsp;`, or tab.
</all>

<chunks>
Continue processing until all chunks are processed.
</chunks>

<validation>
For every TEXT sentence or word:
- Identify at least one parts of speech and/or Funktionsverbgefüge (Nomen-Verb-Verbindung) except excluded ones if they are present.
- Do not skip lines.

For every result line:
- Each line must contain only one character `;`.
</validation>

<compatibility>
Prefer compact answers.
</compatibility>


<extraction>

Write up an example sentence with each identified part of speech and/or Funktionsverbgefüge (Nomen-Verb-Verbindung).
Add a Ukrainian translation to all examples.
Don't explicitly state that it's a translation: just do it.

<nomen_verb_verbindung>
Identify Funktionsverbgefüge (Nomen-Verb-Verbindung).
Translate this stable expression into Ukrainian according to its meaning.

<example>
eine Entscheidung treffen;Ich muss heute eine Entscheidung treffen.<br><br>ухвалювати рішення<br><br>Я маю прийняти рішення сьогодні.
</example>

</nomen_verb_verbindung>


<any_verb>
Make each verb into a verb with 2-3 of the most commonly used prepositions.
If a verb can be used without a preposition, write it without a preposition also without any comment.
Note how the case of the noun changes for each verb you created above (with and without a preposition). 

For each verb, except the ones in section `<exclude>` (see below), write the verb in German (Infinitive), its Präsens form for `er/sie/es`, its Präteritum form for `er/sie/es`, its Perfekt form (with `hat` oder `ist`) in German and markers `A` - for Akkusativ verb, `D` - for Dativ verb, `A+D` - for Akkusativ and Dativ verb.
</any_verb>


<separable_verb>
Identify separable (trenbare) verbs.
Also identify the stem of the verb without a prefix and the translation of this stem.

<example>
aufhören mit;mit + D<br><br>hört auf<br>hat aufgehört<br>hörte auf<br><br>Ich höre jetzt mit dieser Arbeit auf!<br><br>припиняти<br><br>Я припиняю зараз цю роботу!<br><br>hören - слухати
</example>
</separable_verb>


<reflexive_verb>
Identify reflexive verbs.
Add `sich` before each reflexive verb.

<example>
sich beeilen;A<br><br>beeilt sich<br>hat sich beeilt<br>beeilte sich<br><br>Bitte beeilte dich, wir sind spät dran.<br><br>поспішати<br><br>Будь ласка, поспішай, ми спізнюємось.
</example>
</reflexive_verb>


<normal_verb>
Identify normal verbs.

<exclude>
all modal verbs
habe, hast, hat, haben, habt
sehen
sein, bist, ist, sind, seid
war, warst, wart, waren
werde, werden
wurde, wurdst, wurden
</exclude>

<example>
halten;A<br><br>hält<br>hat gehalten<br>hielt<br><br>Kannst du die Tasche halten?<br><br>поспішати<br><br>Чи можеш ти потримати сумку?
</example>
</normal_verb>


<noun>
Identify nouns.

For each noun, except the ones in section `<exclude>` (see below), write the noun in German (Singular) with articel and its plural form without articel.

Leave the noun without an article on the front of the card.

Also write one or two commonly used verbs with this noun and add sentences with this verbs. For example, verbs for `der Termin`: `erneren, stornieren`. 

<exclude>
Bruder
Haus
Mother
Oma
Opa
Vater
</exclude>

<example>
Termin;der<br><br>Termine<br><br>Ich erinnere mich an den Termin.<br><br>зустріч<br><br>Я пам'ятаю дату.
</example>
</noun>


<adjective>
Identify adjectives.

For each adjective, except the ones in section `<exclude>` (see below), write the adjective in German and its antonym.

<exclude>
alt
neu
</exclude>

<example>
schön;hässlich<br><br>Das Wetter heute ist schön.<br><br>гарний / потворний<br><br>Сьогодні гарна погода.
</example>
</adjective>


<other>
Identify other parts of speech.

<example>
wie;Wie ist das Wetter heute?<br><br>яка<br><br>Яка сьогодні погода?
</example>
</other>


</extraction>


<test>
Ensure that the sentence "Der kleine Hund läuft schnell." has been identified:
- laufen
- der Hund
- klein
- schnell
</test>

---

# TEXT


```
