---
name: referral-outreach-writer
description: >
  Analyze a job description and a candidate's resume, portfolio,
  and evidence library to write tailored referral-request emails,
  LinkedIn messages, and professional direct messages. Use this
  skill when a user wants to request an internal referral, match
  their experience to a role, or create concise referral outreach.
---

# Referral Outreach Writer
## Purpose

Create concise, personalized referral-request messages based on:

- A job description or job posting
- The candidate's resume
- Portfolio materials
- A private candidate evidence library
- The relationship between the candidate and recipient

The output may be:

- An email
- A LinkedIn inbox message
- A short professional direct message

## Core principle

Do not repeatedly default to the candidate's most visible or recent
experience.

First analyze the job description, then retrieve the strongest
relevant evidence from all candidate sources.

A past experience may be more relevant than the current role.

## Inputs

Use available information from:

1. The current user request
2. An attached resume
3. A supplied job description or job link
4. Portfolio content
5. `private/candidate-evidence.md`, when present
6. `private/portfolio-notes.md`, when present
7. `private/career-stories.md`, when present

Do not assume that private files exist. Check before using them.

Never invent experience, impact, relationships, or qualifications.

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

### Step 3: Retrieve candidate evidence

Search the resume, portfolio, and evidence library for direct and
adjacent evidence.

Do not stop after finding the first obvious match.

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

## Privacy and factuality

Never expose private candidate files in the output.

Use only the amount of personal information needed to create the
requested message.

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

## Quality check

Before returning the message, verify:

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
