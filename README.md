# 🎵 Flow Music Agent

Agent-producent, który zamienia Twój pomysł w gotowy prompt do generatorów muzyki AI (np. [Flow Music](https://flowmusic.app)). Pracuje po polsku, daje dwa warianty i podpowiada, co poprawić.

## Co to robi

Wpisujesz: *"piosenka o poranku po nocnej zmianie, spokojna"*.
Dostajesz: **STYL + TEKST + WYKLUCZENIA** w dwóch wariantach, gotowe do wklejenia.

## Struktura repozytorium

```
flow-music-agent/
├── agents/
│   └── muzyk.md                  # definicja agenta (system prompt)
├── prompts/
│   └── 01-prompt-muzyczny.md     # główny szablon + meta-prompt
├── knowledge/
│   ├── gatunki-i-tagi.md         # ściąga: gatunki, BPM, nastroje, wokale
│   └── preferencje.md            # Twoje sprawdzone style (agent to czyta)
├── templates/
│   └── brief.md                  # formularz pomysłu na utwór
├── examples/
│   └── przyklady.md              # 3 gotowe utwory
└── .claude/agents/muzyk.md       # link do agenta dla Claude Code
```

## Szybki start (3 sposoby)

### A. Najprościej — bez instalowania
1. Otwórz `prompts/01-prompt-muzyczny.md`, sekcja **Część 2**.
2. Wklej meta-prompt do Claude lub ChatGPT i wpisz swój pomysł.
3. Skopiuj wynik do Flow Music.

### B. Jako projekt w Claude (claude.ai)
1. Utwórz nowy projekt.
2. W instrukcjach projektu wklej treść `agents/muzyk.md` (bez nagłówka między `---`).
3. Dodaj pliki z `knowledge/` jako wiedzę projektu.
4. Pisz pomysły w czacie.

### C. Jako agent w Claude Code
1. Sklonuj repo: `git clone https://github.com/TWOJ-LOGIN/flow-music-agent`
2. Wejdź do folderu i uruchom `claude`.
3. Wywołaj agenta: `@muzyk piosenka o poranku po nocnej zmianie`.

## Wrzucenie na GitHub (krok po kroku)

```bash
cd flow-music-agent
git init
git add .
git commit -m "Pierwsza wersja agenta muzycznego"
gh repo create flow-music-agent --public --source=. --push
```

Bez `gh`: utwórz puste repo na github.com, potem:

```bash
git remote add origin https://github.com/TWOJ-LOGIN/flow-music-agent.git
git branch -M main
git push -u origin main
```

## Zasady agenta

- Teksty są oryginalne, bez cytatów z istniejących piosenek.
- Bez nazwisk żyjących artystów w promptach, zamiast tego opis brzmienia.
- Uczciwie: generatory są losowe, zwykle trzeba 2–4 podejść.
- Zmieniaj **jedną** rzecz naraz, żeby wiedzieć, co zadziałało.

## Plan rozwoju

- [ ] `prompts/02-poprawki.md` — prompt do iteracji ("za wolno", "wokal za ostry")
- [ ] `prompts/03-album.md` — seria spójnych utworów
- [ ] `prompts/04-opis-i-tytul.md` — tytuł, opis i hashtagi pod publikację
- [ ] Skrypt generujący brief z formularza
- [ ] Biblioteka Twoich najlepszych stylów w `knowledge/preferencje.md`

## Prawa i licencje

Sprawdź warunki platformy, z której korzystasz, zanim użyjesz utworu komercyjnie. Zasady dotyczące praw do wygenerowanej muzyki zależą od planu i regulaminu.

## Licencja

MIT — patrz `LICENSE`.
