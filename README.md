# Christian Bleeker SEO-team

Een overdraagbaar team van twaalf SEO/AEO-specialisten voor **Claude Code** en **Codex**. Het pakket bevat instructies, geen klantdata, websitecode, externe accounts of automatische publicatie.

## Installeren in een klantproject

Open de **bedoelde website-repository** in Claude Code of Codex en zeg:

> Installeer alles uit https://github.com/chris-co-creators-ai/christianbleeker_seo in dit project.

De agent haalt de rest uit deze README. Als de actieve projectmap en het domein ondubbelzinnig vaststaan, gebruikt hij die; anders vraagt hij **alleen** welke projectmap en website bedoeld zijn. De URL alleen is **geen** toestemming om in de laatst geopende of een willekeurige repository te installeren. Installatie in een klantproject is een lokale bestandswijziging; commit/push van dat klantproject gebeurt alleen op diens eigen opdracht.

### Installatiecontract voor coding agents

1. Bevestig de **exacte doelproject-root en het domein** uit de gebruikersvraag en de huidige checkout. Controleer bij Git-projecten de werkelijke root met `git rev-parse --show-toplevel`. Stop bij een verschil, ambiguïteit of mogelijk verkeerde klantcontext. Gebruik deze publieke repo alleen als pakketbron, nooit als doelproject.
2. Lees deze README en de vier `SKILL.md`-bestanden. Haal de publieke repo via HTTPS op in een nieuwe tijdelijke map buiten het klantproject; gebruik geen verborgen login, token of privébron. Controleer dat de map `shared/roles/` precies twaalf Markdown-bestanden bevat, `claude/agents/` precies twaalf en beide platformmappen de skills `christianbleeker-seo` en `goseo` bevatten.
3. Doe **vóór iedere wijziging** een preflight van alle onderstaande doelpaden én de bestaande `AGENTS.md`- en `CLAUDE.md`-secties. Vergelijk ieder aanwezig doelbestand met de pakketbron. Een ontbrekend bestand kan worden toegevoegd en een identiek bestand kan blijven staan; bij **één** afwijkend bestand of een afwijkende bestaande SEO-teamsectie: stop zonder iets te kopiëren, toon het verschil en vraag hoe samen te voegen. Zo ontstaat geen half geïnstalleerd pakket. Kopieer pas na een conflictvrije preflight naar **alleen** de bevestigde doelroot.

   | Pakketbron | Doel in klantproject |
   | --- | --- |
   | `shared/roles/*.md` | `.seo-team/roles/*.md` |
   | `codex/skills/christianbleeker-seo/` | `.agents/skills/christianbleeker-seo/` |
   | `codex/skills/goseo/` | `.agents/skills/goseo/` |
   | `claude/skills/christianbleeker-seo/` | `.claude/skills/christianbleeker-seo/` |
   | `claude/skills/goseo/` | `.claude/skills/goseo/` |
   | `claude/agents/*.md` | `.claude/agents/*.md` |

4. Voeg de inhoud van `codex/AGENTS.snippet.md` **eenmaal** toe aan de bestaande `<project>/AGENTS.md`, of maak dat bestand als het ontbreekt. Doe hetzelfde voor `claude/CLAUDE.snippet.md` in `<project>/CLAUDE.md`. Behoud bestaande tekst en volg strengere projectinstructies. Gebruik de sectiekop om dubbele toevoegingen te vermijden; een al bestaande sectie met andere tekst is een preflightconflict. Niet sleutelen aan globale home-instructies.
5. Controleer de twaalf rollen, twaalf Claude-agents, vier skills, twee instructiesecties, alle rolverwijzingen en de werkelijke Git-diff. Meld precies welke bestanden zijn toegevoegd en waar conflicten of ontbrekende toegang het werk stopten. Verwijder de tijdelijke pakketkopie pas nadat de controle is afgerond. Niets deployen of extern publiceren.

Een nieuwe versie installeren volgt dezelfde conflictregel: gewijzigde klantbestanden worden niet automatisch vervangen. De rollen zijn klantneutraal; maak projectspecifieke aanvullingen in de klantrepo en laat oorspronkelijke instructies staan.

## Wanneer gebruik je wat?

| Vraag | Claude Code | Codex |
| --- | --- | --- |
| Eén gerichte SEO-taak | `/christianbleeker-seo` of een passende subagent | `$christianbleeker-seo` |
| Een volledige, gecoördineerde week | `/goseo` | `$goseo` |

De native commando's zijn pas beschikbaar **na installatie in het klantproject**; herstart de agentsessie of laad projectskills opnieuw als de tool nieuwe bestanden nog niet toont. In Claude kunnen de twaalf specialisten als subagents worden gebruikt. Codex routeert via de algemene skill naar dezelfde twaalf canonieke rolbestanden. Beide workflows volgen dezelfde overdrachtsvolgorde.

## `/goseo`: de wekelijkse keten

De workflow maakt in het **klantproject** `output/seo/YYYY-Www/` (ISO-week) met controleerbare concepten en audits. Hij leest bestaand weekwerk eerst en vult geen ontbrekende invoer of meetcijfers in.

1. **Analyse:** Connie en Dora onderzoeken onafhankelijk concurrenten en doelmarkt; Kiki maakt zoekintenties en vragen; Saar kiest één onderbouwde kans.
2. **Creatie:** Coco schrijft een concept met bronnen; Aafke herschrijft het met het directe, feitelijke antwoord eerst; Sjoerd voegt alleen passend structured data toe.
3. **Optimalisatie:** Onno maakt een publicatievoorstel; Lola en Timo controleren links en techniek; Boris levert alleen outreachvoorstellen; Rinus legt nulmeting en opvolging vast.

Een stap start pas als de vereiste eerdere output betrouwbaar beschikbaar is. `onno-ready-to-publish.md` is een **voorstel**, geen publicatie. De workflow wijzigt geen live site, `robots.txt` of AI-trainingsvoorkeuren en stuurt geen outreach zonder afzonderlijke opdracht. Een controle na 72 uur is een eerste meetpunt, niet een garantie op indexering of AI-vermelding.

### Belangrijke redactionele grenzen

- Aafke gebruikt de omgekeerde piramide: eerst het directe, geverifieerde antwoord, dan context. Circa 40–60 woorden kan een redactionele keuze zijn, maar is geen Google- of AI-searchregel.
- Sjoerd genereert geen `FAQPage` als standaard. Structured data moet passen bij zichtbaar materiaal en actuele richtlijnen.
- Timo onderscheidt zoekcrawlers van crawlers/controles voor AI-training. De site-eigenaar bepaalt de voorkeuren.
- Rinus maakt onderscheid tussen crawlbaarheid, indexering, zoekprestaties en daadwerkelijk geobserveerde AI-vermeldingen.

## De twaalf specialisten

| Naam | Specialisme |
| --- | --- |
| Saar de SEO-strateeg | Weekprioriteit en strategie |
| Kiki de Keywordkraker | Zoekintentie, onderwerpen en vragen |
| Connie de Concurrentiespeurder | Concurrentieonderzoek |
| Coco de Contentmaker | Mensgerichte conceptcontent |
| Sjoerd de Schemasmid | Passende structured data |
| Onno de Onpage-optimizer | Pagina-optimalisatievoorstel |
| Lola de Linklegger | Interne linkstructuur |
| Aafke de Antwoordarchitect | Feitelijke antwoord-eerst-redactie |
| Rinus de Resultatenreporter | Nulmeting en resultaatopvolging |
| Boris de Backlinkbouwer | Legitieme PR-/linkkansen |
| Timo de Techniektester | Technische SEO en crawlercontrole |
| Dora de Doelmarkt-detective | Doelgroep, lokaal en internationaal |

De unieke rolbeschrijvingen staan in [`shared/roles/`](shared/roles/). Ze zijn bewust geen verzamelmap met klantcases: elk klantproject levert zijn eigen feiten, website, doelgroep en toestemming.

## Onderbouwing

Voor AI-zoekfuncties blijven [Google's gewone SEO-principes](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide) leidend; er is geen gegarandeerde plek in AI-antwoorden. [Google's wijziging van 8 mei 2026](https://developers.google.com/search/updates#may-2026) meldt dat FAQ-rich results vanaf 7 mei niet meer verschijnen. De crawlerrollen zijn beschreven door [OpenAI](https://developers.openai.com/api/docs/bots), [Anthropic](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) en [Google](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers). Voor de platformspecifieke installatiepaden: [Claude Code skills](https://code.claude.com/docs/en/skills), [Claude Code subagents](https://code.claude.com/docs/en/sub-agents) en [Codex skills](https://learn.chatgpt.com/docs/build-skills).
