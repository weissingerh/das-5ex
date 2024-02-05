# Report

## Results 
### Bone Marrow Dataset

| Model                   |   Accuracy |   Precision |   Recall | Training Time          | Testing Time            |
|-|-|-|-|-|-|
| KNN (20 Neighbors)      |   0.83871  |    0.83871  | 0.840212 | 0.00527501106262207s   | <span style="color:red">0.13753604888916016s</span>   |
| KNN (40 Neighbors)      |  <span style="color:green">0.919355</span> |    <span style="color:green">0.919355</span> | <span style="color:green">0.920106</span> | 0.0030858516693115234s | 0.004518985748291016s  |
| KNN (80 Neighbors)      |   0.677419 |    0.677419 | 0.62963  | <span style="color:green">0.0007240772247314453s</span> | 0.020986080169677734s  |
| Perceptron              |   0.645161 |    0.645161 | 0.592593 | 0.006169795989990234s  | 0.0007369518280029297s |
| Naive Bayes (Gaussian)  |   0.629032 |    0.629032 | 0.574074 | 0.00571894645690918s   | <span style="color:green">0.0004558563232421875s</span> |
| Naive Bayes (Bernoulli) |   0.725806 |    0.725806 | 0.727513 | 0.00189208984375s      | 0.0017139911651611328s |

### Diabetes Dataset

| Model                   |   Accuracy |   Precision |   Recall | Training Time         | Testing Time           |
|-|-|-|-|-|-|
| KNN (20 Neighbors)      |   0.550755 |    0.550755 | 0.382688 | 0.03202390670776367s  | 2.3535330295562744s    |
| KNN (40 Neighbors)      |   0.558824 |    0.558824 | 0.376338 | 0.024196863174438477s | 2.769627094268799s     |
| KNN (80 Neighbors)      |   0.556234 |    0.556234 | 0.367199 | 0.024379968643188477s | <span style="color:red">3.5231099128723145s</span>    |
| Perceptron              |   0.548164 |    0.548164 | 0.351074 | 0.0812530517578125s   | 0.006426811218261719s  |
| Naive Bayes (Gaussian)  |   0.556144 |    0.556144 | <span style="color:green">0.387752</span> | <span style="color:green">0.008704900741577148s</span> | <span style="color:green">0.0032339096069335938s</span> |
| Naive Bayes (Bernoulli) |   <span style="color:green">0.559092</span> |   <span style="color:green">0.559092</span> | 0.383981 | 0.016360998153686523s | 0.0063021183013916016s |


## Beschreibung

In den obigen Tabellen sind die Resultate der Classifier nochmals dargestellt und die besten Ergebnisse grün (beste Effectiveness bzw. Efficiency bei den Zeiten) bzw. bei den Testing Zeiten wurden die beiden schlechtesten farblich mit rot markiert. Ich habe darauf verzichtet, die anderen schlechtesten Werte farblich zu markieren, da hier keine großen Unterschiede zwischen den Classifier bestehen. 

### Diabetes Datensatz

Es hätte beim großen Diabetes Datensatz ebenfalls auf eine grüne Markierung der Metriken verzichtet werden können, da diese sehr ähnlich schlecht sind. Beim Diabetes Datensatz hat man bei allen Classifiern eine ca. 55% Accuracy und Precision, und ebenso sehr niedrige Recall-Werte zwischen 35-38,7%. 
Ich kann mir diese schlechten Ergebnisse nicht so ganz erklären, evtl. hat es damit zu tun, dass es nur einen Wert gibt bei Y, und deswegen die Models nicht wirklich getrained werden konnten, da zu wenig Daten vorhanden waren? Das ist meine Vermutung.

Für mich persönlich überraschend war, dass selbst bei diesem großen Datensatz nur sehr kurze Trainingszeiten (max. 0.008s) und Testingzeiten (max. 3.5s).

Ich bin mir allerdings nicht sicher, ob ich bei der Datenaufbereitung irgendetwas anderes übersehen habe, wodurch die Ergebnisse unbrauchbar wurden.

### Bone Marrow Datensatz

Der kleinere Bone Marrow Datensatz liefert sinnvollere Ergebnisse.
Hier fällt der Classifier KNN mit 40 Neighbors bezogen auf seine Effectiveness mit Abstand am Besten aus, mit ~92% bei Accuracy, Precision und Recall. Am schnellsten in der Training Time ist KNN mit 80 Neighbors, und in der Testing Time fällt der Perceptron Classifier aus.

Negativ sticht bei der Effectiveness der Naive Bayes (v.a. Gaussian Approach) hervor. Hierbei konnte nur ~63% Accuracy und Precision, sowie 57% Recall herbeigeführt werden.

## Fazit

Die KNN mit 40 Neighbors fällt der Effectiveness am besten aus, und ich würde den Classifier beim Bone Marrow Datensatz unter allen auswählen, da bei den Laufzeiten in Training und Test wenig Unterschied besteht.
Beim Diabetes Datensatz besteht kaum Unterschied zwischen den Ergebnissen, weshalb ich in einer realen Situation noch andere Classifier explorieren würde, und sonst die Datenaufbereitung nochmal unter die Lupe nehmen würde.