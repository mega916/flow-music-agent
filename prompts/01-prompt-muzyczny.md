# Prompt muzyczny — główny szablon

Ten plik to serce agenta. Ma dwie części:

- **Część 1** — gotowy szablon, który wklejasz do Flow Music (ręcznie).
- **Część 2** — meta-prompt, którym prosisz AI (Claude/ChatGPT) o wygenerowanie takiego szablonu z Twojego pomysłu.

---

## Część 1. Szablon do wklejenia

Wypełnij pola w `[ ]`. Usuń to, co nie pasuje.

### STYL

```
[gatunek główny], [podgatunek lub epoka], [tempo] BPM, [tonacja opcjonalnie],
[nastrój 1], [nastrój 2],
[instrument wiodący 1], [instrument wiodący 2], [instrument tła],
[typ wokalu: płeć, barwa, sposób śpiewania],
[charakter produkcji: czysta / lo-fi / szeroka / surowa / analogowa],
[dynamika: np. cichy początek, mocny refren]
```

Przykład wypełnienia:

```
indie folk, warm acoustic, 92 BPM, A minor,
nostalgic, hopeful,
fingerpicked acoustic guitar, soft upright bass, light brushed drums,
breathy male vocal, intimate close-mic,
organic analog production,
quiet verses, big singalong chorus
```

### TEKST

```
[Intro]
(opcjonalnie: 1–2 linie lub same instrumenty)

[Verse 1]
linia 1
linia 2
linia 3
linia 4

[Pre-Chorus]
linia 1
linia 2

[Chorus]
fraza-hook
linia 2
fraza-hook
linia 4

[Verse 2]
...

[Bridge]
...

[Chorus]

[Outro]
```

### WYKLUCZENIA

```
no autotune, no rap, no choir, no heavy distortion, no spoken intro
```

---

## Część 2. Meta-prompt (do Claude/ChatGPT)

Skopiuj całość, a w miejscu `{{POMYSŁ}}` wpisz swoją myśl własnymi słowami.

```
Jesteś doświadczonym producentem muzycznym i autorem tekstów.
Zamień mój pomysł w gotowy prompt do generatora muzyki AI.

MÓJ POMYSŁ:
{{POMYSŁ}}

ZASADY:
1. Opis stylu pisz po angielsku, w jednej linii, 5–8 elementów oddzielonych przecinkami.
   Zawsze uwzględnij: gatunek, tempo w BPM, nastrój, 2–4 instrumenty, typ wokalu, charakter produkcji.
2. Tekst piosenki pisz po polsku, oryginalny, z sekcjami [Intro] [Verse 1] [Pre-Chorus] [Chorus] [Verse 2] [Bridge] [Chorus] [Outro].
   Linie po 6–10 sylab, proste rymy, refren z jednym powtarzalnym hookiem (max 4 linie).
3. Dodaj linię WYKLUCZENIA: czego generator ma nie dodawać.
4. Nie używaj nazw żyjących artystów ani cytatów z istniejących piosenek.
   Zamiast artysty opisz brzmienie słowami (epoka, rodzaj wokalu, produkcja).
5. Jeśli brakuje mi informacji, przyjmij rozsądne założenia i wypisz je w 1–2 liniach.

ZWRÓĆ:
- WARIANT A (zgodny z pomysłem)
- WARIANT B (ten sam pomysł, ale zmień jeden element: tempo, wokal albo aranż)
- NASTĘPNY KROK: jedna wskazówka, co zmienić, jeśli wynik będzie słaby.

Format każdego wariantu: STYL / TEKST / WYKLUCZENIA.
```

---

## Jak tego używać (krok po kroku)

1. Wpisz swój pomysł w meta-prompt (Część 2) i wyślij do AI.
2. Dostaniesz dwa warianty. Skopiuj **STYL** i **TEKST** wariantu A do Flow Music.
3. Wygeneruj utwór. Posłuchaj dwa razy.
4. Jeśli coś nie gra, zmień **jedną** rzecz naraz (tempo albo wokal albo instrumenty). Wtedy widzisz, co naprawdę zadziałało.
5. Dobry styl zapisz do `knowledge/preferencje.md`, żeby wracać do niego w kolejnych utworach.

## Najczęstsze błędy

| Błąd | Efekt | Poprawka |
|---|---|---|
| Za dużo tagów (20+) | Brzmienie się rozmywa | Zostaw 5–8 najważniejszych |
| Sprzeczne tagi ("calm" + "aggressive") | Chaos | Wybierz jeden nastrój wiodący |
| Brak BPM | Losowe tempo | Zawsze podaj liczbę |
| Długie linie tekstu | Śpiewak się "zacina" | Skróć do 6–10 sylab |
| Trudne polskie słowa w refrenie | Zła wymowa | Uprość lub zapisz fonetycznie |
| Brak sekcji w tekście | Brak struktury utworu | Dodaj [Verse], [Chorus] itd. |
