# Setup dla zespołu C-ICAS

Toolkit video do produkcji zawartości za pomocą Claude Code.

## Quick Start

### 1. Sklonuj repozytorium
```bash
git clone https://github.com/mariusz-C-ICAS/claude-code-video-toolkit.git
cd claude-code-video-toolkit
```

### 2. Instalacja dependencies
```bash
# Opcjonalnie - dla AI tools (voiceover, image gen, music)
python3 -m pip install -r tools/requirements.txt
```

### 3. Otwórz Claude Code
```bash
claude
```

## W Claude Code

### Setup (first time)
```
/setup
```
Konfiguruje:
- Cloud GPU provider (Modal/RunPod) — ~$30/miesiąc free tier
- File transfer storage (Cloudflare R2 - free tier)
- Voice config (ElevenLabs / Qwen3-TTS)

### Tworzenie pierwszego wideo
```
/video
```
Claude Code przeprowadzi Cię przez cały workflow:
1. Wybór template'u
2. Wybór brandu (design, colors, voice)
3. Script planning
4. Asset gathering
5. Scene review
6. Audio generation
7. Rendering

## Workflow wideo

```
/video → Script → Assets → Scene Review → Design → Audio → Preview → Render
```

## Dostępne komendy

| Komenda | Opis |
|---------|------|
| `/video` | Lista, resume, lub nowy projekt |
| `/setup` | First-time setup (GPU, storage, voice) |
| `/scene-review` | Preview w Remotion Studio |
| `/design` | Refinement einzelnej sceny |
| `/brand` | Brand profiles (colors, fonts, voice) |
| `/template` | Lista templates lub create new |
| `/record-demo` | Nagrywanie screencastu z Playwright |
| `/generate-voiceover` | AI voiceover generation |
| `/redub` | Zmiana głosu w istniejącym wideo |
| `/voice-clone` | Nagranie i klonowanie głosu |

## Struktura repozytorium

```
.
├── .claude/          # Skills i commands dla Claude Code
├── lib/              # Reusable components, transitions, theme
├── tools/            # Python CLI tools (voiceover, music, image gen, video gen)
├── templates/        # Video templates (sprint-review, product-demo, etc)
├── brands/           # Brand profiles (colors, fonts, assets)
├── projects/         # Twoje video projekty (gitignore'd)
├── examples/         # Finished projects (pokaż co jest możliwe)
└── docs/             # Full documentation
```

## Dokumentacja

- [Getting Started](docs/getting-started.md)
- [Creating Templates](docs/creating-templates.md)
- [Creating Brands](docs/creating-brands.md)
- [Modal Setup](docs/modal-setup.md) — Cloud GPU (recommended)
- [RunPod Setup](docs/runpod-setup.md) — Cloud GPU (alternative)

## Przykłady

Skończone projekty w `examples/`:
- `sprint-review-cho-oyu` — iOS sprint review z demosami
- `digital-samba-skill-demo` — Product demo
- `the-space-between` — AI-generated video essay

## Hello World (brak API keys)

Bez setupu — od razu render:

```bash
cd examples/hello-world
npm install
npm run render
# Output: MP4 file, ready to watch
```

## AI Tools (dostępne w /video workflow)

| Tool | Opis | Cost |
|------|------|------|
| `qwen3_tts` | Text-to-speech (9 voices, cloning) | ~$0.01 |
| `flux2` | Image generation & editing | ~$0.02 |
| `image_edit` | AI image editing | ~$0.03 |
| `ltx2` | Text-to-video, image-to-video | ~$0.23 |
| `sadtalker` | Talking head animation | ~$0.10 |
| `musik_gen` | AI music generation | Free (acemusic) / ~$0.05 |

Wszystkie działają na Modal/RunPod cloud GPU — configure via `/setup`.

## Contributing

Zmiany do templates, brands, lub tools:
1. Gałąź od `main`
2. Push
3. Otwórz PR

## Pytania / Issues

Otwórz issue w tym repozytorium — lub skontaktuj się bezpośrednio z zespołem.

---

**Motto: Be brave. Experiment.** Share videos & ideas back!
