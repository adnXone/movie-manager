---
name: movie-manager
description: "Organizează recomandările de filme în Obsidian și generează sugestii bazate pe profilul utilizatorului."
---

# Movie Manager Skill

Transformați-ți agentul AI într-un partener cinematografic sofisticat. Acest skill merge dincolo de liste simple, oferind cercetare proactivă, organizare intelligentă în Markdown/Obsidian și un motor de recomandare personalizat care evoluează odată cu gusturile tale.

## 🌟 Caracteristici cheie

- **Integrare Surse de Vizionare**: Găsește și încadrează trailere oficiale YouTube și sugerează platforme de streaming disponibile.
- **Îmbunătățire Vizuală**: Preia URL-uri de postere și le afișează inline pentru o experiență de navigare bogată.
- **Organizare Inteligentă**: Gestionează dosarele `watchlist/` și `seen/` cu un index centralizat `Movies.md`.
- **Recomandator Personalizat**: Sugerează filme bazate pe profilul tău în evoluție de actori, genuri și teme preferate.
- **Logică Film Dublu**: Sugerează perechi complementare de filme pentru marathonuri personalizate.
- **Jurnalare Reflective**: Include prompt-uri după vizionare pentru a capta gânduri și amintiri.
- **Amintiri Smart**: Integrat cu `cron` pentru a-ți notifica lansările viitoare.
- **Integrare WikiLink**: Leagă persoane și genuri în vault-ul tău (creează ciorne `#people` când e necesar).

## 🛠 Configurare

### Variabile
- `MOVIES_ROOT`: Directorul de bază (implicit: `Movies/`).
- `WATCHLIST_DIR`: Noile descoperiri (implicit: `Movies/watchlist/`).
- `SEEN_DIR`: Filme arhivate (implicit: `Movies/seen/`).
- `INDEX_FILE`: Indexul central (implicit: `Movies/Movies.md`).
- `PROFILE_FILE`: Creierul de învățare (implicit: `Movies/Cinematic Profile.md`).
- `LANG`: Limbă pentru prompt-uri (implicit: `ro`).

## 🚀 Flux de lucru

### 0. Inițializare (Setare Automată)
La prima pornire sau rulare, skill-ul asigură:
1. Existența directorului `MOVIES_ROOT`.
2. Creerea subdirectoarelor `watchlist/` și `seen/` dacă lipsesc.
3. Inițializarea implicită a indexului `Movies.md` și a fișierului `Cinematic Profile.md`.

### 1. Recomandare ("Găsește-mi un film")
1. **Analiză Profil**: Citește `PROFILE_FILE` pentru actori, genuri și teme specifice preferate.
2. **Verificare Context**: Poate verifica jurnalul recent sau starea de spirit pentru a sugera un "vibe" potrivit.
3. **Film Dublu**: Oferă un "Power Duo" de două filme cu o conexiune unică.

### 2. Salvare în Watchlist
- Creează un fișier: `{Titlu} ({An}) - {Actor1}, {Actor2}.md` în `WATCHLIST_DIR`.
- Completează cu rating, surse de streaming, poster și trailer YouTube.
- Dacă filmul nu a fost încă lansat, creează un reminder `openclaw cron`.

### 3. Arhivare ca Vizionat & Învățare
1. **Arhivare**: Mută fișierul în `SEEN_DIR` și bifiază `[x]` în `Movies.md`.
2. **Reflectare**: Întreabă întrebări precum "Care a fost momentul cel mai surprinzător?" sau "Te-ai mai uitat la alte filme de la același regizor?".
3. **Evoluție**: Actualizează `PROFILE_FILE` cu noi actori, regizori sau genuri descoperite.

## 📄 Șablon Structurat

```markdown
# {Titlu} ({An})
![Poster]({URL Poster})

- **Rating**: ⭐ {Notă IMDb/RT}
- **Unde să-l vezi**: 📺 {Platforme Streaming}
- **Descriere**: {Rezumat}
- **Actori**: [[Actor1]], [[Actor2]]
- **Gen**: [[Gen1]]
- **Trailer**: {Link YouTube}

### 💡 De ce ți-ar plăcea
{Motivare personalizată bazată pe actori, gen și teme preferate}

### ✍️ Reflecții după vizionare
*(Adăugate la arhivare)*
- **Scene memorabile**:
- **Rating personal**: ⭐ {1-10}
- **Feedback rapid**: +1 / -1
```

---
Creat cu ❤️ pentru comunitatea OpenClaw.

Limbaj: prompt-urile și textul template-ului sunt în română (`ro`). Pentru engleză (`en`), setează `LANG=en` în configurarea skill-ului la rularea agentului.
