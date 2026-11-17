# CANUSSA – Süsses von Kindern

Kleiner Onlineshop für selbst gemachte Süssigkeiten, von Kindern geführt.
Alles steckt in **einer einzigen Datei** (`index.html`): kein Build, kein Server, keine Datenbank.

## Funktionen

- Sortiment mit Mengenwahl (Caramellisierte Haselnuss-Bonbons, Caramel-Lollipops)
- Caramel-Popcorn als «bald verfügbar» (Bestell-Buttons deaktiviert)
- Warenkorb nur im Arbeitsspeicher des Browsers (nichts wird gespeichert)
- Bestellung per E-Mail: Der Shop öffnet das Mailprogramm mit fertigem Bestelltext (`mailto:`). Falls das nicht klappt, kann der Text kopiert werden.
- Lieferung nur in Winterthur Hegi (Adresse ist Pflichtfeld, keine Abholung)
- Während der Winterthurer Schulferien: Bestellteil ausgeblendet, Hinweis oben auf der Seite
- Hell- und Dunkelmodus, für Handy und Desktop optimiert

## Veröffentlichen mit GitHub Pages

1. Neues Repository auf GitHub anlegen (z. B. `canussa`).
2. Alle Dateien dieses Ordners hochladen (`index.html`, `README.md`, `.nojekyll`).
3. Im Repository **Settings → Pages** öffnen.
4. Bei **Build and deployment** → *Source*: **Deploy from a branch** wählen.
5. Branch `main` und Ordner `/ (root)` wählen, speichern.
6. Nach ein bis zwei Minuten ist der Shop erreichbar unter
   `https://<github-benutzername>.github.io/<repository-name>/`

Änderungen: `index.html` bearbeiten und committen. Pages veröffentlicht automatisch neu.

## Anpassen

Alle Einstellungen stehen am Anfang des `<script>`-Blocks in `index.html`.

| Was | Wo | Beispiel |
|---|---|---|
| E-Mail für Bestellungen | `SHOP_EMAIL` | `"canussa@outlook.com"` |
| Sortiment, Preise | `PRODUCTS` | `{id:"lolli", name:"…", desc:"…", price:1.5, unit:"Stück"}` |
| Maximale Menge pro Artikel | `MAX` | `20` |
| Schulferien | `SCHULFERIEN` | `["2026-12-19","2027-01-03"]` (erster und letzter Ferientag) |
| Ferienmodus testen | `TEST_DATUM` | `"2026-12-24"` (wieder `null` setzen!) |

### Neues Produkt hinzufügen

1. Eintrag in `PRODUCTS` ergänzen. Mit `soon:true` und `price:0` erscheint es als «bald verfügbar» mit deaktivierten Buttons. Sobald es verkauft wird, `soon:true` entfernen und den Preis setzen.
2. Eine Zeichnung als `<symbol id="…" viewBox="0 0 100 100">` im SVG-Block am Anfang der Datei anlegen. Die `id` muss mit der `id` des Produkts übereinstimmen.

### Hintergrundfarbe

Im CSS bei `body{… background:#4169e1; …}` (Royal Blue).

## Schulferien

Die Termine stammen aus dem Schulferienplan der Stadt Winterthur 2025–2033 (Stand 2022, Änderungen vorbehalten). Bitte gelegentlich mit dem aktuellen Plan der Stadt Winterthur vergleichen und `SCHULFERIEN` anpassen. Berücksichtigt sind nur die Ferien, keine einzelnen Feiertage oder Brückentage. Das Datum wird in der Zeitzone Europe/Zurich anhand der Geräteuhr des Besuchers geprüft. Wer die Uhr verstellt, sieht den Bestellteil trotzdem. Das ist bei diesem kleinen Shop kein Problem.

## Gut zu wissen

- **Keine Speicherung:** Bestellungen laufen nur über die E-Mail der Kundin oder des Kunden. Der Shop selbst speichert nichts. Eine Bestellung gilt erst, wenn die E-Mail abgeschickt wurde.
- **E-Mail-Adresse ist öffentlich:** Sie steht im Quelltext einer öffentlichen Seite und kann von Spam-Robotern gelesen werden.
- **Schrift:** Die Handschrift «Patrick Hand» wird von Google Fonts geladen. Ohne Internet greift eine Ersatzschrift.
- **Allergiehinweis:** Der Hinweis zu Nüssen und Milch steht unten auf der Seite. Bitte bei Rezeptänderungen anpassen.
- **Aufsicht:** Kinder sollten Caramel nur zusammen mit Erwachsenen kochen und Lieferungen in der Nachbarschaft absprechen.
