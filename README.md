# Mašinsko učenje 25/26 projekat

Tema: **Klasifikacija muzičkih žanrova**

Članovi tima:

- [Andrija Radojević] [154/2022]
- [Matej Nikolić] [73/2022]

## Tehnikalije

Potrebni paketi navedeni su u datoteci `requirements.txt`.

Instalacija:

```bash
pip install -r requirements.txt
```

Projekat je implementiran u jednoj Jupyter svesci:

`01_music_genre_classification.ipynb`

Za pokretanje projekta potrebno je preuzeti GTZAN skup podataka i smestiti ga u:

```text
Data/genres_original/
```

Nakon toga potrebno je otvoriti Jupyter svesku i izvršiti je od početka do kraja.

## O projektu

Cilj projekta je klasifikacija muzičkih žanrova na osnovu audio zapisa iz GTZAN skupa podataka.

U projektu je upoređeno pet pristupa:

- Logistic Regression
- SVM
- FCNN nad log-Mel spektrogramima
- FCNN nad 93 izdvojene audio karakteristike
- kombinovani CNN + FCNN model

Za predstavljanje audio zapisa korišćeni su log-Mel spektrogrami i 93 izdvojene audio karakteristike.

Podaci su podeljeni na trening, validacioni i test skup u odnosu **70% / 15% / 15%**, uz stratifikaciju.

Najbolji rezultat ostvario je kombinovani **CNN + FCNN** model sa tačnošću od **74% na test skupu**.

## Skup podataka

Korišćen je **GTZAN Genre Collection** skup podataka.

Skup sadrži 10 muzičkih žanrova:

- blues
- classical
- country
- disco
- hiphop
- jazz
- metal
- pop
- reggae
- rock

Originalni skup sadrži 1000 audio zapisa, po 100 za svaki žanr. Jedan nečitljiv fajl je tokom učitavanja preskočen, pa je u projektu korišćeno ukupno **999 audio zapisa**.

Skup podataka nije postavljen na GitHub zbog svoje veličine.

## Sačuvani modeli

Istrenirani modeli i propratni **skaleri** sačuvani su u `.pkl` i `.pth` formatima.

Sačuvani fajlovi su:

```text
logistic_model.pkl
svm_model.pkl
spectrogram_scaler.pkl
features_scaler.pkl
fcnn_model.pth
fcnn_93_features_model.pth
cnn_fcnn_model.pth
```
## Reference

- Albert Pun, Kamilla Nazirhanova — **Music Genre Classification with Mel Spectrograms and CNN**
- George Tzanetakis, Perry Cook — **Musical Genre Classification of Audio Signals**
