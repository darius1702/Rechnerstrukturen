---
title: Zusammenfassung Rechnerstrukturen
author: Darius Schefer
date: 15.03.2023
geometry: margin=2cm
output: pdf_document
---
# Random
### TBD
- Zuverlässigkeit
- Fähigkeit eines Systems, während einer vorgegebenen Zeitdauer bei zulässigen Betriebsbedingungen die spezifiezierte Funktion zu erbringen

- Fehlertoleranz (fault tolerance)
    - System kann spezifiezierte Funktion auch auch mit begrenzter Anzahl fehlerhafter Subsysteme erbringen
    - Redundante Komponenten

# Mathe
#### Wafer Fläche
- $A_{\text{wafer}} = \pi\cdot(\frac{d_{wafer}}{2})^2$

#### Dies per wafer
- $\text{DPW} = \frac{A_{\text{wafer}}}{A_{\text{die}}} - \frac{\pi \cdot d_{\text{wafer}}}{\sqrt{2 \cdot A_{\text{die}}}}$
    - theoretisches Maximum - Verschnitt

#### Die Yield
- $Y_{\text{die}} = Y_{\text{wafer}}\cdot(\frac{1}{1+\text{DPUA}\cdot A_{\text{die}}})$
    - Wafer Yield: $Y_{\text{wafer}}$

#### Kosten pro Die
- $\text{cost}_{\text{die}} = \frac{\text{cost}_{\text{wafer}}}{\text{DPW} \cdot Y_{\text{die}}}$

#### IC-Kosten
- $\text{cost}_{\text{IC}} = \frac{\text{cost}_{\text{die}} + \text{cost}_{\text{dies-test}} + \text{cost}_{\text{packaging}}}{Y_{\text{final}}}$

# Maßzahlen

#### MTTF (mean time to failure)
- auch $E(L)$ (mittlere Lebensdauer)
- Erwartungswert der Lebensdauer bis zum ersten Fehler eines zu beginn fehlerfreien Systems

#### MTTR (mean time to repair)
- auch $E(B)$ (mittlere Behandlungsdauer)

#### MTBF (mean time between failures)
- mittlere Zeitdauer zwischen zwei Ausfällen
- MTBF = MTTF + MTTR

#### Überlebenswahrscheinlichkeit
- $R(t)$
- Mit welcher Wahrscheinlichkeit bleibt das System bis Zeitpunkt t fehlerfrei

#### Verfügbarkeit
- $v = \frac{\text{MTTF}}{\text{MTTF} + \text{MTTR}} = \frac{\text{MTTF}}{\text{MTBF}} = \frac{E(L)}{E(L) + B(L)}$
- Wahrscheinlichkeit, das System zu einem beliebigen Zeitpunkt fehlerfrei anzutreffen

#### FIT (failures in time)
- Ausfallrate, Komplement zu MTTF
- Ausfälle pro $10^9$ Stunden

#### Leistungsaufnahme
- $P_{\text{total}} = P_{\text{switching}} + P_{\text{shortcircuit}} + P_{\text{static}} + P_{\text{leakage}}$
- Dynamischer Leistungsverbrauch:
    - switching: Laden oder Schalten von kapazitiver Last
    - shortcircuit: Übergang bei CMOS-Gatter, wenn sich Eingänge ändern
- Statischer Leistungsverbrauch:
    - static: konzeptuell nicht bei CMOS
    - leakage: Kriechströme (wachsen mit Integrationsdichte!)
- $P \sim V^2 \cdot f$
    - $P \sim V^3, P \sim f^3$ bei simultaner Änderung

# Schaltwahrscheinlichkeit
- $\mathbb{P}_{\text{Schalt}} = \mathbb{P}(0 \rightarrow 1 \vee 1 \rightarrow 0) = 2 \cdot \mathbb{P}(1) \cdot (1 - \mathbb{P}(1))$
- berechne $\mathbb{P}(1)$ pro Gatter

# Mehr Mathe
### Ausführungszeit
- $t_{\text{exe}} = \text{I} \cdot \text{CPI} \cdot f$
    - $\text{I}$: Anzahl Instruktionen
    - $\text{CPI}$: Cycles per instruction
    - $f$: Taktfrequenz
- Instructions per cycle: $\text{IPC} = \frac{1}{\text{CPI}}$

#### MIPS
- Millions of instructions per second
- $\text{MIPS} = \frac{\text{Ausgeführte Instruktionen}}{10^6 \cdot \text{Ausführungszeit}}$

#### MFLOPS
- Millions of floting point operations per second
- $\text{MFLOPS} = \frac{\text{Ausgeführte fp-Instruktionen}}{10^6 \cdot \text{Ausführungszeit}}$

# Benchmarking
#### SPECratio
- $\text{SPEC}_{\text{ratio}} = \frac{\text{Referenzzeit}_{\text{x}}}{\text{Laufzeit}_{\text{x}} \text{auf Testsystem}}$
- bilde geometrisches Mittel: $\sqrt[n]{\prod_{i=1}^{n} \text{SPECratio}_n}$

#### SPECrate
- $\text{SPEC}_{\text{rate}} = n_x \cdot \frac{\text{Referenzzeit}_{\text{x}}}{\text{Ausführungszeit}_{\text{x}}}$
- auch hier geometrisches Mittel $\sqrt[n]{\prod_{i=1}^{n} \text{SPECrate}_n}$



#### Gesetz von Little
- $L = \lambda \cdot t$
    - $L$: mittlere Anzahl Aufträge im Wartesystem
    - $\lambda$: mittlere Ankunftsrate (Aufträge pro Zeiteinheit)
    - $t$: mittlere Verweilzeit ($t = w + b$)
- oder: $Q = \lambda \cdot w$
    - $Q$: mittlere Warteschlangenlänge
    - $w$: mittlere Wartezeit (in Queue)
    - $b$: mittlere Bedienzeit
- Voraussetzung: statistisches Gleichgewicht

# TODO
- Taxonomie Simulatoren
- Fehlerwahrscheinlichkeit advanced
- Parallelität
- Flynn
- Pipelining
- Sprungvorhersage
- Registerumbennenung
- VLIW
- Multithreading
