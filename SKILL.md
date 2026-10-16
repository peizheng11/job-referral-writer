---
name: referral-outreach-writer
description: >
  Analyze a job description against a candidate's résumé variants,
  portfolio, and evidence library to (1) write tailored
  referral-request emails, LinkedIn messages, and professional
  direct messages, and (2) select and tailor the best-matching
  résumé content for that specific JD. Use this skill when a user
  wants to request an internal referral, match their experience to
  a role, tailor or customize a résumé to a job description, or
  create concise referral outreach.
---

# Referral Outreach Writer
## Purpose

Given a job description, this skill does two related things:

1. Retrieves the strongest matching evidence from across the
   candidate's résumé variants, portfolio, and evidence library, and
   drafts a personalized referral-request message.
2. Uses the same JD-matched evidence to select, reorder, and rewrite
   résumé content into a version customized for that specific JD.

The output may be:

- An email
- A LinkedIn inbox message
- A short professional direct message
- A tailored résumé (content-level: selected and rewritten bullets,
  not a formatted document — see "Resume tailoring workflow" and the
  handoff to resume-skill below)

## Core principle

Do not repeatedly default to the candidate's most visible, most
recent, or most-often-used résumé version.

First analyze the job description, then retrieve the strongest
relevant evidence from all candidate sources — including résumé
variants written for entirely different roles or companies.

A past experience, or a bullet phrased in a résumé variant the
candidate hasn't used in years, may be more relevant than what's in
their current default résumé.

## Inputs

Use available information from:

1. The current user request
2. A supplied job description or job link
3. `private/resumes/` — the candidate's résumé variants (see "Résumé variants" below)
4. Portfolio content
5. `private/candidate-evidence.md`, when present
6. `private/portfolio-notes.md`, when present
7. `private/career-stories.md`, when present

Do not assume that private files exist. Check before using them.

Never invent experience, impact, relationships, or qualifications.
Never blend facts from two different roles or projects into one
bullet that describes something that didn't happen as stated.

## Résumé variants

Candidates often hold many résumé versions, each emphasizing
different experience, projects, or phrasing for a past application.
Treat every variant as a legitimate evidence source, not just the
most recent or most complete one.

- Store variants under `private/resumes/` (any mix of PDF, DOCX, or HTML).
- Maintain `private/resumes/_index.md` — one line per variant: filename,
  target role/company (if known), and its distinguishing emphasis or
  angle. See `references/resume-variants-index-template.md`.
- Before reading every variant in full, scan the index to shortlist
  the 2–4 variants most likely to contain the best-matching bullets
  for the current JD (by target domain, role level, or emphasis).
  Read those in full; skim others only if the shortlist doesn't
  cover a JD requirement.
- If no index exists yet, or a variant isn't indexed, read it anyway
  — just note in your working notes that the index needs updating,
  and update it after use.
- When two variants describe the same project with different
  emphasis or numbers, prefer the version that is more specific and
  directly relevant to the current JD, but never merge two variants'
  numbers into a new figure that appears in neither.

## Workflow

### Step 1: Analyze the job description

Identify:

- Core domain
- Product type
- User type
- Required methods
- Leadership expectations
- Technical expectations
- Global or market requirements
- Explicit qualifications
- Implied success criteria

Distinguish required qualifications from preferred qualifications.

### Step 2: Generate JD signals

Look for explicit and related signals.

Examples:

- Wearables → device research, hardware, sensors, longitudinal use
- Developer experience → cloud tools, infrastructure, technical users
- Retail → frontline workers, store operations, scheduling
- Leadership → mentorship, contractor management, Research Operations
- Trust and safety → fraud, integrity, risk, AI trust
- Enterprise → complex workflows, administration, permissions, adoption
- Global research → non-US markets, cross-cultural research, localization
- Quantitative rigor → surveys, experiments, statistics, benchmarking
- AI → human-AI interaction, evaluation, trust, model quality

See `references/jd-signal-map.md` for the full table.

### Step 3: Retrieve candidate evidence

Search résumé variants (via the index shortlist), portfolio, and the
evidence library for direct and adjacent evidence.

Do not stop after finding the first obvious match. Do not stop at
the candidate's default/most-recent résumé variant if an older or
less-used variant has a stronger or more specific bullet for this JD.

Rank evidence by:

1. Direct relevance
2. Demonstrated impact
3. Recency
4. Differentiation
5. Credibility of supporting evidence

### Step 4: Select highlights

Choose two to four highlights that collectively demonstrate:

- One direct domain match
- One methodological or technical match
- One product or business impact
- One leadership or differentiating strength, when relevant

Avoid selecting several examples that all make the same point.

This same shortlist feeds both the outreach message (Step 5) and
résumé tailoring (see "Resume tailoring workflow" below) — do the
retrieval and ranking once, then branch into whichever output the
user asked for.

### Step 5: Draft the outreach

Use this structure:

1. Warm, polite greeting
2. Name the exact company and role
3. Make a clear, low-pressure referral request
4. Give a concise self-introduction
5. Highlight the strongest JD-to-candidate matches
6. Include the portfolio
7. Mention the attached resume or offer to share it
8. End with appreciation and genuine enthusiasm

## Resume tailoring workflow

Run this when the user asks to tailor, customize, or adapt a résumé
to a specific JD (instead of, or in addition to, an outreach
message). Reuse the JD analysis and evidence ranking from Steps 1–4
above rather than redoing them.

### Step A: Choose a base variant

From the shortlisted résumé variants, pick the one whose overall
shape (seniority framing, domain emphasis, section structure) is
closest to what the JD wants. This is the base to edit — don't
build a résumé from scratch each time if a close variant exists.

### Step B: Fill gaps from other variants and the evidence library

For each JD requirement not well covered by the base variant's
existing bullets, check:

1. Other résumé variants for a bullet that already states this experience
2. `private/candidate-evidence.md` for supporting detail
3. `private/career-stories.md` for experience never turned into a résumé bullet at all

Pull in the strongest matching bullet. If a bullet is being brought
in from a variant other than the base, note that in your working
response so the user can sanity-check title/date consistency before
using it.

### Step C: Reorder and rewrite

- Reorder bullets within each role so the JD's top priorities lead.
- Rewrite bullet phrasing to mirror the JD's own terminology
  **only** when the underlying fact is unchanged — this is
  rephrasing for ATS/recruiter matching, not adding scope.
- Cut or shorten bullets that don't serve this JD, even if they're
  strong bullets for a different kind of role.
- Remove duplicate accomplishments that appear across two merged
  bullets — one clear bullet beats two overlapping ones.
- Apply the same confidentiality rules as outreach (see below) —
  internal tool names, generalized product names, and the
  internal-vs-external framing note in `candidate-evidence.md` all
  still apply inside a tailored résumé.

### Step D: Respect length and format norms

- Under 10 years of experience: aim for one page. Senior/10+ years: up to two pages.
- Preserve the base variant's section structure (Summary, Experience, Core Expertise, Skills, Education) unless the JD strongly implies a different emphasis order.
- Output the tailored content as plain text/Markdown grouped by résumé section — this skill produces **content**, not a formatted document.
- To turn tailored content into a polished, templated document, hand off to `resume-skill` (it takes structured content and renders one of its templates) rather than duplicating template/rendering logic here. When handing off, request the editable HTML output with autosave (per `resume-skill`'s `prompts/editable-version.md`) so edits made in the browser persist across reopening the same file, not just the plain print-ready HTML.

## Tone

The message must sound:

- Warm
- Polite
- Confident
- Specific
- Appreciative
- Eager but not desperate
- Natural rather than formulaic

Avoid:

- Excessive flattery
- Unsupported superlatives
- Demanding referral language
- Long resume summaries
- Generic statements
- Repeated information

Résumé bullets should sound confident and specific, the same way —
avoid unsupported superlatives there too ("world-class," "expert in"
without evidence).

## Output length

### Email

Target 180–300 words.

Use up to four short bullet points only when they improve readability.

Include a subject line.

### LinkedIn message

Target 80–150 words.

Use a compact paragraph or no more than three brief highlights.

### Connection note

Keep within the platform's stated character limit.

### Tailored résumé

Follow Step D above (one page under 10 years of experience, up to
two pages for senior candidates).

## Privacy and factuality

Never expose private candidate files in the output.

Use only the amount of personal information needed to create the
requested message or résumé.

Do not reveal:

- Confidential company information
- Internal product names
- Unapproved metrics
- Private contact details
- Portfolio passwords
- Referral-contact history
- Information marked as confidential

When evidence is adjacent rather than direct, use careful language such
as:

- related experience
- adjacent experience
- transferable experience
- closely connected experience

When tailoring a résumé, never combine facts from two different
roles or projects into a single bullet that implies something that
didn't happen as stated, even if each fact individually is true.

## Quality check

Before returning an outreach message, verify:

- Is the referral request clear?
- Is the company and role named?
- Are the selected highlights directly relevant?
- Are all claims supported?
- Did the skill search beyond the candidate's headline experience?
- Is the portfolio included?
- Is the resume appropriately mentioned?
- Is the message concise?
- Does the closing sound polite and eager?
- Has repeated information been removed?

Before returning a tailored résumé, verify:

- Is every bullet traceable to a specific résumé variant or evidence-library entry?
- Were other variants checked, not just the base/default one?
- Are there any fabricated or blended metrics?
- Is phrasing consistent in tense and voice across bullets pulled from different variants?
- Does bullet order lead with the JD's top priorities?
- Does length match the one-page/two-page norm?
- Were confidentiality rules (internal tool names, internal-vs-external framing) applied?
- Did you flag which bullets came from a non-base variant, for the candidate to sanity-check?
