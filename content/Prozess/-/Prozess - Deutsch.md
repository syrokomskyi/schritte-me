Hier wird beschrieben, den Ablauf, wie man beliebige Seiten aus einem deutschen Buch in deine **Muttersprache** übersetzt. Für **Nomen** werden die Artikel bestimmt. Für **Adjektive** werden ihre Antonyme angegeben, um den Wortschatz zu erweitern.

Du kannst die Anweisungen (siehe unten) nach Belieben ändern.

## Prozess
Öffne ChatGPT.  
Füge ein Foto der Seite in deine Nachricht ein.  
Füge den untenstehenden Prompt ein.  
Wähle das Modell `o1` (wichtig: andere Modelle liefern kein gutes Ergebnis).  
Kopiere das Ergebnis in ein neues Google-Dokument und drucke es (`pdf`).

### Alternativer Prozess
Kopiere das Ergebnis aus ChatGPT nach **Obsidian** (`Strg + Shift + V` in eine Notiz).  
Exportiere es als `pdf` und drucke es aus.

## Prompt
```
v2.0.0

Deutsche Sprache. Übersetzen Sie den Text auf dem Foto (den Fotos) ins Ukrainische.

<extraction>
Extrahiere den Text manuell aus dem Foto.
Lasse den Originaltext ebenfalls stehen.
Löse die Aufgaben nicht.
</extraction>

<format>

<all>
Erstelle eine Tabelle im Markdown-Format. Die erste Spalte enthält den Originaltext. Die zweite Spalte enthält die Übersetzung.
Setze den gesamten Text nicht in Klammern.
Verwende eine neue Zeile anstelle des HTML-Tags `<br/>`.
</all>

<original>
Versuche, das Layout beizubehalten, aber keine Tabellen.
Vermeide es, Fettdruck oder Kursivschrift für den gesamten Satz zu verwenden.
</original>

<translation>
Lasse den Text der Übersetzung im selben Format wie das Original.
Schreibe keine Wortarten des Originals in der Spalte der Übersetzung.
Verwende nicht die Wörter "Original" / "Translation".
Setze jeden Satz, jeden logischen Textblock in eine eigene Zeile der Tabelle.
Teile Textblöcke von mehr als 2 Sätzen in mehrere Zeilen auf.

<noun>
Für jedes Substantiv im Singular gebe den Artikel (der, die, das) in Klammern vor der Übersetzung des Substantivs an. Für Substantive im Plural lasse den Artikel weg.
Für jedes Substantiv im Singular schreibe das gleiche Substantiv im Plural in Klammern nach dem übersetzten Substantiv.
Für jedes Substantiv im Plural schreibe das gleiche Substantiv im Singular in Klammern nach dem übersetzten Substantiv.
</noun>

<adjective>
Für jedes Adjektiv schreibe das Adjektiv und sein Antonym auf Deutsch in Klammern nach dem übersetzten Adjektiv.
</adjective>

</translation>

</format>

<result>
Zeige nur das Ergebnis in Tabellenform mit Überschriften.
Überspringe die Darstellung der Schritte, Einleitungen und Schlussbemerkungen: Gib mir einfach das Ergebnis.
</result>
```

[[Process - English]]
