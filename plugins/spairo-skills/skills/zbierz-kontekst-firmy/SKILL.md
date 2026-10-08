---
name: zbierz-kontekst-firmy
description: Zbierz dane firmy z oficjalnego KRS i strony firmy, opcjonalnie pod wskazany formularz, i zapisz kontekst do kolejnych zadań.
---

# Zbierz kontekst firmy

```text
Zbierz kontekst firmy [nazwa firmy] z [miejscowość].
Zbierz dane firmy [nazwa firmy] potrzebne do załączonego formularza oferty.
```

## Dane

Dane rejestrowe bierz z aktualnego odpisu oficjalnego KRS, kontakt i opis
działalności z oficjalnej strony firmy. Niejednoznaczną tożsamość rozstrzygnij
z użytkownikiem.

Jeśli wskazano formularz ścieżką, linkiem lub opisem, zbierz tylko dane
firmy potrzebne do jego uzupełnienia. Pozostałe informacje, np. cenę oferty
lub uczestników wizji, zostaw do podania przez użytkownika.
Bez formularza zbierz podstawowe dane z [prostego wzoru](references/format-kontekstu.md).

Użyj tego wzoru, ograniczając pola do zebranego zakresu. Datę zebrania
i linki do źródeł umieść na końcu; brakujące dane oznacz „brak danych”.
Niedostępnego KRS nie zastępuj agregatorem.
Zachowaj zera na początku identyfikatorów.

## Zapis

Miejsce zapisu: wskazanie w zadaniu → instrukcje lub reguły projektu →
`kontekst-firmy-<company-slug>.md` w katalogu roboczym uruchomienia agenta.
Slug: nazwa bez formy prawnej, małe litery, bez znaków diakrytycznych,
słowa rozdzielone myślnikami; np. `kontekst-firmy-przykladowa-firma.md`.

Istniejący plik tej samej firmy odśwież. Zachowaj uzupełnienia użytkownika
z ich pochodzeniem i wcześniejsze daty danych niezweryfikowanych ponownie.
Kolizję nazw różnych firm rozwiąż dodaniem KRS lub NIP do domyślnego slugu;
wskazanego pliku innej firmy nie nadpisuj.

Podaj lokalizację zapisu oraz braki i rozbieżności.
