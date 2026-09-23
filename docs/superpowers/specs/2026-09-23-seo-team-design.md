# Christian Bleeker SEO-team — ontwerp

## Doel

Een zelfstandige, publieke repository met twaalf Nederlandstalige SEO-rollen, bruikbaar in zowel Claude Code als Codex. Een ontwikkelaar kan een coding agent alleen de GitHub-link en de opdracht "installeer alles" geven. De inhoud is toepasbaar op uiteenlopende websites en bevat geen klantinformatie, credentials, vaste integraties of historische projectbestanden.

## Opzet

- `README.md`: installatiecontract voor zowel mensen als coding agents, gebruiksmomenten, benodigde invoer en verificatie.
- `shared/roles/`: twaalf canonieke, algemene SEO-rolinstructies.
- `codex/skills/christianbleeker-seo/SKILL.md`: Codex-router die alleen de relevante rol(len) laadt.
- `claude/skills/christianbleeker-seo/SKILL.md`: Claude-router met dezelfde werkwijze.
- `claude/agents/`: twaalf Claude Code-subagents met eigen beschrijvingen en een verwijzing naar hun canonieke rol.
- `claude/commands/seo-week.md`: handmatige weekaansturing.
- `codex/AGENTS.snippet.md` en `claude/CLAUDE.snippet.md`: korte verwijzingen voor bestaande projectinstructies.
- `docs/superpowers/specs/`: dit goedgekeurde ontwerp.

De installatie kopieert `shared/roles` naar `<project>/.seo-team/roles`, de Codex-skill naar `<project>/.agents/skills/christianbleeker-seo`, de Claude-skill naar `<project>/.claude/skills/christianbleeker-seo` en de subagents en weekopdracht naar hun native Claude-locaties. Bestaande `AGENTS.md` en `CLAUDE.md` worden behouden; alleen een korte verwijzing wordt toegevoegd als die nog ontbreekt. Bij afwijkende doelbestanden stopt de installerende agent voor controle in plaats van ze te overschrijven. Er is geen installatiecode nodig: de README geeft de uitvoerbare kopieer- en controle-instructies aan de coding agent.

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

Elke canonieke rol beschrijft wanneer die geldt, invoer, werkwijze, concrete output, overdracht en veiligheidsgrenzen. De platform-skill kiest op grond van de taak één rol of een kleine combinatie; de weekaansturing gebruikt het team, maar draait niet automatisch. Claude Code kan de twaalf rollen bovendien als afzonderlijke subagents oproepen. Codex gebruikt één vindbare skill met gerichte rolreferenties om de skill-lijst compact te houden.

## Privacy en kwaliteitscontrole

De rolinstructies worden opnieuw geschreven. Er wordt geen bestaand projectverleden overgenomen. Voor publicatie controleren we alle tracked files en Git-commits op klantnamen, domeinen, persoonsinformatie, credentials en vaste integraties. We controleren tevens dat alle twaalf rollen en Claude-wrappers aanwezig zijn, beide skills valide frontmatter hebben, de weekaansturing aanwezig is en de README-installatiepaden overeenkomen met de werkelijke bestanden. Daarna testen we een schone proefinstallatie in een tijdelijke projectmap met bestaande instructiebestanden, inclusief gedrag bij bestandsconflicten. De GitHub-repository wordt pas gepubliceerd nadat die controles slagen.

## Herstelpad

Bij een fout vóór publicatie blijft de inhoud lokaal en kan ze worden gecorrigeerd. Na publicatie is de GitHub-repository afzonderlijk van andere projecten; een fout kan worden hersteld met een opvolgcommit of, bij onbedoelde gevoelige gegevens, onmiddellijke verwijdering van de publieke repository en credentialrotatie waar nodig.
