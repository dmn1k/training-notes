# KI Text / Sprache

- word2vec: Wörter zu Vektoren: Wörter die häufig zusammen auftauchen liegen
  näher beieinander
- Tensorboard online
- Part of Speech Tagging
- gensim: Standard word2vec lib
- Zufällige Initialverteilung der NN-Gewichte macht wenig Sinn, Wortvektoren als
  Basis
- Verwendung von Recurrent Neural Networks: Ein oder mehrere Wörter als Input,
  ein oder mehrere Outputs
- RNN: Output wieder als Input
- Anwendungsfall: Übersetzung, bspw. deepl
- Objekterkennung: Sprache -> Text -> Finden bestimmter Objekte / Bestandteile
  (bspw. "7 Uhr", "wecken")
- Preprocessing notwendig: Umlaute, ß, zB/bspw, schläft-\>schlafen, des
  Baumes-\>?!
- Lemmatisierer, Stemmer -\> evtl. bei Lucene?
- Hyperparameter: Quasi Startparameter (anzahl runs, Dimensionsanzahl) - viele
  Möglichkeiten
- 80/20 Trainingsdaten / Testset
- Kaggle: ML-Competitions
- Hauptproblem: Overfitting
- Named Entity Recognition: spacy gute Bibiliothek
- Sprache als Input: voice.mozilla.org
