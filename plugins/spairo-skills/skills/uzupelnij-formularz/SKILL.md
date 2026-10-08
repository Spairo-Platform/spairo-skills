---
name: uzupelnij-formularz
description: Uzupełnij kopię formularza wskazanego ścieżką, linkiem lub opisem, korzystając z zapisanego kontekstu firmy.
---

# Uzupełnij formularz

```text
Uzupełnij formularz oferty dla mojej firmy.
Uzupełnij protokół z wizji lokalnej.
Uzupełnij formularz z załącznika, korzystając z podanego kontekstu firmy.
```

Formularz wskazany opisem znajdź w projekcie, także w podkatalogach.
Przy kilku pasujących wzorach zapytaj o wybór.

## Kontekst

Pierwszeństwo: wskazanie w zadaniu → instrukcje lub reguły projektu →
pliki `kontekst-firmy-*.md` bezpośrednio w katalogu roboczym uruchomienia agenta.

- Jeden plik: użyj go.
- Kilka: pokaż nazwy i zapytaj, który wybrać.
- Brak: poproś o nazwę firmy i miejscowość albo wskaż skill
  `zbierz-kontekst-firmy`. Po ustaleniu firmy przeczytaj
  [jego instrukcje](../zbierz-kontekst-firmy/SKILL.md), przekaż mu również
  formularz i wróć z utworzonym kontekstem.

Wskazany kontekst może być plikiem, załącznikiem lub dokumentem pod linkiem.
Braku dostępu do niego nie zastępuj wyborem innego źródła. Akceptuj dowolny
czytelny format; datowana migawka nie oznacza weryfikacji aktualności.

## Uzupełnienie i wynik

Wpisz dane mające pokrycie w kontekście lub zadaniu. Braki i rozbieżności
pozostaw do rozstrzygnięcia. Dane ogólne firmy nie określają kontaktu
w postępowaniu, a KRS nie wybiera podpisującego. Cena, gwarancja, status
MŚP, odbycie wizji i wybory w oświadczeniach wymagają danych dotyczących
zadania. Zachowaj wzór, istniejące wartości i pola podpisów.

Pracuj na nowej kopii; zachowaj oryginał i wcześniejsze wyniki bez zmian.
Miejsce wyniku: wskazanie w zadaniu lub projekcie, domyślnie obok lokalnego
formularza, a dla linku lub załącznika — katalog roboczy albo plik do pobrania.
Zapis zdalny tylko na wyraźne żądanie, jako nowy plik.

Nazwa: `<nazwa-wzoru>-<company-slug>-uzupelniony.<rozszerzenie>`, chyba że
wskazano inną. Slug: nazwa bez formy prawnej, małe litery, bez znaków
diakrytycznych, z myślnikami. Przy zajętej nazwie dodaj numer.
Zachowaj format źródła; natywny Google Docs domyślnie oddaj jako DOCX.
Przy DOCX sprawdź wyrenderowany układ lub zaznacz brak tej weryfikacji.

Obok wyniku zapisz krótką notatkę Markdown: źródło i data kontekstu,
uzupełnione pola oraz braki i decyzje. Podaj link do wyniku.
Danych pojedynczego zadania nie dopisuj do kontekstu bez prośby o zapamiętanie.
