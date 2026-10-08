# Spairo Skills

Skille i narzędzia AI.

Praktyczne umiejętności po polsku. Pierwszy zestaw pomaga zebrać dane firmy
i wykorzystać je do uzupełniania formularzy.

| Skill | Do czego służy |
| --- | --- |
| [zbierz-kontekst-firmy](plugins/spairo-skills/skills/zbierz-kontekst-firmy/SKILL.md) | Zbiera dane z oficjalnego KRS i strony firmy oraz zapisuje kontekst do kolejnych zadań. |
| [uzupelnij-formularz](plugins/spairo-skills/skills/uzupelnij-formularz/SKILL.md) | Uzupełnia nową kopię formularza na podstawie kontekstu firmy i wskazuje brakujące dane. |

## Instalacja w Claude Desktop

1. Otwórz **Customize → Plugins**. W Cowork najpierw otwórz kartę **Cowork**.
2. Wybierz **Add → Add marketplace → Add from a repository**.
3. Wklej `https://github.com/Spairo-Platform/spairo-skills`
   lub `Spairo-Platform/spairo-skills`.
4. Odszukaj plugin **Spairo Skills** (`spairo`) i kliknij **Add**.
5. W rozmowie wpisz `/` lub kliknij `+`, aby zobaczyć oba skille.

Dodanie marketplace udostępnia katalog; zainstalowanie pluginu udostępnia
jego skille. Pluginy wymagają płatnego planu Claude. W organizacji dostęp
może zależeć od ustawień administratora.

## Pierwsze użycie

W Cowork udostępnij katalog z formularzem. W zwykłym czacie dołącz formularz
i zapisany kontekst jako załączniki. Do dokumentów pod linkiem potrzebny jest
dostęp Claude do danego źródła, np. podłączony Google Drive.

Najpierw wybierz **zbierz-kontekst-firmy** i podaj:

> Zbierz dane firmy [nazwa firmy] z [miejscowość] potrzebne do tego formularza.

Następnie wybierz **uzupelnij-formularz** i podaj:

> Uzupełnij załączony formularz, korzystając z tego kontekstu firmy.

W Cowork i Claude Code dostępne są także polecenia:

```text
/spairo:zbierz-kontekst-firmy [nazwa firmy] z [miejscowość]
/spairo:uzupelnij-formularz [ścieżka lub opis formularza]
```

Skill pracuje na kopii wzoru. Ceny, podpisującego, wyborów w oświadczeniach
i innych danych konkretnego zadania nie zgaduje. Przekazuje gotowy plik
oraz krótką notatkę z uzupełnionymi polami i brakami.

## Instalacja w Claude Code

```text
/plugin marketplace add Spairo-Platform/spairo-skills
/plugin install spairo@spairo-skills
```

## Przejście z wersji 0.1.0

Od wersji 0.2.0 identyfikator pluginu to `spairo`, a polecenia mają prefiks
`spairo:`. Nazwa wyświetlana nadal brzmi **Spairo Skills**.

Jeśli masz zainstalowaną wersję 0.1.0, usuń stary plugin `spairo-skills`,
odśwież marketplace i dodaj plugin `spairo`. Jeśli katalog nadal pokazuje
stary wpis, usuń marketplace i dodaj go ponownie z tego samego linku.
Następnie otwórz nową rozmowę.

W Claude Code:

```text
/plugin uninstall spairo-skills@spairo-skills
/plugin marketplace update spairo-skills
/plugin install spairo@spairo-skills
```

## Struktura repozytorium

```text
.claude-plugin/
  marketplace.json
plugins/
  spairo-skills/
    .claude-plugin/
      plugin.json
    skills/
      zbierz-kontekst-firmy/
        SKILL.md
        references/format-kontekstu.md
      uzupelnij-formularz/
        SKILL.md
```

Instrukcje skilli są w formacie `SKILL.md`, wraz z potrzebnymi referencjami.
Pliki `.claude-plugin` odpowiadają za dystrybucję w Claude. Kolejne pluginy
można umieszczać w `plugins/` i dopisywać w `marketplace.json`; integracje
z innymi aplikacjami mogą korzystać z tych samych instrukcji.

Przy publikowaniu zmian pluginu zwiększ `version` w jego `plugin.json`,
żeby instalacje mogły otrzymać nową wersję. Walidacja z katalogu repozytorium:

```bash
claude plugin validate .
claude plugin validate ./plugins/spairo-skills
```

## Dokumentacja formatu

- [Instalowanie i używanie pluginów w Claude](https://support.claude.com/en/articles/13837440-use-plugins-in-claude)
- [Tworzenie marketplace](https://code.claude.com/docs/en/plugin-marketplaces)
- [Manifest pluginu](https://code.claude.com/docs/en/plugins-reference)
