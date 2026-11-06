# Lincoln: municipal law history in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of Lincoln, Buenos Aires, Argentina, which global-law reads at `argentina/buenos-aires/lincoln/acts/`.

The municipal law of the Partido de Lincoln (Province of Buenos Aires), Argentina, as a git history: one file per article, one commit per ordinance on the day it took effect. `git log` lists the changes; checking out a date gives the text the record holds for that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ar-b-lincoln/`. The province's law is in [lexifina/argentina-buenos-aires-law](https://github.com/lexifina/argentina-buenos-aires-law) and Argentina's national law in [lexifina/argentina-law](https://github.com/lexifina/argentina-law).

The text is in Spanish, exactly as the source prints it.

## What this repository holds

1 ordinance so far, in force from 11 January 2017 to 11 January 2017, each as published in the Boletín Oficial Municipal de Lincoln, added in parts.

| Folder | Ordinance | History |
| --- | --- | --- |
| `ordenanza-259-2017/` | Ordenanza 259/2017: Apruébase la programación de los recursos y el presupuesto analítico de gastos de la Municipalidad de Lincoln, correspondiente al ejercicio … | in force 11 January 2017 |

## Source

Sistema de Boletines Oficiales Municipales (SIBOM), Subsecretaría Legal y Técnica, Secretaría General, Provincia de Buenos Aires: Boletín Oficial Municipal de Lincoln, <https://sibom.slyt.gba.gob.ar/cities/72>. SIBOM is the platform on which each municipality of the Province of Buenos Aires makes its Boletín Oficial Municipal (Ley 14.491). For each bulletin it lists the ordinances it published; each ordinance has its own page with the text as published (HTML). The site states no terms restricting reuse.

## Dates

- Each commit is dated at **noon, America/Argentina/Buenos_Aires, on the day the ordinance took effect**: the day its own vigencia clause names, or otherwise the ninth day after its publication in the Boletín Oficial Municipal de Lincoln (Código Civil y Comercial de la Nación, arts. 5 and 6).
- Each ordinance is its text as published. Later ordinances that amend it are separate folders; their changes are not merged into the earlier text.
- Versions that take effect after the retrieval day are on the `futuro` branch, never merged into `main`.

## Files

`<ordinance>/art-005.md` is Artículo 5; `encabezado.md` holds the number, the place and date, the expediente line and anything printed before Artículo 1. Signatures and annexes stay in the file of the article they follow. One paragraph per line.

## How it is checked

- Every version of every ordinance is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`.
- The letters and digits of every version equal those of the source page it was read from (read again with an independent HTML reader), so no word is lost or added.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## Limits

This is not an official publication. The binding text is the one published in the Boletín Oficial Municipal de Lincoln. Only the ordinances listed above are included, and amendments are not consolidated into the texts they amend.
