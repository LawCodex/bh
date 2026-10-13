# Bahrain — LawCodex (تشريعات مملكة البحرين)

Bahraini legislation as plain Markdown, in Arabic. Part of [LawCodex](https://github.com/LawCodex):
one repository per jurisdiction.

> **Coverage is minimal, because the official sources do not allow republication.** The official
> legislation database of the **Legislation and Legal Opinion Commission** (هيئة التشريع والرأي
> القانوني, [lloc.gov.bh](https://www.lloc.gov.bh)) is complete, technically easy to use and
> reachable, but its terms of use forbid what LawCodex does (see below). This repository therefore
> holds only two texts, taken from **Arabic Wikisource**, a volunteer, unofficial transcription.
> Check them against the official text before you rely on them.

- Retrieved: **2026-10-13**

## Coverage

| File | Text | Notes |
| --- | --- | --- |
| `ar/constitution/2002-constitution.md` | دستور مملكة البحرين: the Constitution of the Kingdom of Bahrain, promulgated 14 February 2002 (125 articles) | Text as promulgated in 2002. The constitutional amendments of 2012 and 2017 are **not** incorporated. |
| `ar/laws/2006/2006-22.md` | قانون رقم (22) لسنة 2006 بشأن حماية حقوق المؤلف والحقوق المجاورة: Law No. 22 of 2006 on Copyright and Related Rights | Text as enacted; later amendments are not incorporated |

The Wikisource transcription of the Constitution omits most hamzas and contains a few typing
errors (e.g. "ظم" for "تنظم" in Article 1(c)). It is reproduced as is. The front matter of each
file records the Wikisource revision it was built from (`source_revision`).

## Why the official sources were not used

**Legislation and Legal Opinion Commission (lloc.gov.bh).** The site offers every law,
decree-law, decree, royal order and decision. It has an HTML text of each instrument
(`/Legislation/HTM/<id>`), a consolidated Word file (`/FullAr/<id>.docx`), English versions
(`/FullEn/<id>.docx`) and a scan (`/PDF/<id>.pdf`). Its
[terms and conditions](https://www.lloc.gov.bh/page/الشروط%20والاحكام) (last updated 25 April 2025)
state:

> محتويات هذا الموقع بما في ذلك المعلومات والبرامج محمية بموجب حقوق النشر والعلامات التجارية.
> يعتبر تعديل أي من المحتوى أو استخدام المحتوى لأية أغراض أخرى انتهاكًا لهيئة التشريع والرأي
> القانوني - مملكة البحرين لحقوق النشر وحقوق الملكية الفكرية.

("The contents of this site, including information and software, are protected by copyright …
Modifying any of the content, or using it for any other purpose, is an infringement of the
Commission's copyright and intellectual-property rights.")

LawCodex's work means converting the texts and republishing them, so the site was not crawled.
LawCodex would need the Commission's written permission to use it.

**Council of Representatives (nuwab.bh).** It published the Constitution (archived copy of
`/LegislativeGroup/Pages/Constitution.aspx`, 2014), but its terms of use forbid copying or
republishing its content without prior written permission ("لا يسمح بنسخ محتويات هذا الموقع أو
إعادة نشرها … بدون إذن كتابي مسبق"). The live site answers HTTP 403. Not used.

**Shura Council (shura.bh).** Its pages are rendered entirely in JavaScript, and no legislation
texts could be found in them.

Note that Bahraini law itself excludes legislation from copyright protection: see Article 4(b) of
Law No. 22 of 2006, [`ar/laws/2006/2006-22.md`](ar/laws/2006/2006-22.md), which excludes
"legislation, judicial rulings and decisions … international agreements and all other official
documents, as well as official translations of any of them". The restriction comes from the
websites' terms of use, not from copyright in the laws.

## Structure

```
ar/constitution/2002-constitution.md
ar/laws/<year>/<year>-<number>.md
```

Parts (الباب), chapters (الفصل) and sections (الفرع) are headings, and each article (مادة)
is a heading one level below.

## Licence

These are official texts of the Kingdom of Bahrain and are not protected by copyright (see above).
The transcriptions come from Wikisource (CC BY-SA 4.0 for any editorial contribution); every file
links its Wikisource page.

## Regenerating

```sh
pip install -r scripts/requirements.txt
python scripts/bh_wikisource.py /path/to/raw .
```
