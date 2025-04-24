# Statystyczna Analiza Predykcji Przedziałów Cenowych Telefonów Mobilnych
źródło: https://www.kaggle.com/datasets/iabhishekofficial/mobile-price-classification

Ten projekt przedstawia analizę i modelowanie danych dotyczących telefonów komórkowych w celu predykcji przedziału cenowego (price\_range) urządzenia. Wykorzystano zestaw danych zawierający szczegółowe informacje o 2000 telefonach i ich cechach.


## Opis Danych

Zbiór danych zawiera 2000 rekordów telefonów mobilnych. Każdy rekord opisany jest następującymi zmiennymi:

1. `id` – Unikalny identyfikator telefonu.
2. `battery_power` – Całkowita pojemność baterii w mAh.
3. `blue` – Obsługa Bluetooth (1 = tak, 0 = nie).
4. `clock_speed` – Prędkość procesora w GHz.
5. `dual_sim` – Obsługa dwóch kart SIM (1 = tak, 0 = nie).
6. `fc` – Rozdzielczość przedniego aparatu w megapikselach.
7. `four_g` – Obsługa sieci 4G (1 = tak, 0 = nie).
8. `int_memory` – Pojemność pamięci wewnętrznej w GB.
9. `m_dep` – Grubość telefonu w cm.
10. `mobile_wt` – Waga telefonu w gramach.
11. `n_cores` – Liczba rdzeni procesora.
12. `pc` – Rozdzielczość tylnego aparatu w megapikselach.
13. `px_height` – Wysokość rozdzielczości ekranu w pikselach.
14. `px_width` – Szerokość rozdzielczości ekranu w pikselach.
15. `ram` – Ilość pamięci RAM w MB.
16. `sc_h` – Wysokość ekranu w cm.
17. `sc_w` – Szerokość ekranu w cm.
18. `talk_time` – Maksymalny czas rozmowy na jednym ładowaniu w godzinach.
19. `three_g` – Obsługa sieci 3G (1 = tak, 0 = nie).
20. `touch_screen` – Informacja o ekranie dotykowym (1 = tak, 0 = nie).
21. `wifi` – Obsługa Wi-Fi (1 = tak, 0 = nie).
22. `price_range` – Zmienna docelowa: 0 = low cost, 1 = medium cost, 2 = high cost, 3 = very high cost.



## Cel Projektu

1. **Eksploracyjna analiza danych** – sprawdzenie kompletności danych, wizualizacja rozkładów i korelacji.
2. **Redukcja wymiarowości** – zastosowanie PCA w celu usunięcia szumu i zachowania istotnej wariancji.
3. **Modelowanie** – porównanie klasyfikatorów:
   - Drzewo decyzyjne (Decision Tree)
   - Sieć neuronowa (MLPClassifier)
4. **Analiza reguł asocjacyjnych** – wykrycie zależności między cechami a `price_range` za pomocą Apriori i ECLAT.


## 📊 Kluczowe Wnioski

- Zbiór jest czysty (brak wartości brakujących i duplikatów) i zrównoważony pod względem `price_range`.
- PCA z 4 składowymi wyjaśnia \~95% wariancji, co poprawia generalizację modelu.
- **Drzewo decyzyjne** osiąga \~85% dokładności na zbiorze testowym po PCA.
- **Sieć neuronowa** działa lepiej po PCA (poprawa z niskich wartości do \~83–85% dokładności).
- Reguły asocjacyjne wskazują, że cechy takie jak `ram`, `battery_power` i `px_width` są silnymi predyktorami `price_range`.


## 🛠️ Technologie i Biblioteki

- Python
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn` (StandardScaler, PCA, DecisionTreeClassifier, MLPClassifier)
- `mlxtend` (Apriori, association\_rules)
- `factor_analyzer` (Bartlett’s test)
- `pyECLAT` (ECLAT)
- `missingno`

