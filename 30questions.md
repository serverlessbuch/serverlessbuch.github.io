---
layout: page
title: 30 (kritische) Fragen an Serverless Fanboys
permalink: /30questions/
---

Die folgenden 30 Fragen sollte sich jeder stellen, der serverlose Anwendungen bauen und betreiben möchte.
Sie sind bewusst kritisch und vielleicht in Teilen auch provokant formuliert.
Die Fragen sollen nicht vom Einsatz von serverlosen Diensten abhalten, sondern zum intensiven und kritischen Überdenken der einzelnen angesprochenen Punkte anregen, so dass Lösungen gefunden werden können.

Es gibt auf die Fragen keine Standard-Antwort.
Für jeden Anwendungszweck und jedes Szenario sind evtl. andere Antworten passend.
Nur, wer auf so viele wie mögliche Fragen eine Antwort für sein Einsatzszenario findet, ist bestmöglichst auf das Abenteuer _Serverless_ vorbereitet.

Die Fragen stammen im Original aus einem Blog-Post von Sean Hull, welcher mir freundlicherweise erlaubt hat, diese zu übersetzen und in meinem Buch zu verwenden.
Der Originalartikel findet sich unter der URL <a href="http://www.iheavy.com/2017/03/13/30-questions-to-ask-a-serverless-fanboy/" target="_blank">http://www.iheavy.com/2017/03/13/30-questions-to-ask-a-serverless-fanboy/</a>.


#### Security

* Fühlst Du Dich ohne eine Barriere um Deine Datenbank wohl?
* Mehr Services bieten mehr Angriffsfläche. Wie verhinderst Du schadhaften Code?
* Woher weißt Du, dass Dein Cloudanbieter das Thema Sicherheit richtig umsetzt?
* Wie transparent ist Dein Cloudanbieter hinsichtlich Schwachstellen?


#### Testing

* Wie realisierst Du Integration Tests mit mehreren Cloud Services?
* Wie testest Du Deine API Gateway Konfiguration?
* Kannst Du Konfigurationsänderungen des API Gateways über die Versionskontrolle nachvollziehen?
* Können Dir Tools wie CloudFormation oder Terraform dabei helfen?
* Wie führst Du Lasttests mit einer Datenbank, die von einem Drittanbieter stammt, durch?
* Greifen Deine QA Tests auf die Produktions-DB zu?
* Kannst Du einfach neue Test-Datenbanken erstellen und löschen?


#### Management

* Wie realisierst Du Deployments ohne Ausfallzeiten ("zero downtime") mit Lambda?
* Gibt es eine Möglichkeit, Funktionen gruppenweise oder alle auf einmal zu deployen?
* Wie gehst Du mit Vendor Lock-in auf Monitoring und Tool Ebene um? Wie bei Code und anderen Diensten?
* Wie entschärfst Du die Wartungsarbeiten Deines Cloudanbieters? Was ist mit Downtimes und Upgrades?
* Wie planst Du den Wechsel zu einem alternativen Cloudanbieter? Datenbank Im- und Export könnte nicht ideal sein, Code und Infrastruktur muss ggf. dupliziert werden.
* Wie gehst Du mit der Authentifizierung durch einen Drittanbieter um? Was sind die Vor- und Nachteile dabei?
* Was sind die Vor- und Nachteile bei der Verwendung einer Service-basierten Backend-Datenbank?
* Wie gehst Du mit Code-Redundanzen um, wenn jeder Client mit der Backend-Datenbank kommunizieren will bzw. muss?


#### Monitoring & Debugging

* Wie baust Du ein Drittanbieter Monitoring Tool? Wo sind die APIs?
* Wenn Du "down" bist - ist es Deine App oder ist es ein System-weites Problem?
* Wo is das "New Relic" für Lambda?
* Wie setzt Du die Fehlertoleranz (Graceful degredation) bei der Verwendung von mehreren Cloudanbietern um?
* Wie überwachst Du die Ausführungsdauer, so dass Deine Funktion nicht unerwartet ausfällt?
* Wie überwachst Du Deine Account-bezogenen Limits, so dass ein Dev-Deployment nicht die Produktionsumgebung negativ beeinflusst?


#### Performance

* Wie gehst Du mit Latenzen beim Start-up um?
* Wie optimierst Du Deinen Code für mobile Anwendungen?
* Verhindert bei mobilen Anwendungen die Batterielaufzeit eine große Codebasis auf dem Client?
* Wie realisierst Du das Caching auf dem Server, wenn jeder Aufruf alles zurücksetzt?
* Wie erreichst Du ein Connection-Pooling für die Datenbank?
