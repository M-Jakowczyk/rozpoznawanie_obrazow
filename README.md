# rozpoznawanie_obrazow

## Opis projektu

Ten projekt zawiera serię notebooków Jupyter (`.ipynb`) poświęconych podstawom rozpoznawania obrazów i sieci neuronowych. Celem jest praktyczne zapoznanie się z budową, trenowaniem i oceną prostych modeli uczenia maszynowego, w szczególności sieci neuronowych, z wykorzystaniem biblioteki PyTorch.

---

### `1_neuron.ipynb` - Wprowadzenie do sieci neuronowych i klasyfikacji binarnej

Notebook `1_neuron.ipynb` stanowi wprowadzenie do koncepcji sieci neuronowych w kontekście problemu klasyfikacji binarnej. Używamy w nim syntetycznego zbioru danych "make_moons" z biblioteki `scikit-learn`, który jest klasycznym przykładem danych nieliniowo separowalnych.

**Główne kroki realizowane w notebooku:**

1.  **Generowanie danych:** Tworzymy syntetyczny zbiór danych `make_moons`, idealny do wizualizacji problemów klasyfikacji binarnej, które wymagają nieliniowego rozdzielenia.

2.  **Wizualizacja początkowa (próba klasyfikacji liniowej):**
    *   Przedstawiamy, jak prosty klasyfikator liniowy (odpowiednik regresji logistycznej) próbuje rozdzielić dane.
    *   Wizualizacja ta jasno pokazuje, że model liniowy jest niewystarczający dla tego typu danych.

3.  **Budowa prostej sieci neuronowej (PyTorch):**
    *   Definiujemy architekturę wielowarstwowego perceptronu (MLP) za pomocą PyTorch (`torch.nn.Module`).
    *   Sieć składa się z kilku warstw `nn.Linear` (warstwy gęste), funkcji aktywacji `ReLU` oraz warstw `BatchNorm1d` dla stabilizacji treningu.
    *   Warstwa wyjściowa wykorzystuje funkcję aktywacji `Sigmoid` do generowania prawdopodobieństw przynależności do klasy.

4.  **Trenowanie sieci:**
    *   Konfigurujemy funkcję straty (`nn.BCELoss` - Binary Cross-Entropy) oraz optymalizator (`torch.optim.SGD`).
    *   Przeprowadzamy proces trenowania sieci, iterując przez epoki i aktualizując wagi modelu.

5.  **Wizualizacja granicy decyzyjnej po treningu:**
    *   Po wytrenowaniu modelu, wizualizujemy jego granicę decyzyjną na zbiorze danych.
    *   Pokazujemy, jak sieć neuronowa jest w stanie nauczyć się złożonej, nieliniowej granicy, skutecznie rozdzielając dane "make_moons".