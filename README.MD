# GitHub — opis organizacji i przewodnik konfiguracji

Materiały do skonfigurowania profilu organizacji GitHub oraz repozytorium projektu **Cyber-Trener Siatkarz** (grupa URAN, KCK).

---

## 1. Propozycja nazwy organizacji

| Pole | Wartość |
|------|---------|
| **Nazwa organizacji (slug)** | `grupa-uran-kck` lub `cyber-trener-uran` |
| **Wyświetlana nazwa** | Grupa URAN — Cyber-Trener |
| **Lokalizacja** | Łódź, Polska |
| **Strona WWW** | *(opcjonalnie)* link do README na GitHub Pages lub strona uczelni |

Slug wybierzcie raz — później zmiana jest uciążliwa. Krótki i czytelny wystarczy.

---

## 2. Opis organizacji (do wklejenia w GitHub)

### Krótki (pole *Description* w ustawieniach organizacji, max ~350 znaków)

```
Zespół studencki Politechniki Łódzkiej (grupa URAN). Projekt KCK „Cyber trener” — wirtualny trener odbicia dolnego w siatkówce: analiza postawy na żywo (MediaPipe, YOLO), feedback głosowy i wizualny, tryb Dual-Cam.
```

### Dłuższy (profil README organizacji — patrz sekcja 5)

```markdown
# Grupa URAN — Cyber-Trener Siatkarz

Zespół projektowy realizujący przedmiot **KCK (*Cyber trener*)** na Politechnice Łódzkiej.

## O projekcie

**Cyber-Trener Siatkarz** to stacjonarny system wspomagający naukę odbicia piłki sposobem dolnym. Aplikacja analizuje postawę i moment kontaktu z piłką za pomocą kamery, podaje wskazówki na żywo oraz krótkie podsumowanie po każdym odbiciu — tak, aby ćwiczący mógł skupić się na ruchu, a nie na ekranie.

## Zespół

| Imię i nazwisko      | Nr albumu |
|----------------------|-----------|
| Szymon Zamachowski   | 255735    |
| Piotr Michalak       | 255654    |
| Krzysztof Olbiński   | 255667    |
| Dominik Kwintal      | 255647    |

## Repozytoria

| Repozytorium | Opis |
|--------------|------|
| [wirtualny-trener-grupa-uran](https://github.com/ORG/wirtualny-trener-grupa-uran) | Główny monorepo: backend Python/FastAPI, frontend React, logika trenera |

## Technologie

Python · FastAPI · MediaPipe · YOLO · React · TypeScript · Supabase · Vosk · TTS

## Dokumentacja

- [README projektu](https://github.com/ORG/wirtualny-trener-grupa-uran#readme)
- [Uruchomienie i szkolenie](https://github.com/ORG/wirtualny-trener-grupa-uran/blob/main/URUCHOMIENIE_I_SZKOLENIE.md)
- [Konsultacja trenera](https://github.com/ORG/wirtualny-trener-grupa-uran/blob/main/KONSULTACJA_TRENERA.md)

---
*Projekt studencki — Politechnika Łódzka, 2025/2026*
```

*(Zamień `ORG` na faktyczny slug organizacji.)*

---

## 3. Opis repozytorium (pole *About* przy repo)

### Description (krótki, ~350 znaków)

```
Wirtualny trener odbicia dolnego w siatkówce — analiza postawy na żywo (MediaPipe + YOLO), Dual-Cam, feedback głosowy i wizualny, zapis sesji. Projekt KCK, grupa URAN, Politechnika Łódzka.
```

### Website (opcjonalnie)

```
https://github.com/ORG/wirtualny-trener-grupa-uran#readme
```

### Topics (tagi — wklej w pole *Topics*)

```
volleyball
computer-vision
mediapipe
yolov8
fastapi
react
typescript
sports-analytics
pose-estimation
student-project
politechnika-lodzka
kck
```

---

## 4. Przewodnik — krok po kroku

### Krok 1: Utworzenie organizacji

1. Zaloguj się na [github.com](https://github.com).
2. Kliknij avatar (prawy górny róg) → **Your organizations** → **New organization**.
3. Wybierz plan **Free** (wystarczy do projektu studenckiego).
4. Wpisz **Organization name** (np. `grupa-uran-kck`).
5. Podaj **Contact email** (np. wspólny mail zespołu lub uczelniany).
6. Organizacja należy do: **My personal account** (na start; później można przekazać własność).
7. Zaproś członków zespołu (**Invite owners** lub dodaj później).

**Role członków:**

| Rola | Kto | Uprawnienia |
|------|-----|-------------|
| **Owner** | 1–2 osoby (np. lider repo) | Pełna kontrola, billing, usuwanie org |
| **Member** | Pozostali z zespołu | Dostęp do repozytoriów wg ustawień |

---

### Krok 2: Przeniesienie repozytorium do organizacji

Jeśli repo jest na koncie osobistym:

1. Wejdź w repo → **Settings** → na samym dole **Danger Zone**.
2. **Transfer ownership** → wybierz organizację.
3. Wpisz nazwę repo, aby potwierdzić.
4. Zaakceptuj transfer (Owner organizacji musi potwierdzić, jeśli to inna osoba).

Alternatywa — repo od zera w organizacji:

1. W organizacji: **New repository**.
2. Nazwa: `wirtualny-trener-grupa-uran`.
3. **Add a README** — nie zaznaczaj (macie już kod).
4. Lokalnie dodaj remote i push:

```bash
git remote add origin https://github.com/grupa-uran-kck/wirtualny-trener-grupa-uran.git
git push -u origin main
```

---

### Krok 3: Uzupełnienie profilu organizacji

1. Organizacja → **Settings** → **Profile**.
2. Wypełnij:
   - **Display name:** `Grupa URAN — Cyber-Trener`
   - **Description:** *(krótki opis z sekcji 2)*
   - **Location:** `Łódź, Poland`
   - **URL:** link do README lub strony projektu
3. **Upload logo** — użyj `frontend/public/favicon.svg` (piłka siatkówka) lub eksport PNG 200×200.

---

### Krok 4: Profil README organizacji (opcjonalnie, ładny efekt na stronie org)

1. W organizacji utwórz **publiczne** repo o nazwie dokładnie: `.github`
2. W środku dodaj plik `profile/README.md` z treścią z sekcji 2 (dłuższy opis).
3. Po pushu profil będzie widoczny na `https://github.com/ORG`.

```bash
# Przykład — w osobnym katalogu lub branchu
mkdir -p .github/profile
# skopiuj treść README z sekcji 2 do .github/profile/README.md
git add .github/profile/README.md
git commit -m "Dodaj profil README organizacji"
git push
```

---

### Krok 5: Konfiguracja repozytorium głównego

1. Repo → **Settings** → **General** → **Features:**
   - Issues: **włączone** (bugi, zadania)
   - Projects: opcjonalnie (tablica Kanban)
   - Wiki: wyłączone (macie markdown w repo)
2. **Settings** → prawa kolumna **About** (ołówek):
   - Wklej **Description**, **Website**, **Topics** z sekcji 3.
3. **Social preview** — *Settings* → *General* → *Social preview* → wgraj screenshot z Live Analysis (1200×630 px).

---

### Krok 6: Szablony Issues (zalecane)

Utwórz w repo folder `.github/ISSUE_TEMPLATE/`:

**bug_report.md** — zgłoszenie błędu (kroki reprodukcji, środowisko).  
**task.md** — zadanie zespołowe (np. kalibracja progów, PDF export).

Krótki przewodnik dla zespołu:

1. **Issues** → **New issue** → wybierz szablon.
2. Przypisz **Assignee** i **Labels** (`bug`, `enhancement`, `documentation`, `backend`, `frontend`).

Etykiety utwórz ręcznie: repo → **Issues** → **Labels** → **New label**.

| Label | Kolor | Zastosowanie |
|-------|-------|--------------|
| `bug` | czerwony | Błąd w działaniu |
| `enhancement` | niebieski | Nowa funkcja / ulepszenie |
| `documentation` | szary | README, raport, instrukcje |
| `backend` | zielony | Python, CV, API |
| `frontend` | fioletowy | React, UI |
| `prio-demo` | pomarańczowy | Blokuje prezentację / obronę |

---

### Krok 7: Ochrona gałęzi `main` (zalecane)

1. Repo → **Settings** → **Branches** → **Add branch protection rule**.
2. **Branch name pattern:** `main`
3. Włącz:
   - **Require a pull request before merging** (min. 1 approval — opcjonalnie na start wyłączone dla małego zespołu)
   - **Require status checks to pass** — jeśli dodacie CI później
4. **Do not allow bypassing** — tylko dla Ownerów, jeśli chcecie luźniejszy workflow studencki.

Dla zespołu 4-osobowego często wystarczy: **PR + review kolegi** bez sztywnej ochrony.

---

### Krok 8: Sekrety i pliki wrażliwe

**Nigdy nie commitujcie:**

- `.env` z kluczami Supabase
- tokenów API, haseł

Sprawdźcie, że `.gitignore` zawiera `.env`. Klucze Supabase trzymajcie lokalnie; w README opisujcie tylko **nazwy zmiennych**, nie wartości.

Jeśli kiedyś dodacie GitHub Actions z deployem — sekrety: **Settings** → **Secrets and variables** → **Actions**.

---

### Krok 9: Widoczność i licencja

1. **Public** — zalecane na projekt uczelniany (prezentacja, portfolio).
2. W README na dole możecie dopisać: *„Kod projektu studenckiego — grupa URAN, Politechnika Łódzka, 2025/2026”*.
3. Licencja: dla projektu KCK często **brak licencji open-source** lub **MIT** — ustalcie z prowadzącym.

---

## 5. Checklist po konfiguracji

- [ ] Organizacja utworzona, wszyscy członkowie zaproszeni
- [ ] Repo przeniesione / opublikowane pod organizacją
- [ ] Wypełniony opis organizacji i logo
- [ ] W repo: Description, Topics, Social preview
- [ ] README linkuje do `URUCHOMIENIE_I_SZKOLENIE.md` i `KONSULTACJA_TRENERA.md`
- [ ] `.env` nie jest w historii gita
- [ ] (Opcjonalnie) Profil `.github/profile/README.md`
- [ ] (Opcjonalnie) Etykiety Issues i szablony zgłoszeń

---

## 6. Szybkie linki (po utworzeniu — podmień ORG)

| Co | URL |
|----|-----|
| Profil organizacji | `https://github.com/ORG` |
| Repozytorium | `https://github.com/ORG/wirtualny-trener-grupa-uran` |
| Issues | `https://github.com/ORG/wirtualny-trener-grupa-uran/issues` |
| Ustawienia org | `https://github.com/ORG/settings/profile` |

---

*Dokument przygotowany dla zespołu URAN — czerwiec 2026*
