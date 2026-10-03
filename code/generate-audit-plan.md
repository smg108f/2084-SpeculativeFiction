# Cowork Prompt: Generate Apotheosis Audit + Mortal Recertification Plan

## Your Task

You are an agent working on the 2084 speculative fiction project. Given an entity name (person or organization), you will:

1. Read the project's worldbuilding context
2. Look up the entity in the appropriate data file
3. Research the entity using current web sources
4. Write an Apotheosis Audit file to `audits/`
5. Write a Mortal Recertification Plan file to `plans/`

Both files should be written as if produced by the Human Protection Bureau (HPB) — a bureaucratic agency in 2084 that monitors wealth concentration and enforces the Demi-God Act of 2034. The tone is formal, dry, slightly ominous, and occasionally sardonic. This is speculative fiction grounded in real current data.

---

## Step 1: Read Context Files

Before writing anything, read these files from the project root:

- `files/2084 (setting).md` — the worldbuilding document. This defines the HPB, Demi-God classification, Ascension thresholds, Flotillas, Saints, Slayers, and the Whuffie economy.
- `files/Citizen's Guide to Avoiding Ascension.md` — the HPB's public-facing advisory. Use this for vocabulary and tone.
- `code/audit-templates.md` — the canonical format for both output files. Follow these templates closely.

Also skim one existing audit and one existing plan for voice calibration:
- `audits/MARC ANDREESSEN (aa.12026.02).md`
- `plans/MARC ANDREESSEN (mrp.12026.02).md`

---

## Step 2: Look Up the Entity in the Data

The data files live in `data/`. Choose the right file based on the entity type:

| File | Use for |
|---|---|
| `cb-lions.csv` | Individuals with ~$100B+ net worth |
| `b-lions.csv` | Individuals with ~$1B–$100B net worth |
| `cb-companies.csv` | Companies/orgs with ~$100B+ market cap or endowment |
| `b-companies.csv` | Companies/orgs with ~$1B–$100B market cap |
| `nonprofits.csv` | Major foundations and endowments |

If the entity is not in any data file, proceed with web research only and note the absence in `data-notes`.

Key fields to extract if present:
- `rank-value` — current estimated net worth / market cap
- `patron-source` / `patron-industry` — primary wealth source
- `capitalist_origin-story` — origin narrative
- `firstseen-country` / `lastseen-country` — nationality / current base
- `capitalist-currentage` — age
- `person_age-group` — archetype stage (childhood / student / householder / teacher / advisor / phantasim)
- `capitalist_consort-name` — partners (useful for calculating family wealth concentration)
- `evolution-value_descendant-count` — number of children / heirs
- `data-notes` — any flags, controversies, or known data gaps

---

## Step 3: Research the Entity

Use web search to gather current information. You do not need to find everything — billionaires and powerful organizations are secretive, and some actively scrub information. Take best guesses where reasonable and note uncertainty.

Useful research angles:
- Current net worth and primary asset breakdown
- Recent philanthropy or public-benefit actions (the "Saintly Pivot" evidence)
- Political activity, lobbying, PAC spending, or government relationships
- Any public statements about wealth, society, or the future that could qualify as "Deity-Adjacent Rhetoric"
- Known preparations for exit (private islands, bunkers, seastead investments, space programs, second passports, offshore structures)
- Controversies, legal exposure, or reputational risks
- Number of heirs and family wealth structure

Spend no more than 4–6 searches. Move on if a datapoint is elusive.

---

## Step 4: Determine the Date

Use today's date to set the reference date for file naming and the audit reference number.

Format: `1YYYY.MM` (Holocene calendar — just prepend `1` to the year)

Example: May 2026 → `12026.05`

---

## Step 5: Write the Apotheosis Audit

Follow `TEMPLATE A` in `code/audit-templates.md` exactly.

**File name:** `[First Last] (aa.1YYYY.MM).md`
**Save to:** `audits/`

For companies or organizations without a single named individual, use the organization name:
`[Organization Name] (aa.1YYYY.MM).md`

The audit must include:
- A verdict (CRITICAL ASCENSION RISK / MARGINAL ASCENSION RISK / PROBATIONARY SAINT / CLEARED)
- A confidence score (%)
- A comparative metrics table using real data where possible
- A direct quote from a fictional "auditor's summary" in the HPB's bureaucratic voice

Ground the audit in the entity's actual current holdings, ideology, and behavior. The 2084 framing should feel like a logical extension of their present-day trajectory, not a parody.

---

## Step 6: Write the Mortal Recertification Plan

Follow `TEMPLATE B` in `code/audit-templates.md` exactly.

**File name:** `[First Last] (mrp.1YYYY.MM).md`
**Save to:** `plans/`

The recertification plan must:
- Include 3–4 specific "burns" tailored to the entity's actual assets, ideology, and self-mythology
- Use the entity's own stated values or public persona against them where possible (see the Andreessen plan for an example — his "Techno-Optimist Manifesto" becomes the basis for the penance)
- End with a Mortal Oath that inverts their specific brand of exceptionalism
- Specify a failure consequence that feels fitting for this particular subject

Do not write a generic plan. Each plan should only make sense for this specific entity.

---

## Step 7: Verify and Report

After writing both files, confirm:
- Both files exist at the correct paths with correct names
- Column data from the CSV was used where available
- The audit verdict and plan are internally consistent (a CLEARED audit should not require a 30-day burn schedule)
- The `[!warning]` callout is present at the bottom of both files

Report back with:
- The two file paths
- The audit verdict and confidence score
- One sentence on the most interesting or unexpected finding from your research
