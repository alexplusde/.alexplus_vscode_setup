# Mein VSCode-Setup für REDAXO CMS

Es gibt bereits einen [Trick bei FOR](https://friendsofredaxo.github.io/tricks/development/editor-vscode) zum Thema VSCode, jedoch habe ich in meinen Projekten einen etwas anderen Aufbau, den ich bevorzuge. Wer als REDAXO-Entwickler sich meinen Workflows anschließen will, wird hier fündig.

## Ziele

1. **Mein Editor soll mich bei der fehlerfreien Entwicklung unterstützen**. Dazu msus der Code lokal vorliegen, um Code-Vorschläge und Überprüfungen machen zu können. Dadurch habe ich eine "Rechtschreib- und Grammatikprüfung" für meinen Code.
2. **Mein Editor soll mir die tägliche Arbeit bei der Entwicklung und Erleichterung beschleunigen**. Auch dafür muss der Code lokal vorliegen. Ich kann darauf aufbauend z.B. GPT-Dienste wie GitHub Copilot nutzen und direkt auf bestimmten Code (z.B. Klassen und Methoden), Dokumentation oder Beispiele von Implementierungen verweisen, um ein genaueres Ergebnis zu erhalten.
3. **Mein Editor soll die Kommandozentrale für mein Projekt sein**. Ich möchte wenig zusätzliche Werkzeuge benutzen müssen und orchestrieren müssen, wenn es auch von Haus aus mit VSCode oder einer Erweiterung funktioniert. Damit schließe ich mich selbst Personen an, die spezifische Ahnung in ihrem Bereich haben und kann deren Werkzeuge und Ergebnisse mit nutzen.

## Grundkonfiguration

1. Ich bin mit meinem GitHub-Account in VSCode angemeldet, um die Konfiguration zwischen mehreren Arbeitsplätzen zu synchronisieren und als "Backup", wenn man das Gerät wechselt.
2. Ich nutze [GitHub Desktop](https://github.com/apps/desktop) als GUI zur Unterstützung bei der Verwaltung von Projekten / Repositories. Alle Projekte, an denen ich arbeite, haben ein (privates) Repository auf GitHub zur Versionierung und Synchronisierung mit Projektpartnern. GitHub Desktop macht es mir einfacher, initial Repositories anzulegen, zu verwalten und im Problemfall via GUI an die Commit-History zu kommen, statt via Terminal / Kommandozeile.
3. Ich nutze [Laragon](https://laragon.org/) unter Windows und empfehle [MAMP Pro](https://www.mamp.info/de/mamp-pro/windows/) für MacOS. Ganz klar: Ich entwickle immer lokal. Und lokal sollten möglichst ähnliche Voraussetzungen zu meinem Projekt vorhanden sein, bspw. dasselbe DBMS (MySQL) und dieselbe PHP-Version (aktuell `8.4`, 23.02.2025).
4. Ein Workspace in VSCode enthält immer das komplette Projektverzeichnis.
5. Durchgehend sicherer Umgang mit Zugangsdaten:
   1. Verbindung zu externen Servern (Upload/Download/Deployment) ausschließlich via SSH, keine Passwörter!
   2. Verwendung eines Passwort-Managers.
   3. Aktivierung von 2FA, wo möglich.
   4. Verwendung von Passkeys anstelle von Passwörtern, wo möglich.

## Essentielle VSCode-Plugins

### Umgang mit Dateiformaten

- `Rainbow CSV`, <https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv> formatiert CSV-Dateien und macht sie lesbar für Menschen.
- `dotlang`, <https://marketplace.visualstudio.com/items?itemName=Nobuwu.dotlang>. Formatiert und prüft `.lang`-Dateien, bei eigenen Projekten und REDAXO-Addons hilfreich.
- `json`, <https://marketplace.visualstudio.com/items?itemName=ZainChen.json>, formatiert und prüft `.json`-Dateien.
- `JsonLint`, <https://marketplace.visualstudio.com/items?itemName=wekex.JsonLint> 
- `Live SASS Compiler`, <https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass> zum Generieren von CSS-Dateien aus SCSS/SASS-Dateien. Ideal, wenn man selbst SCSS/SASS nutzt oder Frameworks wie Boostrap integrieren will.
- `SQL Formatter`, <https://marketplace.visualstudio.com/items?itemName=adpyke.vscode-sql-formatter>, formatiert SQL.
- `YAML`, <https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml>, formatiert und prüft YAML-Dateien nach vorgegebenem Schema, bspw. in `package.yml`-Dateien aus Add-ons und `config.yml` von REDAXO.
- `markdownlint`, <https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint>, formatiert und prüft Markdown-Dateien auf Korrektheit. Markdown wird in REDAXO-Dokumentationen und READMEs benötigt.
  
### Entwicklung mit PHP

- `php cs fixer`, <https://marketplace.visualstudio.com/items?itemName=junstyle.php-cs-fixer>. Code-Style-Fixer. Beim Speichern der Datei(en) oder auf Kommando werden PHP-Dateien in einem einheitlichen standardisierten Format gespeichert. Standards erleichtern es, Code immer gleich zu schreiben und zu formatieren und erhöhen damit langfristig die Lesbarkeit für sich selbst - und für andere, am Projekt beteiligte.
- `PHP Debug`, <https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug>, integriert XDebug, wenn lokal aktiv.
- `PHP Intelliphense`, <https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client>, lernt deinen Projekt Code kennen

### Zusätzliche Editorfunktionen und Kollaboration

- `Live Share`, <https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare>. Gemeinsame Arbeit am Code im selben Workspace. Gibt nicht nur das eigene Projekt frei, sondern den eigenen Editor.

### Zusätzliche VSCode-Plugins

- `German Language Pack`, <https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-de>
- `GitHub Copilot`, <https://marketplace.visualstudio.com/items?itemName=GitHub.copilot> und <https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat> as Assistent
- `Github Markdown Preview`, <https://marketplace.visualstudio.com/items?itemName=bierner.github-markdown-preview>, Vorschau von `.md`-Dateien. Benötige ich, da ich technische Dokumentationen schreibe.
- `Material Icon Theme`, <https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme>, hebt auch innerhalb der Ordnerstrukturen bestimmter Ordner mit bestimmten Namen optisch hervor.
- `PWABuilder Studio`, <https://marketplace.visualstudio.com/items?itemName=PWABuilder.pwa-studio> wird nur im Kontext von Progressive Web App-Entwicklung benötigt.

## VSCode-Plugins, von denen ich Abstand genommen habe.

- `LanguageTool Linter`, <https://marketplace.visualstudio.com/items?itemName=davidlday.languagetool-linter>, Rechtschreibkorrektur für Dateien wie Markdown. Da ist Copilot mittlerweile schneller/zuverlässiger.
- `PHPDoc Generator`, <https://marketplace.visualstudio.com/items?itemName=ronvanderheijden.phpdoc-generator>, unterstützt beim Generieren von PHPDocs-Anmerkungen und Kommentaren. Da ist Copilot m.E. hilfreicher.
- `SFTP`, <https://marketplace.visualstudio.com/items?itemName=Natizyskunk.sftp>, durch den Deployment-Prozess
- `Snippet Manager`, <https://marketplace.visualstudio.com/items?itemName=zjffun.snippetsmanager> - wäre nur sinnvoll, wenn mehr REDAXO-spezifische Snippets in der Community gemeinsam angelegt würden.

## VSCode-Plugins, die ich nicht eingerichtet bekommen habe, aber gerne hätte

- <https://marketplace.visualstudio.com/items?itemName=SanderRonde.phpstan-vscode>
- <https://marketplace.visualstudio.com/items?itemName=st-pham.php-refactor-tool>
- <https://marketplace.visualstudio.com/items?itemName=zobo.php-intellisense>
- <https://marketplace.visualstudio.com/items?itemName=getpsalm.psalm-vscode-plugin>

## Fragen und Antworten

### Warum VSCode und nicht bspw. PHPStorm?

VSCode ist Open Source, wird stetig weiterentwickelt und ist kostenlos.

Ich bin mit PHPStorm nicht warm geworden und froh, die Dinge etwas "einfacher" halten zu können. Außerdem sind VSCode und GitHub sehr angenehm integriert. Die Prozesse mit Git und GitHub, die bspw. YDeploy nutzen, sind hier gut dokumentiert und zu guter Letzt bin ich es inzwischen einfach gewohnt.

### Was ist YDeploy?

Eine Werkzeugsammlung zum [Deployment aus dem Hause Yakamara](https://github.com/yakamara/ydeploy). Grob gesagt hat man damit ein Orchester im Projekt, das lokale Entwicklung und Test- bzw. Live-Instanzen verwaltet und Änderungen an Code und Datenbank in einem vorgefertigten Prozess aktualisiert. Ideal, wenn man nicht an der Live-Seite bis zum Absturz "rumbasteln" will.
