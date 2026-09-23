# SEO Team Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publiceer een klantneutraal SEO/AEO-team met twaalf rollen, veilige installatie en een native weekcommando voor Claude Code en Codex.

**Architecture:** `shared/roles/` is de enige bron voor rolgedrag. De twee platforms hebben korte skills die naar die rollen verwijzen; Claude krijgt daarnaast dunne subagent-wrappers. De README is het installatiecontract en vereist een expliciet doelproject.

**Tech Stack:** Markdown, YAML-frontmatter, Git, GitHub CLI; geen runtime-dependencies of installer-script.

## Global Constraints

- De doelmap is een nieuwe, afzonderlijke map `christianbleeker_seo` op het bureaublad; wijzig de bronrepo niet.
- Geen klantnaam, privédomein, toegangssleutel of bron-Gitgeschiedenis in de publieke repo.
- Publiceer geen klantwebsite, wijzig geen crawlerinstellingen en stuur geen outreach vanuit de SEO-workflow.
- Claude gebruikt `/goseo`; Codex gebruikt `$goseo`.
- Ontbrekende feiten en meetgegevens blijven expliciet onbekend.

---

### Task 1: Canonieke rollen

**Files:** Maak de twaalf bestanden in `shared/roles/` met de slugs uit de ontwerpspecificatie.

**Interface:** Elke rol bevat trigger, vereiste invoer, werkwijze, overdracht/output en grenzen. Aafke hanteert antwoord-eerst zonder valse 40–60-woordenclaim; Timo onderscheidt zoekcrawlers van trainingscrawlers; Rinus belooft geen indexatie.

- [x] Schrijf vóór de rollen een toepassingsscenario zonder skill en noteer waar de grens gemist wordt.
- [x] Maak de twaalf rolbestanden met unieke verantwoordelijkheden.
- [x] Controleer met `find shared/roles -name '*.md' | wc -l` dat het er precies twaalf zijn en lees de drie risicorollen terug.
- [x] Commit de rollen apart.

### Task 2: Native ingangen

**Files:** Maak `codex/skills/christianbleeker-seo/SKILL.md`, `codex/skills/goseo/SKILL.md`, `claude/skills/christianbleeker-seo/SKILL.md`, `claude/skills/goseo/SKILL.md`, `claude/agents/*.md`, `codex/AGENTS.snippet.md` en `claude/CLAUDE.snippet.md`.

**Interface:** Skills lezen geïnstalleerde rollen uit `<project>/.seo-team/roles/`; Claude-wrappers verwijzen naar exact één rol. `goseo` schrijft concepten/audits in `<project>/output/seo/YYYY-Www/` en bewaakt fase-afhankelijkheden.

- [x] Leg de bestandsovergangen en handmatige stopgrenzen in beide `goseo`-skills vast.
- [x] Maak de twee algemene router-skills en beide projectinstructie-snippets.
- [x] Maak twaalf dunne Claude-subagent-wrappers met correcte rolverwijzing.
- [x] Valideer de vier skills met `quick_validate.py` en controleer alle rolverwijzingen.
- [x] Test een risicoscenario met de nieuwe skill-instructies; herstel afwijkingen.
- [x] Commit de native ingangen apart.

### Task 3: Zelfinstallerende README en publicatie

**Files:** Maak `README.md`; wijzig alleen documentatie als verificatie een gat blootlegt.

**Interface:** De README bevat een direct kopieerbare installatievraag met GitHub-URL en exact doelproject, veilige kopieerlocaties, conflictregels, verificatie, gebruiksmomenten en de commando's voor beide tools.

- [x] Schrijf de installatie- en gebruiksinstructies met niet-destructieve conflictafhandeling.
- [x] Controleer alle paden, aantallen, frontmatter en een proefinstallatie in een tijdelijke doelmap.
- [x] Scan alle tracked inhoud én Gitgeschiedenis op herleidbare klantgegevens en geheimen.
- [ ] Commit de README, bevestig een schone werkboom en maak daarna pas de publieke GitHub-repo aan.
- [ ] Lees GitHub-reponaam, URL en publieke zichtbaarheid onafhankelijk terug.
