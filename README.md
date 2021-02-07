# Meine InDesign GREP-Schnipsel

## Für flächendeckendes Suchen/Ersetzen geeignet

### Apostroph korrigieren

Suchen nach: ```~&apos;|~[|´|`|‘```

Ersetzen mit: `’`

### Blindzeilen löschen

Suchen nach: `~b~b+`

Ersetzen mit: `\r`

### Gerade doppelte Anführungszeichen mit Voreinstellung ersetzen

Suchen nach: `~&quot;`

Ersetzen mit: `&quot;`

### Leerraum – Achtelgeviert vor %

Suchen nach: `(?&lt;=\d)‰|(?&lt;=\d)\s‰`

Ersetzen mit: `~&lt;‰`

### Leerraum – FR Achtelgeviert vor doppelten Satzzeichen

Suchen nach: `(?&lt;=\S)\?|(?&lt;=\S)\!|(?&lt;=\S)\;|(?&lt;=\S)\:`

Ersetzen mit: `~&lt;$0`

### Leerraum – FR Achtelgeviert zwischen Anführungszeichen

Suchen nach: `[~{]\s?(.+?)\s?[~}]`

Ersetzen mit: `«~&lt;$1~&lt;»`

### Leerraum – FR Keine Leerzeichen vor doppelten Satzzeichen

Suchen nach: `\s(\?|\!|\;|\:)`

Ersetzen mit: `$1`

### Leerraum – FR Keine Leerzeichen zwischen Anführungszeichen

Suchen nach: `(~{)\s(.*?)\s(~})`

Ersetzen mit: `$1$2$3`

### x mit Multiplikationszeichen ersetzen

Suchen nach: `(?&lt;=\s)x(?=\s)`

Ersetzen mit: `×`

### Zeilenumbruch immer mit Leerzeichen davor

Suchen nach: `(?&lt;=\S)\n`

Ersetzen mit: ` \n`

## Für kontrolliertes Suchen/Ersetzen geeignet

### Bindestrich (bis) zwischen zwei Ziffern durch Halbgeviert ersetzen

Suchen nach: `(\d|\d.)(-|\s-\s)(\d)`

Ersetzen mit: `$1~=$3`

### Dezimalpunkt mit Dezimalkomma ersetzen

Suchen nach: `\.(\d{1,20})\&gt;`

Ersetzen mit: `,$1`

### EN Ordnungszahlen hochgestellt

Suchen nach: `(?&lt;=\d)nd|(?&lt;=\d)st|(?&lt;=\d)th`

Ersetzen mit: `$0`

### FR Ordnungszahlen hochgestellt

Suchen nach: `(?&lt;=\d)ème|(?&lt;=\d)ère|(?&lt;=\d)er|(?&lt;=\d)e`

Ersetzen mit: `$0`

### Leerraum – Achtelgeviert bei Bis-Strich (zwischen Zahlen)

Suchen nach: `(?&lt;=\d)\s~=\s(?=\d)|(?&lt;=\d)\s-\s(?=\d)`

Ersetzen mit: `~&lt;~=~&lt;`

### Leerraum – Datum mit geschütztem Leerzeichen

Suchen nach: `(\d+\.) ([\l\u]+) (\d\d\d\d)`

Ersetzen mit: `$1~S$2~S$3`

### Leerraum – EN Geschütztes Leerzeichen in Gesetzesartikeln

Suchen nach: `(?&lt;=art\.) |(?&lt;=Art\.) |(?&lt;=para\.) |(?&lt;=no\.) |(?&lt;=lit\.) | (?=Cst)`

Ersetzen mit: `~S`

### Leerraum – FR Geschütztes Leerzeichen in Gesetzesartikeln

Suchen nach: `(?&lt;=art\.) |(?&lt;=Art\.) |(?&lt;=al\.) |(?&lt;=ch\.) |(?&lt;=let\.) | (?=Cst\.)`

Ersetzen mit: `~S`

### Leerraum – Geschütztes Leerzeichen nach CHF, Fr. oder fr.

Suchen nach: `(?&lt;=CHF|Fr\.|fr\.) `

Ersetzen mit: `~S`

### Leerraum – Geschütztes Leerzeichen vor abgekürzten Längenmass

Suchen nach: `(?&lt;=\d)(mm|cm|m|km)(?=\s)|(?&lt;=\d)(\s)(mm|cm|m|km)(?=\s)`

Ersetzen mit: `~s$1$3`

### Leerraum – Geschütztes Leerzeichen vor CHF, Fr. oder fr.

Suchen nach: `\s(?=CHF|Fr\.|fr\.)`

Ersetzen mit: `~S`

### Leerraum – IT Geschütztes Leerzeichen in Gesetzesartikeln

Suchen nach: `(?&lt;=art\.) |(?&lt;=Art\.) |(?&lt;=n\.) |(?&lt;=cpv\.) |(?&lt;=lett\.) | (?=Cost\.)`

Ersetzen mit: `~S`

### Minuszahl mit Halbgeviertstrich

Suchen nach: `-(?=\d)`

Ersetzen mit: `–`

### Zahlen gliedern 1 – Bereinigung alte Gliederung

Suchen nach: `(?&lt;=\d)(&apos;|\s)(?=\d{3})`

Ersetzen mit: 

### Zahlen gliedern 2 – Workaround Leerzeichen hinzufügen

Suchen nach: `(\d+)\Z`

Ersetzen mit: `$1~|`

### Zahlen gliedern 3 – ab fünfstelligen Ziffern – mit Achtelgeviert

Suchen nach: `(?&lt;=\d)\d(?=\d{3}\b)|\d(?=(\d{3}){2, }\b)`

Ersetzen mit: `$0~&lt;`

### Zahlen gliedern 3 – ab fünfstelligen Ziffern – mit Zeichenformat Laufweite180

Suchen nach: `(?&lt;=\d)\d(?=\d{3}\b)|\d(?=(\d{3}){2, }\b)`

Ersetzen mit: `$0`

### Zahlen gliedern 4 – Vierstellig in Tabellen – mit Achtelgeviert

Suchen nach: `\d(?=\d{3}\b)`

Ersetzen mit: `$0~&lt;`

### Zahlen gliedern 4 – Vierstellig in Tabellen – mit Zeichenformat Laufweite180

Suchen nach: `\d(?=\d{3}\b)`

Ersetzen mit: `$0`