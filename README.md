# TiAuMU
# Predviđanje ponovne hospitalizacije dijabetičkih pacijenata

Projekat se bavi predviđanjem da li će pacijent sa dijabetesom biti ponovo hospitalizovan u roku od 30 dana.

Koristi se **XGBoost** model, uz EDA, feature engineering i automatsku optimizaciju hiperparametara pomoću **Ray Tune**.

## Pokretanje projekta

Projekat je napravljen za **Google Colab**.

### 1. Otvoriti notebook

Otvoriti fajl `TiAuMU.ipynb` u Google Colab-u.

### 2. Instalirati biblioteke

Prva ćelija notebook-a instalira potrebne biblioteke:

```python
!pip install -q ray[tune] imbalanced-learn xgboost
```

Ostale korišćene biblioteke (`numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `statsmodels` i `scikit-learn`) su standardno dostupne u Colab-u.

### 3. Dodati podatke

U Google Drive-u napraviti folder:

```text
MyDrive/MLOps/
```

U njega je potrebno postaviti:

```text
diabetic_data.csv
IDS_mapping.csv
```

Notebook automatski učitava podatke iz tog foldera.

### 4. Pokrenuti notebook

Nakon pokretanja ćelije za povezivanje sa Google Drive-om, pokrenuti ćelije redom pomoću **Runtime → Run all**.

Notebook zatim izvršava:

- učitavanje i pregled podataka
- analizu nedostajućih vrednosti
- EDA
- analizu ciljne promenljive
- feature engineering
- poređenje baseline i FE pristupa
- proveru uticaja SMOTE-a
- treniranje XGBoost modela
- automatsku optimizaciju hiperparametara pomoću Ray Tune
- evaluaciju finalnog modela na test skupu

## Napomena

Potrebno je da Google Drive bude povezan sa Colab-om i da se podaci nalaze tačno na putanji:

```text
/content/drive/MyDrive/MLOps/
```

Za reprodukciju rezultata preporučuje se da se ćelije pokrenu redom od početka do kraja.
