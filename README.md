<!--
author:   Your Name

email:    your@mail.org

version:  0.0.1

language: en

narrator: Deutsch Female

comment:  Try to write a short comment about
          your course, multiline is also okay.

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
          https://d3js.org/d3-random.v2.min.js
          https://d3js.org/d3.v4.min.js
          https://cdn.plot.ly/plotly-latest.min.js
          https://cdn.jsdelivr.net/gh/tinybike/fzero/dist/fzero.min.js
          https://cdn.jsdelivr.net/gh/jquery/jquery/
          http://cdnjs.cloudflare.com/ajax/libs/raphael/2.1.0/raphael-min.js
          https://cdn.jsdelivr.net/gh/LiaTemplates/KekuleJS//kekule/three.js
          https://cdn.jsdelivr.net/gh/LiaTemplates/KekuleJS/kekule/kekule.min.js
link: https://cdn.jsdelivr.net/gh/LiaTemplates/KekuleJS/kekule/themes/default/kekule.css
link: https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.0/animate.min.css

translation: Deutsch  translations/German.md

translation: Français translations/French.md

@eval: @eval_(@uid)

@eval_
<script>
    @input(0);
    @input(1);
    Plotly.newPlot("@0", traces, layout);
</script>

<div id="@0"></div>
@end

@Kekule.molecule3d: @_molecule3d_(@0, @uid)

@_molecule3d_
<div style="text-align: center" id="molecule_parent2_@1"></div>

<script>
const div = document.getElementById("molecule_parent2_@1");

const rawData = `@0`;
const mol = Kekule.IO.loadFormatData(rawData, 'cml');
var viewer = new Kekule.ChemWidget.Viewer(document);

viewer.setDimension('800px', '800px');
viewer.setChemObj(mol);
viewer.setRenderType(Kekule.Render.RendererType.R3D);
viewer.setZoom(1.5);

viewer.setEnableToolbar(true);

div.appendChild(viewer.getElement());
</script>
@end
-->

# “#SemesterHack - Wir hacken das digitale Sommersemester!”

> **Die interaktive Version dieses Kurses können Sie unter [Link](https://liascript.github.io/course/?https://raw.githubusercontent.com/TUBergakademieFreiberg/HackathonChemie/master/README.md#1) einsehen.**
----------------------------------------------


* {|>}{Herzlich Willkommen},
* {|> UK English Male}{Welcome},
* {|> Russian Male}{Добро пожаловать},
* {|> Arabic Female}{اهلا وسهلا},
* {|> French Female}{Bienvenue},
* {|> Chinese Female}{欢迎你}> []

               {{0-1}}
        TU - Freiberg
    |     R R       R R
    |  R         R        R      OOOO  EEEEE  XXXXX
    | R                    R     O  O  E      X   X
    | r                    r     O  O  EEEEE  XXXXX
    |  r                  r      O  O  E      X  X
    |    r              r        OOOO  EEEEE  X   X
    |      r          r
    |        r      r
    |          r  r
    |           r
    +--------------------


## Motivation

    --{{1}}--
Dieser Kurs entstand im Rahmen des [Hackathons](https://hochschulforumdigitalisierung.de/de/online-hackathon)  des Hochschulforums Digitalisierung. Er soll illustrieren, wie die etablierten Labore, die situationsbedingt in diesem Semester nicht genutzt werden können trotzdem für die Studierenden konzeptionell zugänglich gemacht werden sollen.

Der Kurs soll:

     {{1}}
+ als Open Educational Ressoures (OER) bereitgestellt werden und ohne spezifische Software oder Infrastruktur nutzbar sein
+ Templates zur Darstellung von spezifischer Inhalte integrieren
+ die Möglichkeit bieten mit Codeelementen eigene Simulationen zu integrieren.

Daran mitgewirkt haben:

| Name               | Alter | Derzeitig IN |
|:------------------ | ----- | ------------:|
| Andre Dietrich     | 38    |       Berlin |
| Patric Wellershaus | 24    |       Bochum |
| Yannik Höll        | 18    |    Spansberg |
| Philipp Wabnitz    | 29    |      Zwickau |
| Sebastian Zug      | 42    |     Freiberg |
| Ines Aubel         | 37    |     Freiberg |

Ausgangspunkt dafür war ein exisiterender Laborversuch, der den Studierenden die konzeptionelle und praktische Vorgehensweise für die Auslegung einer Rektifikationskolone nahebringt.

# Praktikum zum Modul "Industrielle Chemie"

**Versuch "Rektifikation"**

Diese Unterlagen dienen der Vorbereitung / Begleitung eines Grundlagenversuches in der ....

![Refraktor im Labor der Technischen Chemie (TU Bergakademie Freiberg)](https://raw.githubusercontent.com/TUBergakademieFreiberg/HackathonChemie/master/img/RefraktorTUBAF.png)<!-- width="50%" -->


## Motivation und Begrifflichkeiten

                 {{0-1}}
*******************************************************************************


``` @Kekule.molecule3d
<cml xmlns="http://www.xml-cml.org/schema">
<molecule>
 <atomArray>
  <atom id="a1" elementType="C" x3="-2.887004" y3="-4.726722" z3="0.516350"/>
  <atom id="a2" elementType="C" x3="-2.387966" y3="-3.300634" z3="0.690624"/>
  <atom id="a3" elementType="O" x3="-1.847050" y3="-5.527758" z3="0.028564"/>
  <atom id="a4" elementType="H" x3="-2.225096" y3="-6.440270" z3="-0.065600"/>
  <atom id="a5" elementType="H" x3="-3.228789" y3="-5.109087" z3="1.503693"/>
  <atom id="a6" elementType="H" x3="-3.733566" y3="-4.723567" z3="-0.205585"/>
  <atom id="a7" elementType="H" x3="-1.543512" y3="-3.278000" z3="1.411812"/>
  <atom id="a8" elementType="H" x3="-3.208958" y3="-2.660524" z3="1.077450"/>
  <atom id="a9" elementType="H" x3="-2.044560" y3="-2.895328" z3="-0.284838"/>
 </atomArray>
 <bondArray>
  <bond atomRefs2="a1 a2" order="1"/>
  <bond atomRefs2="a1 a3" order="1"/>
  <bond atomRefs2="a3 a4" order="1"/>
  <bond atomRefs2="a1 a5" order="1"/>
  <bond atomRefs2="a1 a6" order="1"/>
  <bond atomRefs2="a2 a7" order="1"/>
  <bond atomRefs2="a2 a8" order="1"/>
  <bond atomRefs2="a2 a9" order="1"/>
 </bondArray>
</molecule>
</cml>
```

Die Rektifikation, auch als Gegenstromdestillation bezeichnet, ist in der chemischen Technik das bedeutendste thermische Trennverfahren für die Auftrennung homogener Zwei- oder Mehrstoffgemische. Das Trennprinzip beruht dabei auf den unterschiedlichen Siedegleichgewichten der Komponenten und wird in einer Kolonne durch den Stoffaustausch der im Gegenstrom strömenden Phasen intensiviert.
Beispiele hierfür sind die Gewinnung von Kraftstoffen und Basischemikalien aus Erdöl und Erdgas, die Luftzerlegung durch Tieftemperatur-Rektifikation (Linde-Verfahren) oder die großtechnische Herstellung von reinem Ethanol.


Flüssigkeitsgemische, deren einzelne Komponenten eine geringe Siedepunktsdifferenz aufweisen bzw. deren relative Flüchtigkeit sich dem Wert 1 nähert, können destillativ nicht mehr genügend rein getrennt werden. Hieraus würde sich ergeben, dass die Konzentration der leichter siedenden Komponente im Destillat nur geringfügig größer als im Ausgangsgemisch wäre. Abhilfe hierfür schafft die Rektifikation durch mehrfache Gleichgewichtseinstellung zwischen im Gegenstrom zueinander fließender Flüssig- und Dampfphase in der Rektifikationskolonne. Dabei ist eine Unterscheidung in einer kontinuierlichen und diskontinuierlichen Betriebsweise möglich. Die kontinuierliche Rektifikation zeichnet sich durch ein permanentes einspeisen des zu trennenden Gemisches bei Siedetemperatur in dem Mittelteil der Kolonne sowie der kontinuierlichen Entnahme des Kopf- bzw.- Sumpfproduktes aus.

Im Vergleich hierzu wird bei der diskontinuierlichen Rektifikation eine bestimmte Menge an zu trennendem Gemisch vorgelegt und die Rektifikationskolonne angefahren. Nach Einstellen des Gleichgewichtes auf allen Böden bei unendlichen Rücklauf, erfolgt die Entnahme des gewünschten Kopf- bzw. Sumpfproduktes. Dadurch kommt es zu einer Veränderung der Zusammensetzung sowie zu Gleichgewichtsverschiebungen. Entspricht hierbei das gewünschte Produkt nicht mehr den Anforderungen, wird die Rektifikation abgebrochen und eine neue Charge gestartet.

Die Anwendung des Gegenstromprinzips erzielt im Vergleich zur klassischen Destillation eine wesentlich stärkere Anreicherung der niedriger siedenden Komponente im Kopf der Kolonne. Der aus dem Kolonnensumpf aufsteigende Dampf wird mit der aus dem Kondensator zurückfließenden Flüssigkeit auf jedem Boden in intensiven Phasenkontakt gebracht und dieser durch zusätzliche Einbauten weiter verstärkt. Hierbei ist die Unterscheidung in Füllköper- und Bodenkolonnen möglich, die je nach Ausführung für unterschiedliche Trennaufgaben geeignet sind. Das Ziel dieser Einbauten (Füllkörper, Packungen, Glocken-, Sieb- oder Ventilböden) ist die optimale Gestaltung des Stoff- und Wärmetransports in der Kolonne. Auf jedem Boden wird ein Teil des Dampfes kondensiert und gleichzeitig Flüssigkeit verdampft. Aufgrund des sich über die Höhe der Kolonne verändernden Phasengleichgewichts erfolgt eine Anreicherung der Leichtsieder im Verstärkerteil der Kolonne. Dieses ist der oberhalb des Gemischzulaufes befindliche Kolonnenteil. Der Anteil der Schwersieder wächst mit abnehmender Höhe im Abtriebsteil (unterhalb des Zulaufs liegender Kolonnenteil) der Kolonne. Die Phasengleichgewichte auf jedem einzelnen Boden werden maßgeblich durch die Temperatur sowie durch den Druck auf dem jeweiligen Boden bestimmt. Für den Betrieb einer Rektifikationskolonne ist es deshalb erforderlich, dass ein Temperaturgradient über die Kolonnenhöhe erzeugt wird. Dies erfolgt durch die Sumpfheizung und durch den Kondensator im Kopf der Kolonne. Die Auslegung einer technischen Rektifikationskolonne verfolgt immer die Optimierung bezüglich minimaler Gesamtkosten. Voraussetzung derartiger Berechnungen  sind umfangreiche Kenntnisse der Phasengleichgewichte und der Fluiddynamik.

*******************************************************************************

              {{1-2}}
*******************************************************************************


Das war eine Menge Text deshalb wollen wir nun schauen, was bei Ihnen davon hängen geblieben ist.

**Frage 1: Was steckt hinter dem Begriff Rektifikation?**

[( )] Solventextraktion
[(X)] Gegenstromdestillation
[(X)] Kontinuierliche Destillation
[[?]] Denken Sie noch mal genau darüber nach, welche Unterschiede bei der Rektifikation beschreibt der Text?
***************************************************************

                                {{1}}
Richtig, wie im Text oben beschrieben ...

***************************************************************

**Frage 2: Welche Parameter beeinflussen die Rektifikation?**

[( )] Korngrößerverteiung
[(X)] Rücklaufverhältnis
[( )] der Katalysator
[[?]] Denken Sie noch mal genau darüber nach, welche Unterschiede bei der Rektifikation beschreibt der Text?
***************************************************************

                                {{1}}
Richtig, wie im Text oben beschrieben ...

***************************************************************
*******************************************************************************

## Thermodynamische Grundlagen


### Modellierung des Dampfdruckes

| Stoff   | $T_{min}$ | $T_{max}$ | A       | B        | C       |
| ------- | --------- | --------- | ------- | -------- | ------- |
| Benzol  | 8         | 80        | 7.00481 | 1196.76  | 219.161 |
| Ethanol | 20        | 93        | 8.23714 | 1592.864 | 226.184 |
| Wasser  | 1         | 99        | 8.07131 | 1730.63  | 233.426 |

Angewandt auf die zugehörige Gleichung ergibt sich damit folgendes Bild

$$ log(p^\star) =A - \frac{B}{T+C} $$

```javascript  Antoine.js
const substance_0 = "Wasser"
const minTemp_0 = 1       // water data
const maxTemp_0 = 99
const A_0 = 8.07131
const B_0 = 1730.63
const C_0 = 233.426

var temp_0 = d3.range(minTemp_0, maxTemp_0)
var pressure_0 = temp_0.map(T => Math.pow(10, A_0-B_0/(T + C_0)));

const substance_1 = "Ethanol"
const minTemp_1 = 20       // Ethanol data
const maxTemp_1 = 93
const A_1 = 8.23714
const B_1 = 1592.864
const C_1 = 226.184

var temp_1 = d3.range(minTemp_1, maxTemp_1)
var pressure_1 = temp_1.map(T => Math.pow(10, A_1-B_1/(T + C_1)));
```
```js -Visualization.js
console.clear();
var traces = [
  {
    x: temp_0,
    y: pressure_0,
    type: 'scatter',
    name: substance_0,
  },
  {
    x: temp_1,
    y: pressure_1,
    type: 'scatter',
    name: substance_1,
  },
];

var layout = {
    height : 300,
    width :  650,
    yaxis: {
      range: [0, Math.max(pressure_0)],
      title: {
        text: 'pressure [hPa]',
      },
    },
    xaxis: {
      title: {
        text: 'Temperatur [Grad Celsius]',
      },
    },
    margin: { l: 60, r: 10, b: 35, t: 10, pad: 4},
    showlegend: true,
    legend: { x: 1, xanchor: 'right', y: 0},
    tracetoggle: false
};
```
@eval


### Modellierung des Siedepunktes

Ausgehend vom Raoult'sche Gesetz können wir einen Zusammenhang zwischen den Graphen des Dampfdrucks über der Zusammensetzung bei konstanter Temperatur ableiten.

> **Beachten Sie:** Die Berechnung nach dem Raoult'schen Gesetz ist eine Annäherung!. Die meisten realen Gemische zeigen ein stärker nach oben oder unten abweichendes Verhalten.


```javascript  Raoult.js
const T = 50

const substance_a = "Wasser"
const minTemp_a = 1       // water data
const maxTemp_a = 99
const A_a = 8.07131
const B_a = 1730.63
const C_a = 233.426
var p_a =  Math.pow(10, A_a-B_a/(T + C_a))

const substance_b = "Ethanol"
const minTemp_b = 20       // Ethanol data
const maxTemp_b = 93
const A_b = 8.23714
const B_b = 1592.864
const C_b = 226.184
var p_b =  Math.pow(10, A_b-B_b/(T + C_b))

var moleFraction = [0,1];
var booling_a = [0, p_a,]
var booling_b = [p_b, 0]
var mixture = [p_b, p_a]
```
```js -Visualization.js
var traces = [
  {
    x: moleFraction,
    y: booling_a,
    type: 'scatter',
    name: substance_a,
  },
  {
    x: moleFraction,
    y: booling_b,
    type: 'scatter',
    name: substance_b,
  },
  {
    x: moleFraction,
    y: mixture,
    type: 'scatter',
    name: "mixture",
  },
];

var layout = {
    height : 300,
    width :  650,
    yaxis: {
      range: [0, Math.max([p_a, p_b])],
      title: {
        text: 'pressure [hPa]',
      },
    },
    xaxis: {
      title: {
        text: 'relativer Anteil von xa',
      },
    },
    margin: { l: 60, r: 10, b: 35, t: 10, pad: 4},
    showlegend: true,
    legend: { x: 1, xanchor: 'right', y: 0},
    tracetoggle: false
};
```
@eval

Welches reale Verhalten erwarten Sie für die Wasser / Ethanol-Kombination?


## Auslegung der Rektifikationskolone

Für die Beurteilung der Rektifikationskolonne mit ihren Einbauten in Bezug auf ein spezielles Trennproblem ist es wichtig, die betriebstechnisch relevanten Parameter zu identifizieren und hinsichtlich ihrer Auswirkung auf die Trennleistung der Kolonne einzuschätzen. Im Folgenden werden die wichtigsten Betriebsparameter einer Rektifikationskolonne kurz aufgeführt und erläutert.

![images](https://raw.githubusercontent.com/TUBergakademieFreiberg/HackathonChemie/master/img/Rektifikation.jpeg)<!-- width="80%" -->
