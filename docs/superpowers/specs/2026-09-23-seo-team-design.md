# Christian Bleeker SEO-team — ontwerp

## Doel

Een zelfstandige, publieke repository met twaalf Nederlandstalige SEO-rollen, bruikbaar in zowel Claude Code als Codex. Een ontwikkelaar kan een coding agent alleen de GitHub-link en de opdracht "installeer alles" geven. De inhoud is toepasbaar op uiteenlopende websites en bevat geen klantinformatie, credentials, vaste integraties of historische projectbestanden.

## Opzet

- `README.md`: installatiecontract voor zowel mensen als coding agents, gebruiksmomenten, benodigde invoer en verificatie.
- `shared/roles/`: twaalf canonieke, algemene SEO-rolinstructies.
- `codex/skills/christianbleeker-seo/SKILL.md`: Codex-router die alleen de relevante rol(len) laadt.
- `codex/skills/goseo/SKILL.md`: herhaalbare SEO/AEO-weekworkflow, in Codex aanroepbaar als `$goseo`.
- `claude/skills/christianbleeker-seo/SKILL.md`: Claude-router met dezelfde werkwijze.
- `claude/skills/goseo/SKILL.md`: dezelfde weekworkflow, in Claude Code aanroepbaar als `/goseo`.
- `claude/agents/`: twaalf Claude Code-subagents met eigen beschrijvingen en een verwijzing naar hun canonieke rol.
- `codex/AGENTS.snippet.md` en `claude/CLAUDE.snippet.md`: korte verwijzingen voor bestaande projectinstructies.
- `docs/superpowers/specs/`: dit goedgekeurde ontwerp.

De installatie kopieert `shared/roles` naar `<project>/.seo-team/roles`, de twee Codex-skills naar `<project>/.agents/skills/`, de twee Claude-skills naar `<project>/.claude/skills/` en de Claude-subagents naar `<project>/.claude/agents/`. Bestaande `AGENTS.md` en `CLAUDE.md` worden behouden; alleen een korte verwijzing wordt toegevoegd als die nog ontbreekt. De installerende agent controleert **alle** doelpaden en bestaande instructiesecties vóór de eerste kopieeractie; bij één afwijking stopt hij zonder gedeeltelijke installatie. Er is geen installatiecode nodig: de README geeft de uitvoerbare kopieer- en controle-instructies aan de coding agent.

Er wordt geen applicatie, database, dependency of automatische publicatie toegevoegd. Elke agent werkt met de feitelijk beschikbare projectcontext en vraagt alleen ontbrekende informatie die niet veilig uit het project of de website te achterhalen is. Adviezen onderscheiden brongegevens, aannames en voorstellen. Externe communicatie, wijzigingen aan websites en publicatie vergen een opdracht die die handeling dekt.

## Agenten

| Vakgebied | Naam | Bestand |
|---|---|---|
| SEO-strategie | Saar de SEO-strateeg | `saar-seo-strateeg.md` |
| Zoekwoorden | Kiki de Keywordkraker | `kiki-keywordkraker.md` |
| Concurrentieanalyse | Connie de Concurrentiespeurder | `connie-concurrentiespeurder.md` |
| Content | Coco de Contentmaker | `coco-contentmaker.md` |
| Structured data | Sjoerd de Schemasmid | `sjoerd-schemasmid.md` |
| On-page SEO | Onno de Onpage-optimizer | `onno-onpage-optimizer.md` |
| Interne links | Lola de Linklegger | `lola-linklegger.md` |
| AI-zoekresultaten | Aafke de Antwoordarchitect | `aafke-antwoordarchitect.md` |
| Rapportage | Rinus de Resultatenreporter | `rinus-resultatenreporter.md` |
| Backlinks | Boris de Backlinkbouwer | `boris-backlinkbouwer.md` |
| Technische SEO | Timo de Techniektester | `timo-techniektester.md` |
| Lokale en internationale doelmarkten | Dora de Doelmarkt-detective | `dora-doelmarkt-detective.md` |

Elke canonieke rol beschrijft wanneer die geldt, invoer, werkwijze, concrete output, overdracht en veiligheidsgrenzen. De algemene platform-skill kiest op grond van de taak één rol of een kleine combinatie. Claude Code kan de twaalf rollen bovendien als afzonderlijke subagents oproepen. Codex gebruikt één vindbare algemene skill met gerichte rolreferenties om de skill-lijst compact te houden.

## `/goseo`-workflow

De handmatige workflow gebruikt `output/seo/YYYY-Www/` met ISO-jaar en week. Hij controleert eerst doelproject, domein, beschikbare bronnen en bestaande uitvoer. De drie fasen zijn:

1. Analyse: Connie en Dora onderzoeken concurrenten en doelmarkt; Kiki maakt zoekintenties en natuurlijke vragen; Saar kiest een onderbouwde weekprioriteit.
2. Creatie: Coco maakt alleen voor de gekozen kans een concept; Aafke zet een direct, feitelijk antwoord voorop en onderbouwt claims; Sjoerd kiest alleen schema dat bij zichtbare inhoud en actuele zoekmachinerichtlijnen past.
3. Optimalisatie: Onno maakt een publicatievoorstel; Lola en Timo auditen links en technische vindbaarheid; Boris maakt uitsluitend relevante, legitieme outreachvoorstellen; Rinus levert een nulmeting en vervolgmoment.

Een volgende stap leest de vorige bestanden en markeert ontbrekende gegevens expliciet. Een fase mag geen ontbrekend bronbestand of meetcijfer verzinnen. Parallel werken is alleen toegestaan voor onafhankelijke stappen en alleen als de runtime dat ondersteunt. De workflow schrijft concepten en audits; sitepublicatie, wijziging van crawler- of trainingsvoorkeuren en externe outreach vereisen een afzonderlijke opdracht. Een controle na 72 uur kan een eerste meetpunt zijn maar is geen indexatiegarantie.

Aafkes antwoord-eerst-stijl is een redactiekeuze, geen vaste 40–60-woordenregel of gegarandeerde AI-vermelding. `FAQPage` is geen standaardoutput: [Google beëindigde de FAQ-rich-results in mei 2026](https://developers.google.com/search/updates#may-2026). Voor Google AI-zoekfuncties gelden volgens [Google Search Central](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide) de gewone SEO-beginselen. Timo onderscheidt zoektoegang van trainingsvoorkeuren volgens de crawlerdocumentatie van [OpenAI](https://developers.openai.com/api/docs/bots), [Anthropic](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) en [Google](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers).

## Privacy en kwaliteitscontrole

De rolinstructies worden opnieuw geschreven. Er wordt geen bestaand projectverleden overgenomen. Voor publicatie controleren we alle tracked files en Git-commits op klantnamen, domeinen, persoonsinformatie, credentials en vaste integraties. We controleren tevens dat alle twaalf rollen en Claude-wrappers aanwezig zijn, beide skills valide frontmatter hebben, de weekaansturing aanwezig is en de README-installatiepaden overeenkomen met de werkelijke bestanden. Daarna testen we een schone proefinstallatie in een tijdelijke projectmap met bestaande instructiebestanden, inclusief gedrag bij bestandsconflicten. De GitHub-repository wordt pas gepubliceerd nadat die controles slagen.

## Herstelpad

Bij een fout vóór publicatie blijft de inhoud lokaal en kan ze worden gecorrigeerd. Na publicatie is de GitHub-repository afzonderlijk van andere projecten; een fout kan worden hersteld met een opvolgcommit of, bij onbedoelde gevoelige gegevens, onmiddellijke verwijdering van de publieke repository en credentialrotatie waar nodig.
