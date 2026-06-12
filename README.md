# Seiltur Kroatia — Pula tur/retur, to uker

Alt materiale til familieturen: seilplan med vær-alternativer, og lydbok-kilder for NotebookLM.

## Innhold

- [seilplan.md](seilplan.md) — tre alternative ruter (A: stor runde m/Kornati, B: Kvarner-runden, C: Istria-kysten), beslutningspunkter og værguide
- `havner/` — havneguide, én fil per øy/område i rutas rekkefølge: marinaer, bykaier, bøyefelt og ankringsbukter med le-retninger for bura/jugo/maestral. Start med [havner/README.md](havner/README.md) (inkl. hurtigtabell «hvor gjemmer dere dere» per vindretning)
- `kart/` — [KML for Google My Maps](kart/seiltur-kroatia.kml) og [GPX for Navionics/kartplotter](kart/seiltur-kroatia.gpx): alle havnene som punkter + rutene A/B/C som linjer. Importveiledning i [kart/README.md](kart/README.md)
- `lydbok/` — fem kapitler skrevet som kildemateriale for NotebookLM:
  1. [Adriaterhavets historie](lydbok/01-adriaterhavets-historie.md) — den lange linjen: illyrere, Roma, Venezia, Østerrike, Jugoslavia, Kroatia
  2. [Pula og Istria](lydbok/02-pula-og-istria.md) — Pula, Brijuni, Rovinj, Limski kanal, Vrsar, Poreč
  3. [Kvarner-øyene](lydbok/03-kvarner-oyene.md) — Unije, Susak, Lošinj, Cres/Osor, Ilovik, Silba, Rab, Krk, Senj
  4. [Mot sør](lydbok/04-mot-sor-zadar-og-kornati.md) — Molat, Dugi otok, Telašćica, Kornati, Zadar (rute A)
  5. [Livet langs kysten](lydbok/05-livet-langs-kysten.md) — mat, vind, klapa, språk, sjømannskultur

## Slik lager dere lydboken i NotebookLM

1. Gå til [notebooklm.google.com](https://notebooklm.google.com) og opprett en ny notatbok, f.eks. «Seiltur Kroatia».
2. Sett **utdataspråk til norsk**: Innstillinger (tannhjulet) → Output language → Norsk. Da blir lydoversikter generert på norsk.
3. Last opp filene i `lydbok/`-mappen som kilder (dra og slipp `.md`-filene — NotebookLM tar dem som tekstfiler; alternativt lim inn innholdet som «Copied text»). Last gjerne også opp `seilplan.md`, så kan lyden knyttes til ruta deres.
4. Klikk **Audio Overview / Lydoversikt → Generate**. Det gir én podcast-aktig episode basert på alle kildene.

### Tips for bedre episoder

- **Én episode per kapittel:** Bruk «Customize»-knappen før du genererer, og skriv f.eks. *«Lag en episode kun om kapittel 3, Kvarner-øyene. Fortell historiene levende for en norsk familie med barn som seiler dit.»* Generer på nytt for hvert kapittel — eller lag én notatbok per kapittel hvis dere vil beholde alle episodene samtidig.
- **Lengde:** Be om lengre episoder i customize-feltet («grundig og lang gjennomgang») — standard er ofte 10–15 min.
- **Last ned** episodene som lydfiler i appen/nettleseren før avreise — mobildekningen er god langs kysten, men roaming-data er dyrebar og ankerbukter har sine dødsoner.
- NotebookLM-appen (iOS/Android) kan spille episodene offline om bord.

### Forslag til «episodeliste» for turen

| Når | Episode |
|---|---|
| Flyet/kjøreturen ned | Kapittel 1: Det store bildet |
| Dag 1–2 i Pula | Kapittel 2: Pula og Istria |
| Kryssingen til Unije | Kapittel 3: Kvarner-øyene |
| Kvelden på Silba (beslutningspunktet!) | Kapittel 4: Mot sør |
| En stille fjaka-ettermiddag | Kapittel 5: Livet langs kysten |
