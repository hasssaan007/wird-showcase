# Wird

> **Showcase page.** This repository is a public showcase of a **private repository**:
> it contains a description of the work only, with **no source code**.

Paste a link to a reel that recites an ayah, a hadith or a dua, and it lands in your daily list **in verified Arabic**, with a reciter of your choosing to read it back.

*Wird* is the classical word for a daily portion of recitation, which is exactly what the app keeps.

## The one design rule

Speech recognition mishears Arabic constantly, so the transcript is **never** what gets saved.

```
reel link -> audio extraction -> Whisper -> transcript
                                     |
                 transcript is a SEARCH QUERY, not content
                                     |
          Quran corpus  |  hadith corpus  |  dua library
                                     |
                    canonical text + source + grade
```

If nothing matches above the confidence threshold, the app says so and saves nothing as scripture. A plausible guess at somebody's daily recitation is worse than an honest blank.

## Authenticity

The corpora are pinned and verified rather than trusted:

- **Quran** - Uthmani Hafs, cross-checked against an independent publisher; all 6,236 ayat agree on every strong consonant, with the corpus file pinned by checksum
- **Hadith** - six books plus Malik, Nawawi 40 and Hadith Qudsi (36,064 entries); gradings are shown where they exist, and an ungraded hadith is never presented as authenticated
- **Duas** - a sourced adhkar library, each entry with a stated reference
- **Tafseer** - streamed from its original archive rather than rehosted

A verification script re-runs the corpus check and reports differences in tiers, so a typographic variant never masks a real textual difference.

## Stack

TypeScript, React Native mobile app, Python backend, Whisper speech-to-text, audio extraction pipeline, Supabase (Postgres, auth, storage), full-text and fuzzy matching over the corpora

---

*Source code is private. This page documents the work; code can be shared on request.*
