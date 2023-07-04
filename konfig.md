# Konfigurationsmanagement

#### basiskonzepte

- zusammenarbeit an softwareprojekten 
- continuous integration 
- test automation, build automation, documentation, source code versioning

#### Probleme und Herausforderungen in softwareprojekten

- Different (deployed) Software Versions
    - lösbar mittels versioniersungssoftware wie zb git 

• Bugs, Failures, …
    - buglösbar mit ausreichendem testing
    - zu failures sollte es gar nicht kommen 
• Maintenance
    - leichter wenn dokumentation ordentlich erfolgt ist und gute testcases geschrieben wurden
• Parallel development by many team members
    - versionierung und automatische builds 
• High Quality needed
    - genug zeit lassen und ert updaten wenn fertig
• New features
    - ausreichend testen und in eigenem branch haben bevor integrieren 
• Change Requests by customers / users
    - same wie oben 

Können gelöst werden mittels source code versioning sowie der documentation, test automation und build automation

#### Welche Technologien und Maßnahmen unterstützen sie in der gemeinsamen Zusammenarbeit bei Softwareentwicklungsprojekten?

Zb git bei versionskontrolle
maven zur automatischen generierung der ptrojektstruktur

generell 
README Documentation
• Project Layouts
• Source Code Versioning
• Technical Documentation
• Test Automation
• Build Automation
• Standardization in Build Automation

#### Erklären sie den Begriff continuous integration

Änderungen im Code sollen kontinuierlich und automatisch integriert werden, integration aus verschiedenen entwicklungsquellen um potenzielle konflikte zu finden 

Ein CI Server überwacht die Integration und führt Tests durch, danach erhalten Entwickler Feedback 
Verbessert Code-Qualität

Versionskontrolle: Eine Versionskontrolllösung wie Git oder Subversion ermöglicht die zentrale Verwaltung des Quellcodes und die Nachverfolgung von Änderungen. Jeder Entwickler arbeitet auf Basis einer aktuellen Codeversion und kann seine Änderungen in das Repository hochladen.

Build-Automatisierung: Der Build-Prozess umfasst das Kompilieren des Quellcodes, das Erstellen von ausführbaren Dateien und das Zusammenfügen aller Abhängigkeiten. Automatisierte Build-Tools wie Maven, Gradle oder Ant ermöglichen die Automatisierung dieses Prozesses, um sicherzustellen, dass der Build korrekt und konsistent erfolgt.

Automatisierte Tests: Durch die Erstellung von automatisierten Tests wird sichergestellt, dass der Code fehlerfrei funktioniert und den Anforderungen entspricht. Unit-Tests, Integrationstests und Akzeptanztests sind wichtige Testarten, die in den CI-Prozess integriert werden sollten. Diese Tests werden automatisch ausgeführt, sobald ein Entwickler Codeänderungen hochlädt.

CI-Server: Ein CI-Server wie Jenkins, Travis CI oder CircleCI verwaltet den CI-Prozess. Er überwacht das Versionskontrollsystem auf neue Änderungen, führt den Build-Prozess aus und startet die automatisierten Tests. Der CI-Server gibt Feedback über den Erfolg oder das Scheitern des Build-Prozesses und der Tests.

Kontinuierliche Integration: Der eigentliche Prozess der kontinuierlichen Integration beinhaltet das regelmäßige Zusammenführen von Codeänderungen aus verschiedenen Quellen in das Hauptrepository. Dies geschieht in kurzen Zeitintervallen, idealerweise mehrmals täglich. Durch die häufige Integration wird sichergestellt, dass potenzielle Konflikte und Fehler frühzeitig erkannt und behoben werden.

Rückmeldung und Berichterstattung: Der CI-Prozess sollte den Entwicklern Rückmeldung über den Status ihrer Änderungen geben. Dies kann in Form von Berichten, Benachrichtigungen oder Dashboards erfolgen, die den Erfolg oder das Scheitern von Builds und Tests anzeigen. Dadurch können Entwickler schnell auf Probleme reagieren und Fehler beheben.

##### wie unterstützt maven dabei 

Standardisiertes Build-System: Maven bietet eine standardisierte Projektstruktur und ein Build-System, das die Erstellung von Projekten erleichtert. Es definiert die Konventionen für den Projektordneraufbau und ermöglicht eine konsistente Verwaltung von Abhängigkeiten und Build-Skripten. Dies erleichtert die Integration von Maven-Projekten in den CI-Prozess.

Build-Lebenszyklus: Maven definiert einen Build-Lebenszyklus, der aus einer Reihe von Phasen besteht, die während des Build-Prozesses durchlaufen werden. Diese Phasen umfassen das Kompilieren, Testen, Paketieren und Bereitstellen des Projekts. Durch die Definition und Ausführung dieser Phasen in der richtigen Reihenfolge kann der CI-Server den Build-Prozess automatisieren und die einzelnen Phasen ausführen, um das Projekt zu erstellen.

Abhängigkeitsmanagement: Maven bietet ein leistungsstarkes Abhängigkeitsmanagement, das die Verwaltung von Bibliotheken und externen Abhängigkeiten vereinfacht. Maven ermöglicht die Deklaration von Abhängigkeiten in der Projektkonfiguration (pom.xml) und lädt automatisch die erforderlichen Abhängigkeiten aus einem zentralen Repository herunter. Dadurch werden die Build-Umgebung und die Abhängigkeiten im CI-Prozess automatisch und konsistent verwaltet.

Automatisierte Tests: Maven integriert nahtlos das Test-Framework, z. B. JUnit, und ermöglicht die Definition und Ausführung von automatisierten Tests während des Build-Prozesses. Durch die Integration von Tests in den Build-Prozess kann der CI-Server automatisch Tests ausführen und Feedback über den Erfolg oder das Scheitern der Tests geben. Dies ist entscheidend, um die Codequalität sicherzustellen und potenzielle Fehler frühzeitig zu erkennen.

Plugin-System: Maven bietet ein umfangreiches Plugin-System, das die Integration von zusätzlichen Funktionen und Tools in den Build-Prozess ermöglicht. Es gibt eine Vielzahl von Plugins für verschiedene Aufgaben wie Code-Analyse, Dokumentationserstellung, Code-Qualitätsüberwachung und vieles mehr. Durch die Verwendung von Plugins können CI-Server spezifische Aufgaben im Build-Prozess automatisieren und erweitern.

Zusammenfassend unterstützt Maven Continuous Integration, indem es einen standardisierten Build-Prozess, ein leistungsfähiges Abhängigkeitsmanagement, automatisierte Tests und ein flexibles Plugin-System bietet. Durch die Integration von Maven in den CI-Prozess kann der Build-Prozess automatisiert, konsistent und effizient ausgeführt werden, was zu einer effektiven Continuous Integration beiträgt.

#### Beschreiben Sie den Ablauf von Continuous Integration nach einer fertiggestellten Funktion einer/s SoftwareentwicklerIn

Codeänderungen: Der Entwickler implementiert neue Funktionen oder behebt Fehler im Code und lädt die Änderungen in das Versionskontrollsystem hoch. Es ist wichtig, dass der Entwickler sicherstellt, dass der Code gut getestet und fehlerfrei ist, bevor er hochgeladen wird.

CI-Server-Überwachung: Der CI-Server überwacht das Versionskontrollsystem auf neue Änderungen. Sobald der CI-Server eine Codeänderung erkennt, wird er den Build-Prozess starten.

Build-Prozess: Der CI-Server ruft das Build-Tool (wie Maven) auf, um den Code zu kompilieren, Abhängigkeiten herunterzuladen, Artefakte zu erstellen und gegebenenfalls den Code zu paketieren oder zu deployen. Der Build-Prozess kann auch andere Aufgaben wie Code-Analyse oder Dokumentationserstellung umfassen, je nach den konfigurierten Schritten.

Automatisierte Tests: Nach dem Build-Prozess führt der CI-Server automatisierte Tests aus, um die Qualität des Codes zu überprüfen. Dies umfasst in der Regel Unit-Tests, Integrationstests und gegebenenfalls auch Akzeptanztests. Die Tests werden automatisch ausgeführt, und der CI-Server erfasst die Testergebnisse.

Rückmeldung: Der CI-Server gibt Feedback über den Erfolg oder das Scheitern des Build-Prozesses und der Tests. Dies kann in Form von Berichten, Benachrichtigungen oder Dashboards erfolgen, die den Entwicklern und dem Team den Status des Builds und der Tests anzeigen. Bei erfolgreichem Build und bestandenen Tests kann das Team davon ausgehen, dass die Änderungen funktionieren und mit dem Rest des Codes kompatibel sind.

Konfliktbehandlung: Falls Konflikte oder Fehler während des CI-Prozesses auftreten, wird der CI-Server dies anzeigen. Das Entwicklungsteam muss die Konflikte analysieren und möglicherweise weitere Anpassungen am Code vornehmen, um die Probleme zu beheben. Dies ermöglicht es, Fehler frühzeitig zu erkennen und zu beheben, bevor sie in die Hauptentwicklungszweige integriert werden.

#### wie unterstützt uns git bei der entwicklung neuer funktionen?

erlaubt das arbeiten an verschiedenen features durch branching und zusammenfügen unterschiedlicher codeteile mittels merge

