# Analizer-rymow

Aplikacja okienkowa (GUI) napisana w języku Python, służąca do zaawansowanej analizy tekstów, wierszy oraz tekstów piosenek pod kątem wyszukiwania i wizualizacji rymów.

## Główne funkcjonalności

*   **Wczytywanie i analiza tekstu:** Możliwość wczytania własnego pliku `.txt` lub bezpośredniego wklejenia tekstu do edytora.
*   **Inteligentne wyszukiwanie rymów:** Algorytm automatycznie oczyszcza tekst ze znaczników (np. `[Refren]`), usuwa interpunkcję i grupuje słowa o tych samych końcówkach.
*   **Dynamiczna wizualizacja:** Zgrupowane rymy są automatycznie podświetlane w edytorze za pomocą losowo generowanych, pastelowych kolorów (opartych na przestrzeni barw HSV), co ułatwia analizę wzrokową.
*   **Eksport wyników (JSON):** Możliwość zapisu wygenerowanego raportu (zgrupowanych rymów) do pliku `.json` z zachowaniem polskiego kodowania znaków.

## Wykorzystane technologie i koncepcje (Python)

Projekt został podzielony na moduły zgodnie z zasadą *Separation of Concerns* i wykorzystuje następujące techniki programistyczne:
*   **Tkinter (GUI):** Tworzenie interfejsu graficznego, obsługa zdarzeń i system tagowania tekstu (`tag_config`, `tag_add`).
*   **Programowanie Obiektowe (OOP):** Klasy, konstruktory (`__init__`), enkapsulacja i referencje `self`.
*   **Wyrażenia regularne (RegEx):** Zaawansowane czyszczenie tekstu i tokenizacja słów (`re.sub`, `re.findall`, granice słowa `\b` i `\m`).
*   **Generatory:** Wykorzystanie słowa kluczowego `yield` do leniwego (oszczędzającego pamięć RAM) przetwarzania końcówek słów.
*   **Dekoratory:** Własny dekorator `@time_it` (z obsługą `*args` i `**kwargs`) do pomiaru czasu wykonywania algorytmów bez ingerencji w ich logikę.
*   **Custom Exceptions:** Definicja i rzucanie własnych błędów (np. `EmptyTextError`) oraz ich bezpieczna obsługa za pomocą bloków `try-except`.
*   **Struktury danych:** Zaawansowane wykorzystanie słowników, zbiorów (`set`) oraz wyrażeń słownikowych (*Dict Comprehension*).

## Jak uruchomić projekt?

Projekt korzysta wyłącznie ze standardowej biblioteki Pythona i **nie wymaga** instalacji dodatkowych paczek (brak pliku requirements.txt).

1. Sklonuj repozytorium na swój komputer.
2. Upewnij się, że masz zainstalowanego Pythona w wersji 3.x.
3. Otwórz terminal, przejdź do katalogu z pobranym projektem i uruchom plik startowy:

```bash
python main.py
```
