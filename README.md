# DLMAIIUK01 – Jupyter Notebooks (Kausalität & probabilistische Modellierung)

Dieses Repository enthält eine kleine Sammlung von **Jupyter-Notebooks**, die Themen aus probabilistischer Modellierung und kausaler Inferenz demonstrieren, u.a.:

* **Kausale Inferenz mit** [`doWhy`](https://github.com/microsoft/dowhy) (Confounding, Backdoor-Adjustment, Interventionen / *do*-Operator)
* **Bayes’sche Netze** mit `pgmpy` (Wet Grass / Sprinkler sowie das klassische „Asia“-Netz)
* **Markov-Ketten** (Konvergenz zum Gleichgewicht / zur stationären Verteilung)
* **Bayes’sche lineare Regression** mit `PyMC3`

Die (gepinnten) Python-Abhängigkeiten stehen in `requirements.txt`.

## Schnellstart

### 1) Umgebung erstellen

Mit `venv`:

```bash
python -m venv .venv
.
.venv\Scripts\activate
pip install -r requirements.txt
```

Mit `conda`:

```bash
conda create -n dlmaiiuk01 python=3.8 -y
conda activate dlmaiiuk01
pip install -r requirements.txt
```

### 2) (Optional) Graphviz als Systempaket installieren

Einige Notebooks rendern Graphen. Dafür muss Graphviz ggf. zusätzlich auf dem Betriebssystem installiert sein.

* Linux (Debian/Ubuntu):

```bash
sudo apt install graphviz libgraphviz-dev graphviz-dev pkg-config
```

Unter Windows Graphviz installieren (z.B. von https://graphviz.org/download/) und sicherstellen, dass `dot` im `PATH` liegt.

### 3) JupyterLab starten

```bash
jupyter lab
```

## Notebooks (was man damit machen kann)

* **DoWhyFirstSteps.ipynb**
  * Synthetische kausale Daten erzeugen, `CausalModel` definieren, Estimand identifizieren und die **ATE** mittels linearer Regression und Propensity-Score-Methoden schätzen.

* **doWhy_Confounder.ipynb**
  * Ein klassisches **Confounding**-Szenario („Sweet Spot“-Artefakt) zeigen und demonstrieren, dass der Effekt nach Adjustierung verschwindet.

* **doWhy_CausalDo.ipynb**
  * **Interventionen** mit dem *do*-Operator: Outcomes unter `do(X=1)` vs `do(X=0)` vergleichen und die ATE berechnen.

* **Adjusting_for_confounder_binary_variables.ipynb**
  * Binäre Treatment-Variable mit Confounder: verzerrte Schätzung (ohne Confounder) vs. adjustierte Schätzung (Backdoor-Methoden) und Diskussion einer Refutation.

* **Adjusting_for_confounder_continuous_variables.ipynb**
  * Kontinuierliches Treatment und mehrere Outcomes: Effekte pro Outcome schätzen und mit einem **Placebo-Refuter** plausibilisieren.

* **Sprinkler.ipynb**
  * Wet-Grass-Bayesnetz (C/S/R/W) aufbauen, CPTs definieren und Posterioren mit Variablenelimination in `pgmpy` berechnen.

* **AsiaBayesNet.ipynb**
  * Das bekannte **Asia**-Bayesnetz (aus einer BIF-Datei) laden und Inferenz mit Evidenz durchführen.

* **MCEquilibrium.ipynb**
  * Übergangsmatrix einer Markov-Kette definieren, Zustände iterieren und die Konvergenz zur Gleichgewichtsverteilung beobachten.

* **LinearRegressionProbabilistic.ipynb**
  * Bayes’sche lineare Regression in **PyMC3**: Priors festlegen, Posterior sampeln, Diagnostik prüfen und Unsicherheit / Credible Intervals visualisieren.

## Anmerkung

Die Jupyter-Notebooks sind bisher aus dem englishen "Inference and Causality" Kurs der IU und noch nicht in die deutsche Sprache übersetzt.

Bei Problemen diesbezüglich bitte bei dem Tutor des Kurses melden.