# CLAUDE.md — Seiltur Kroatia

Prosjekt: to ukers familieseilas (5 pers.) fra Pula tur/retur, sommer 2026. Repoet er både **planleggingsverktøy** (seilplan, havneguide, kart) og **kildemateriale for NotebookLM-lydbok** (historie + havneerfaringer). Alt innhold skrives på **norsk bokmål**. Stedsnavn beholder kroatisk skrivemåte (Telašćica, Lošinj); etablerte begreper holder seg konsistente gjennom repoet (bura, jugo, maestral, konoba, bøyefelt).

## Struktur

- `seilplan.md` — tre ruter (A: stor runde m/Kornati, B: Kvarner, C: Istria) med beslutningspunkter. Etappedistanser i nm skal være realistiske — sjekk at en etappe faktisk er seilbar (man kan ikke krysse øyer; Cres by nås via Osor-kanalen eller rundt nordspissen).
- `havner/<område>/<sted>.md` — én fil per øy/område i rutas rekkefølge. Fast format: `## <Havn>` med punktene Type / Le for–utsatt for / Fasiliteter / Notater, en avsluttende **Ved bura / Ved jugo**-linje, og nederst `## Stemmer fra nettet` (se under).
- `lydbok/NN-<tema>.md` — historiekapitler skrevet for opplesning.
- `kart/seiltur-kroatia.kml` + `.gpx` — samme innhold som havneguiden i kartform.

**Synk-regel:** Endres et faktum om en havn (navn, plassering, le-retning, status), skal endringen speiles tre steder: havnefilen, `kart/`-filene (KML **og** GPX) og hurtigtabellen i `havner/README.md`. Kartfilene valideres med en XML-parser før commit. KML bruker lon,lat-rekkefølge; GPX bruker lat/lon-attributter og ASCII-navn (ingen æøå/diakritika i `<name>`).

## NotebookLM-regler (gjelder lydbok/ og «Stemmer fra nettet»)

NotebookLM henter isolerte tekstbiter og lager lyd av prosa — derfor:

1. **Flytende prosa, ikke punktlister**, i alt som skal lyttes til. Praktiske seksjoner (Type/Le for) kan være punkter; de er for oppslag, ikke opplesning.
2. **Hver seksjon skal stå på egne ben.** Ingen anaforiske referanser over seksjonsgrenser («som nevnt i forrige kapittel», «denne bukta» som åpning). Navngi tingen eksplisitt («Telašćica-bukta», «buraen»).
3. **Gjenta definisjoner kort ved gjenbruk** — én setning («buraen, den kalde fallvinden fra nordøst, …»), ikke full forklaring på nytt.
4. **Temaspesifikke overskrifter**: «Sammendrag: Kornati», ikke «Sammendrag». Generiske overskrifter gjentatt på tvers av filer ødelegger gjenfinning.
5. **Last opp Markdown-filene direkte som kilder, én fil per kilde** — aldri PDF (topptekster/sidetall forurenser tekstuttrekket). PDF er for menneskelig lesing/utskrift.
6. Konseptrekkefølge: grunnleggende før avansert — lydbok-kapittel 1 (storhistorien) forutsettes kjent i kapittel 2–5; innenfor ett kapittel forklares alt som brukes.

## Research-regler («Stemmer fra nettet» m.m.)

- **Utforsk før du skriver.** Ny havne-/stedsinfo baseres på websøk (Navily, Cruisers Wiki, NoForeignLand, Tripadvisor, seilforum, offisielle parksider), ikke på antakelser. Parallelle agenter per område fungerer godt.
- **Aldri dikt opp sitater eller erfaringer.** Gjengi bare det som faktisk er funnet; attribuer løst («en seiler på Navily…», «flere på Cruisers Forum…»). Tynt kildegrunnlag sies ærlig i teksten.
- **Priser og regler dateres** («2025-priser», «per 2026-prislisten») — de endres årlig.
- Avslutt hver «Stemmer fra nettet»-seksjon med kildelinje: `*Kilder: …*` (kildenavn, ikke URL-er).
- Finner research en faktafeil i eksisterende tekst: rett den der den står (og husk synk-regelen).
- Standardforbehold står i `havner/README.md` og `kart/README.md`: posisjoner og rutelinjer er for orientering — Navily/sjøkart/havnekontor er fasit. Ikke svekk disse forbeholdene.

## Større skrivejobber

For nye bøker/kapittelserier (f.eks. en samlet reisebok): følg fasene fra skill-filen — (1) avklar mål, omfang, språk og om NotebookLM-modus gjelder; (2) research; (3) **presenter kapitteldisposisjon for godkjenning før skriving**; (4) skriv én fil per kapittel, nummerert `NN-tema.md`; (5) ev. PDF.

## PDF («cockpit-utgaven»)

PDF genereres med pandoc + xelatex (sjekk `which pandoc && which xelatex`; installeres via `brew install pandoc` og `brew install --cask basictex`). Lag `metadata.yaml` med `lang: nb`, `documentclass: report`, marger 1in, fancyhdr-topptekst, og bygg:

```bash
pandoc <filer i rekkefølge> --pdf-engine=xelatex --toc --number-sections \
  --metadata-file=metadata.yaml -o seiltur-kroatia.pdf
```

Verifiser at filen finnes og har størrelse før du melder suksess. PDF-en er for utskrift/lesing — aldri NotebookLM-kilde.

## Git

Repo: `git@github.com:trefsahl/kroatia-seiltur.git` (push til `main` er etablert praksis her). Commit-meldinger på norsk, med beskrivende brødtekst ved substansielle endringer. `.DS_Store` er gitignored.

## Vanlige feil å unngå

- Skrive stedsinfo fra hukommelsen når oppgaven ber om research — søk først.
- Punktlister i tekst som skal bli lyd.
- Etapper/posisjoner som ikke stemmer med geografien (valider mot kart).
- Oppdatere havnefil uten å oppdatere KML/GPX/hurtigtabell.
- Generiske seksjonsoverskrifter, bare tilbakereferanser, eller udaterte priser.
- Laste opp PDF til NotebookLM.
