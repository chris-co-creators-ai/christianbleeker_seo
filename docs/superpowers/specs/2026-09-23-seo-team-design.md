# Christian Bleeker SEO-team — ontwerp

## Doel

Een zelfstandige, publieke repository met twaalf Nederlandstalige SEO-agenten en één handmatige weekaansturing. De inhoud is toepasbaar op uiteenlopende websites en bevat geen klantinformatie, credentials, vaste integraties of historische projectbestanden.

## Opzet

- `README.md`: doel, installatie in een eigen project, benodigde invoer en grenzen.
- `.claude/agents/`: twaalf losse Markdown-agentdefinities met frontmatter en elk één expertisegebied.
- `.claude/commands/seo-week.md`: handmatige coördinatie van onderzoek, prioritering en rapportage.
- `docs/superpowers/specs/`: dit goedgekeurde ontwerp.

Er wordt geen applicatie, database, dependency of automatische publicatie toegevoegd. Elke agent werkt met de feitelijk beschikbare projectcontext en vraagt ontbrekende gegevens uit. Adviezen onderscheiden brongegevens, aannames en voorstellen. Externe communicatie, wijzigingen aan websites en publicatie vergen aparte toestemming van de eigenaar.

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

Elke agent beschrijft invoer, werkwijze, concrete output, overdracht en veiligheidsgrenzen. De weekaansturing gebruikt de twaalf rollen als specialistenteam, maar draait niet automatisch.

## Privacy en kwaliteitscontrole

De agentbestanden worden opnieuw geschreven. Er wordt geen bestaand projectverleden overgenomen. Voor publicatie controleren we alle tracked files en Git-commits op klantnamen, domeinen, persoonsinformatie, credentials en vaste integraties. We controleren tevens dat alle twaalf definities en de weekaansturing aanwezig zijn, frontmatter leesbaar is en de README overeenkomt met de werkelijke bestanden. De GitHub-repository wordt pas gepubliceerd nadat die controles slagen.

## Herstelpad

Bij een fout vóór publicatie blijft de inhoud lokaal en kan ze worden gecorrigeerd. Na publicatie is de GitHub-repository afzonderlijk van andere projecten; een fout kan worden hersteld met een opvolgcommit of, bij onbedoelde gevoelige gegevens, onmiddellijke verwijdering van de publieke repository en credentialrotatie waar nodig.
