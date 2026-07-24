# simplified-tech-doc

A Claude skill that rewrites existing documentation — or drafts new documentation —
following the idea behind [ASD-STE100 Simplified Technical English](https://www.asd-ste100.org/).

## What it does

Technical documentation is often read by people whose first language is not English,
and is frequently translated. Simplified Technical English (STE) is a controlled-language
standard built for exactly that audience: a dictionary of roughly 900 approved words,
each with one meaning and one part of speech, plus a set of writing rules covering
sentence length, tense, voice, and structure.

This skill applies those rules to your docs. It has two modes:

- **Rewrite** — all technical facts, values, part numbers, code, commands, and file
  paths are preserved exactly. Only the language and structure change.
- **Author** — new content written directly in STE.

Technical nouns and technical verbs (part names, commands, product names, process verbs)
are permitted by the standard and are kept as-is, so precision is not lost.

Ambiguity in a source document is flagged rather than guessed at.

## Example

**Before:**

> In order to get started, you'll want to go ahead and carefully make sure the device
> has been properly powered down before attempting to remove the housing, as failure
> to do so could potentially result in damage.

**After:**

> Before you remove the housing, disconnect the power.
> If you do not disconnect the power, you can cause damage to the device.

## Installation

**Claude Code / agent skills:** clone this repository into your skills directory so that
`SKILL.md` sits inside a folder named `simplified-tech-doc`.

```
git clone https://github.com/birchamp/simplified-tech-doc-skill.git simplified-tech-doc
```

**Any other assistant:** copy the body of `SKILL.md` (everything below the YAML
frontmatter) and use it as a system prompt or custom instruction.

## Limitations

This skill encodes the *rules* of STE, not the official dictionary. No language model
has the approved word list memorized, so output will be close to STE but is not
certified compliant. For formal or regulated deliverables, run the result through a
dedicated STE checker.

## About the standard

ASD-STE100 Simplified Technical English is maintained by the Simplified Technical
English Maintenance Group (STEMG), a working group of ASD (Aerospace, Security and
Defence Industries Association of Europe). The current release is Issue 9
(15 January 2025), which carries the subtitle *Standard for Technical Documentation*.

The standard is available at no cost from [asd-ste100.org](https://www.asd-ste100.org/).

**This project is not affiliated with, endorsed by, or sponsored by ASD or the STEMG.**
ASD-STE100 is owned by ASD. This repository contains original instructions and
paraphrased guidance only — it does not reproduce the approved dictionary or the text
of the standard. To use STE properly, request the official copy from ASD.

## License

The contents of this repository are released under the MIT License. See [LICENSE](LICENSE).

This license applies to the material in this repository only. It does not extend to
ASD-STE100, which remains the property of ASD.
