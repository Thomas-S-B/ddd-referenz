# I. Das Modell zum Einsatz bringen

Domain-driven Design ist ein Ansatz für die Entwicklung komplexer
Software, bei dem wir:

1. Uns auf die [Core Domain](#core-domain) konzentrieren.

2. [Modelle](#model) in einer kreativen Zusammenarbeit von
   Domänen-Praktikern und Software-Praktikern erkunden.

3. Eine [Ubiquitous Language](#ubiquitous-language) in einem
   expliziten [Bounded Context](#bounded-context) sprechen.

Diese Zusammenfassung von DDD in drei Punkten stützt sich auf die
Definition der Begriffe, die in dieser Broschüre definiert sind.

Viele Projekte betreiben Modellierung, ohne am Ende einen echten Nutzen
zu erzielen. Die Muster von DDD stellen erfolgreiche Praktiken aus
Projekten dar, bei denen die Modellierung bedeutende Vorteile gebracht
hat. Zusammen angewendet stellen sie eine ganz andere Herangehensweise an
Modellierung und Softwareentwicklung vor, die von kleinen Details
bis hin zur übergreifenden Vision reicht. Starre Konventionen für die
Modellierung müssen gegen freies Erforschen von
Modellen in Zusammenarbeit mit nicht-technischen Personen abgewogen werden.
Für einen Erfolg müssen Taktik und Strategie kombiniert werden;
DDD befasst sich sowohl mit taktischem als auch mit strategischem
Design.

## Bounded Context {#bounded-context}

*Dt.: Begrenzter Kontext*

*Bei jedem großen Projekt sind mehrere Modelle im Spiel.* Sie
entstehen aus vielen Gründen. Zwei Subsysteme bedienen in der Regel
sehr unterschiedliche Benutzergruppen, mit unterschiedlichen Aufgaben,
für die unterschiedliche Modelle sinnvoll sein können. Voneinander unabhängig
arbeitende Teams lösen möglicherweise das gleiche Problem auf andere Weise, weil sie nicht miteinander kommunizieren. Auch die Werkzeuge im Einsatz sind vielleicht unterschiedlich, so dass Programmcode nicht gemeinsam genutzt werden kann.

Die Präsenz mehrerer Modelle ist unvermeidlich, aber wenn Code, der auf
verschiedenen Modellen basiert, kombiniert wird, wird Software
fehlerhaft, unzuverlässig und schwer verständlich und die Kommunikation
zwischen den Teammitgliedern konfus. Oft ist unklar, in
welchem Zusammenhang ein Modell nicht angewendet werden soll.

Ausdrücke aus dem Modell haben, wie jede andere Formulierung auch,
nur im [Kontext](#context) eine Bedeutung.

Daher:

**Definiere explizit den Kontext, in dem ein Modell Anwendung findet.
Lege explizit die Grenzen bezüglich Teamorganisation, Verwendung
innerhalb bestimmter Teile der Anwendung und
physischen Umsetzungen wie Codebasen und Datenbankschemata fest. Wende
[Continuous Integration](#continuous-integration) an, um
Modellkonzepte und -begriffe innerhalb dieser Grenzen strikt konsistent
zu halten, lass dich aber nicht von
Problemen außerhalb ablenken oder verwirren. Standardisiere
einen einzigen Entwicklungsprozess innerhalb des Kontextes, der
anderswo nicht verwendet werden muss.**

## Ubiquitous Language {#ubiquitous-language}

*Dt.: allgegenwärtige Sprache*

Zuerst schreibst du einen Satz,  
Und dann hackst du ihn klein;  
Dann mische die Stücke und ordne sie so an  
wie sie zufällig gefallen sind:  
Die Reihenfolge der Ausdrücke macht  
überhaupt keinen Unterschied.  

--- Lewis Carroll, "Poeta Fit, Non Nascitur"

Um ein Design zu schaffen, das flexibel und reich an Wissen ist,
bedarf es einer vielseitigen, gemeinsam im Team genutzten Sprache und
lebhaftem Experimentieren mit der Sprache, wie es in
Softwareprojekten selten vorkommt.

Innerhalb eines einzigen [Bounded Context](#bounded-context) kann die
Sprache so
kaputt sein, dass sie die Bemühungen um eine anspruchsvolle
Modellierung untergräbt.  Wenn das Modell nur dazu dient,
UML-Diagramme für die Techniker im Team zu erstellen, dann trägt es
nicht zur kreativen Zusammenarbeit, dem Kern von DDD, bei.

Domänenexperten verwenden ihren Fachjargon, während die Techniker im
Team ihre eigene Sprache haben, um über die Domäne hinsichtlich Design
zu diskutieren. Die Terminologie in den täglichen Diskussionen ist getrennt von
der im Code verwendeten (letztendlich dem
wichtigsten Produkt eines Softwareprojekts). Und selbst die gleiche
Person verwendet unterschiedliche Sprachen in Wort und Schrift, so
dass die prägnantesten Ausdrücke der Domäne oft in einer flüchtigen
Form entstehen, die nie im Code oder auch nur schriftlich erfasst wird.

Übersetzung stört die Kommunikation und macht das Erarbeiten des
Wissens blutleer.

Doch keiner dieser Dialekte kann eine gemeinsame Sprache werden, weil
keiner alle Bedürfnisse erfüllt.

Domänenexperten sollten gegen Begriffe oder Strukturen protestieren,
die ungeschickt oder unzureichend sind, um das Domänenverständnis zu
vermitteln; Entwickler sollten auf Mehrdeutigkeit oder Inkonsistenz
achten, die das Design stören.

Spielt mit dem Modell, während ihr über das System sprecht. Beschreibt
Szenarien *laut* mit Hilfe der Elemente und Interaktionen aus dem Modell
und kombiniert dabei Konzepte so, wie es das Modell erlaubt. Findet
einfachere Wege, um zu sagen, was ihr sagen wollt, und übertragt diese
neuen Ideen dann wieder zurück in die Diagramme und den Code.

Mit einer [Ubiquitous Language](#ubiquitous-language) ist das Modell
nicht nur ein
Design-Artefakt. Es wird zu einem integralen Bestandteil von allem,
was die Entwickler und Fachexperten gemeinsam tun.

Daher:

**Verwende das Modell als Rückgrat einer Sprache. Verpflichte das Team
dazu,
diese Sprache unermüdlich in der gesamten Kommunikation innerhalb des
Teams und im Code anzuwenden. Verwende in einem [Bounded
Context](#bounded-context) die
gleiche Sprache in Diagrammen, beim Schreiben und insbesondere beim
Sprechen.**

**Begreife, dass eine Änderung der Sprache eine Änderung des
Modells
ist.**

**Beseitige Schwierigkeiten, indem du mit alternativen Ausdrücken
experimentierst, die alternative Modelle widerspiegeln. Dann
überarbeite den Code und benenne Klassen, Methoden und Module um, so
dass sie
dem neuen Modell entsprechen. Löse Verwirrung über Begriffe in einem
Gespräch auf, und zwar in der Art und Weise, wie wir uns über die
Bedeutung gewöhnlicher Wörter einigen.**

## Continuous Integration {#continuous-integration}

*Sobald ein Bounded Context definiert ist, müssen wir ihn intakt
 halten.*

Wenn mehrere Personen am gleichen [Bounded Context](#bounded-context)
arbeiten, besteht
eine starke Tendenz dazu, dass das Modell fragmentiert wird. Je
größer das
Team, desto größer das Problem, aber schon drei oder vier Personen
können auf ernsthafte Probleme stoßen. Doch die Zerlegung des Systems
in immer kleinere [Bounded Contexts](#bounded-context) führt
letztendlich dazu, das sie
kein ausreichendes Maß an Integration und Kohärenz mehr haben.

Daher:

**Etabliere einen Prozess, bei dem alle Code- und alle andere
  Implementierungsartefakte regelmäßig zusammengeführt werden, und nutze
  automatisierte Tests, um Fragmentierungen schnell zu finden. Wende
  ständig die [Ubiquitous Language](#ubiquitous-language) an, um
  eine gemeinsame Sicht auf das Modell auszuarbeiten, während sich die
  Konzepte in den Köpfen der verschiedenen beteiligten Personen
  weiterentwickeln.**

## Model-driven Design {#model-driven-design}

*Dt.: modellgetriebener Entwurf*

*Die enge Verknüpfung des Codes mit einem zugrunde liegenden Modell
gibt dem Code einen Sinn und macht das Modell relevant.*

Wenn das Design oder zumindest ein zentraler Teil davon nicht auf das
Domänenmodell abgebildet werden kann, hat dieses Modell nur einen
geringen
Wert, und die Korrektheit der Software ist fraglich. Gleichzeitig
sind komplexe Abbildungen zwischen Modellen und den Funktionen
des Designs schwer verständlich und in der Praxis nicht
wartbar, sobald sich das Design ändert. Eine tödliche Kluft
öffnet sich zwischen Analyse und Design, so dass die in den beiden
Aktivitäten gewonnenen Erkenntnisse nicht in die jeweils andere
einfließen.

Leite aus dem Modell die beim Design verwendete Terminologie und die
grundlegende Zuordnung von Verantwortlichkeiten ab. Der Code wird zu
einem Ausdruck des Modells, so dass eine Änderung des Codes eine
Änderung des Modells bedeuten kann. Seine Wirkung muss sich entsprechend
auf den Rest der Projektarbeit auswirken.

Um die Implementierung eng an ein Modell zu binden, sind in der
Regel Softwareentwicklungswerkzeuge und -sprachen erforderlich, die
ein solches Modellierungsparadigma unterstützen, wie beispielsweise die
objekt-orientierte Programmierung.

Daher:

**Entwirf einen Teil des Softwaresystems so, dass es das
Domänenmodell möglichst genau widerspiegelt, so dass die
Umsetzung offensichtlich ist. Betrachte das Modell immer wieder und
modifiziere es, um es natürlicher in Software zu implementieren, sogar während du versuchst, das Modell den tieferen Einblick in die Domäne besser reflektieren zu lassen.
Erhebe den Anspruch, ein einziges Modell zu finden, das beiden Zwecken
gerecht wird und
zudem eine flüssige [Ubiquitous Language](#ubiquitous-language)
unterstützt.**

## Hands-on Modelers {#hands-on-modelers}

*Dt.: Praktizierende Modellierer*

Wenn sich die Personen, die den Code schreiben, nicht für das Modell
verantwortlich fühlen oder nicht verstehen, wie das Modell für eine
Anwendung funktionieren soll, dann hat das Modell mit der
Software nichts zu tun. Wenn Entwickler nicht erkennen, dass Code-Änderungen
das Modell verändern, dann wird ihr Refactoring das Modell eher
schwächen als stärken. Wenn ein Modellierer vom
Implementierungsprozess getrennt ist, gewinnt er oder sie nie ein
Gefühl für
die Restriktionen bei der Implementierung oder verliert dieses schnell.
Die grundlegende Bedingung des [Model-driven
Designs](#model-driven-design) - dass
das Modell eine effektive Implementierung unterstützt und wichtige
Erkenntnisse über die Domäne abstrahiert - geht dadurch nahezu verloren
und die daraus
resultierenden Modelle werden unpraktisch sein. Schließlich werden die
Kenntnisse und Fähigkeiten erfahrener Designer nicht auf andere
Entwickler übertragen, wenn die Arbeitsteilung die Art der
Zusammenarbeit verhindert, welche die Feinheiten der Programmierung
eines modellgetriebenen Entwurfs vermittelt.

Daher:

**Jede technische Person, die am Modell mitwirkt, muss einige Zeit
damit verbringen, am Code zu arbeiten, unabhängig davon, welche
Rolle sie im Projekt primär hat. Alle, die für das Ändern von
Code verantwortlich sind, müssen lernen, ein Modell durch Code
auszudrücken. Jeder Entwickler muss auf der einen oder anderen Ebene an
der Diskussion über das Modell beteiligt sein und Kontakt zu
Domänenexperten haben. Diejenigen, die auf andere Weisen zum Projekt
beitragen, müssen diejenigen, die am Code arbeiten, bewusst in einen
dynamischen Austausch von Ideen zum Modell mithilfe der [Ubiquitous
Language](#ubiquitous-language) einbeziehen.**

## Refactoring Toward Deeper Insight {#refactoring-toward-deeper-insight}

*Dt.: Refactoring zum tieferen Verständnis*

Die Verwendung eines bewährten Satzes von Grundbausteinen zusammen mit
einer konsistenten Sprache bringt ein wenig Vernunft in die
Entwicklungsarbeit. Aber es bleibt eine Herausforderung, tatsächlich
ein prägnantes Modell zu finden, das die subtilen Belange der
Fachexperten aufgreift und ein praktisches Design vorantreiben kann.
Ein Modell, welches das Oberflächliche abstreift und das Wesentliche
erfasst, ist ein tiefgreifendes Modell. Dadurch sollte die Software
der Denkweise der Domänenexperten besser entsprechen und besser auf die
Bedürfnisse der Benutzer eingehen.

Traditionell wird Refactoring als Code-Transformation aus technischen
Gründen beschrieben. Refactoring kann aber auch durch einen tieferen
Einblick in die Domäne und eine entsprechende Verfeinerung des Modells
oder dessen Ausdruck im Code motiviert werden.

Anspruchsvolle Domänenmodelle erweisen sich selten als nützlich, außer
wenn sie durch einen iterativen Prozess mit Refactoring entwickelt
werden, in der engen Zusammenarbeit von Domänenexperten mit
Entwicklern, die daran interessiert sind, etwas über die Domäne zu
erfahren.
