# LogisticRegressionAufg2
Prüfungsaufgabe 2 der Angleichsleistung

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Lara-167/LogisticRegressionAufg2/HEAD)

#Code-Ausführung:

    1. GitHub URL des Repository "Logistic-Regression" in https://mybinder.org/ einfügen und launchen
    2. Notebook öffnen
    3. Code-Zeilen nacheinander ausführen lassen

Zur Code-Ausführung muss der gesamte Code, Zelle für Zelle ausgeführt werden. Die notwendigen Bibliotheken werden mithilfe der requirements.txt und postBuild.txt installiert. Die Ergebnisse der Testfälle werden in der mean_func.log gespeichert.
Der Code beinhaltet die Funktionen my_logger und my_timer, um Funktionen zu loggen und um die Zeit der Ausführung zu messen.
Zudem werden zwei Testfälle mit den Trainingsfunktionen predict() und fit() ausgeführt.

Die Testdaten liegen in der Advertising.csv Datei.
Anhand dieser Daten werden die Testfälle ausgeführt.

Mit der Durchschnittsfunktion werden im Unittest folgende Werte erwartet:
- Ein Mittelwert für das Alter zwischen 30 und 40
- Ein Mittelwert für das Einkommen zwischen 50000 und 60000
Sowie mit der Min-Funktion ein Mindestalter von 18 Jahren.

Zum Testen der Vorhersagefunktion, werden die Indikatoren accuracy und precision angewandt, die sich aus der Confusion Matrix ableiten lassen:
Accuracy (test_01) wird verwendet, um die Leistung des Modells zu messen. Sie ist das Verhältnis zwischen der Gesamtzahl der richtigen Instanzen und der Gesamtzahl der Instanzen.
Precision (test_02) ist ein Maß dafür, wie die positiven Vorhersagen eines Modells sind. Sie sind definiert als das Verhältnis der wahren positiven Vorhersagen zur Gesamtzahl der positiven Vorhersagen des Modells.

Das Testkriterium legt fest, dass die Accuracy größer als 0.85 sein muss, ansonsten ist der Test ungültig und die Testdaten sind anzuzweifeln.
Zudem muss die Precision größer als 0.8 sein, da sonst auch in diesem Fall der Test ungültig und die Testdaten anzuzweifeln sind.
Damit kann geprüft werden, ob die Vorhersagefunktion korrekt funktioniert.

Um zu prüfen, ob das System innerhalb normaler Parameter läuft, wurde die repräsentative Laufzeit von 0.0245 aus 1000 Durchläufen ermittelt.
Im Unittest (test_03) wird geprüft, dass die Laufzeit der Trainingsfunktion während der Testfallausführung, einen Grenzwert von 150% der repräsentativen Laufzeit nicht überschreitet.

Je nachdem wie viel Zeit für den Testfall anfällt, ist der Test gültig oder ungültig.
Eine mögliche Bildschirmausgabe für alle Testfälle ist:

    test_01 (__main__.LaraTest)
    confusion matrix, accuracy... ... ok
    test_02 (__main__.LaraTest)
    confusion matrix, precision... ... ok
    test_03 (__main__.LaraTest)
    measurement of training function within 150% ... FAIL

    FAIL: test_03 (__main__.LaraTest)

    measurement of training function within 150%
    ----------------------------------------------------------------------
    Traceback (most recent call last):
    File "C:\Users\Lara\AppData\Local\Temp\ipykernel_12728\1903896088.py", line 31, in test_03
     self.assertLess(t_ist, t_max) # 150% max
    AssertionError: 0.14000463485717773 not less than 0.036750000000000005

    ----------------------------------------------------------------------
    Ran 3 tests in 0.152s

    FAILED (failures=1)
