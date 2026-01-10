We can import the transformed grammatic to Anki Desktop - https://apps.ankiweb.net

Attach the tables with title (see `Grammatik` above) to this prompt.

Good models: `Claude 3.7`, `ChatGPT`.

See also [[Vorbessern Wortschatz in Anki App]], [[Organisieren von Sprachlerndecks in Anki - Ukrainisch]], and [[Text to Anki App]].

## Transform from Grammatik tables

```
v1.3.0

Transform the attached tables into this format:

<example>
## Verb
|abbezahlen|bezahlte ab|hat abbezahlt|A|виплатити повністю|bezahlen платити|
...

## Nomen
|🏷️die Abbuchung|Abbuchungen|списання|prüfen, erklären|
...

## Adjektiv
|alt|neu|старий / новий|alte Kontonummer prüfen|
...
</example>

should be trasformed to

<format>
abbezahlen;bezahlte ab<br/>hat abbezahlt<br/>A<br/><br/>виплатити повністю<br/><br/>bezahlen платити;Verb
...
Abbuchung;die<br/><br/>Abbuchungen<br/><br/>списання<br/><br/>prüfen, erklären<br/>Nomen
...
alt;neu<br/>старий / новий<br/><br/>alte Kontonummer prüfen<br/>Adjektiv
</format>

Use the above as an example: there may be other categories in the actual table below.
```
