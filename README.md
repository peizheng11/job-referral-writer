# Referral Outreach Writer

A reusable Agent Skill that analyzes a job description and retrieves the most relevant evidence from a candidate’s résumé, portfolio, and private career library to draft tailored referral requests.

The skill supports:

- Referral emails
- LinkedIn inbox messages
- Slack and other professional direct messages
- Job-description-to-résumé matching
- Evidence retrieval beyond a candidate’s most visible experience
- Privacy-conscious use of local candidate materials

## Why this skill exists

Generic referral-writing prompts often repeat the candidate’s current title or most prominent experience, even when an earlier project is more relevant to the role.

This skill uses a JD-driven evidence retrieval process. It first identifies the most important requirements in the job description, then searches across the candidate’s résumé, portfolio, and private evidence library for the strongest supporting examples.

For example, the skill may surface:

- Wearable-device experience for a device role
- Hardware and sensor research for an emerging-technology role
- Developer productivity research for a developer-experience role
- Retail and frontline workflow research for an operations role
- Mentorship and Research Operations experience for a leadership role
- Global field research for an international-research role
- Trust, integrity, or fraud research for a safety-focused role
- Advanced quantitative methods for a measurement-heavy role

A past role may be more relevant than the candidate’s current position.

## Features

- Analyzes explicit and implied requirements in a job description
- Matches role requirements to evidence from candidate materials
- Prioritizes direct relevance, demonstrated impact, recency, and differentiation
- Selects concise, evidence-based résumé highlights
- Writes warm, polite, confident, and low-pressure referral requests
- Supports both email and short-message formats
- Avoids unsupported claims and fabricated experience
- Keeps personal candidate materials outside the public repository
- Includes confidentiality and factuality checks

## Repository structure

```text
referral-outreach-writer/
├── SKILL.md
├── README.md
├── LICENSE
├── .gitignore
├── references/
│   ├── candidate-evidence-template.md
│   ├── jd-signal-map.md
│   └── writing-guidelines.md
├── examples/
│   ├── referral-email-example.md
│   └── linkedin-message-example.md
└── private/
    └── README.md
```

After local setup, the ignored `private/` directory may also contain:

```text
private/
├── README.md
├── candidate-evidence.md
├── resume.pdf
├── portfolio-notes.md
└── career-stories.md
```

Only `private/README.md` should be committed. The other files should remain local.

## How the skill works

The skill follows this general workflow:

1. Analyze the job description.
2. Identify the role’s core domain, users, methods, leadership expectations, technical context, and implied success criteria.
3. Search the candidate’s résumé, portfolio, and evidence library.
4. Retrieve both prominent and less-visible relevant experience.
5. Rank evidence by relevance, impact, recency, and differentiation.
6. Select two to four complementary highlights.
7. Draft a referral request suited to the requested channel.
8. Check factual accuracy, confidentiality, tone, and length.

## Privacy model

The public repository contains only reusable instructions, blank templates, and anonymized examples.

Personal materials should remain local and must not be committed to the public repository, including:

- Résumés
- Personal email addresses and phone numbers
- Portfolio notes
- Candidate evidence
- Career stories
- Referral-contact information
- Portfolio passwords
- Confidential work details
- Internal product names
- Unreleased product information
- Metrics that are not approved for external use

Store personal files inside the ignored `private/` directory.

The public skill logic and the local private evidence work together:

```text
Public skill instructions
        +
Local private candidate evidence
        =
Personalized referral outreach
```

You do not need to maintain separate public and private versions of the full skill.

## Setup

### 1. Clone or download the repository

Using Git:

```bash
git clone https://github.com/YOUR_USERNAME/referral-outreach-writer.git
cd referral-outreach-writer
```

Alternatively, download the repository as a ZIP file from GitHub and open the extracted folder.

### 2. Confirm that the private directory exists

```bash
mkdir -p private
```

### 3. Create your private candidate evidence file

Copy the public template:

```bash
cp references/candidate-evidence-template.md private/candidate-evidence.md
```

Then edit:

```text
private/candidate-evidence.md
```

Add your own experience, methods, leadership examples, impact evidence, safe external wording, and confidentiality constraints.

### 4. Add your résumé

Place your current résumé at:

```text
private/resume.pdf
```

You may use another filename, but update your request so the agent knows which file to read.

### 5. Add optional private materials

You may also create:

```text
private/portfolio-notes.md
private/career-stories.md
```

Use `portfolio-notes.md` to record:

- Portfolio project links
- Publicly shareable project summaries
- Relevant job-description signals
- Confidential details that should not be used

Use `career-stories.md` to record experiences that may not be fully represented in the résumé, such as:

- Mentoring junior researchers
- Managing contractors
- Overseeing Research Operations
- Reviewing research plans
- Developing reusable methods
- Influencing senior stakeholders
- Working with international teams

### 6. Confirm that private files are ignored

Check all ignored files:

```bash
git status --ignored
```

Check a specific file:

```bash
git check-ignore -v private/resume.pdf
```

A successful result will show the matching `.gitignore` rule, for example:

```text
.gitignore:6:*.pdf    private/resume.pdf
```

This is confirmation, not an error.

### 7. Review files before committing

Run:

```bash
git status
```

The following private files should not appear as files ready to commit:

```text
private/candidate-evidence.md
private/resume.pdf
private/portfolio-notes.md
private/career-stories.md
```

The public `private/README.md` may appear and can be committed.

## Usage

Provide the skill with:

- A job description or job-posting link
- A résumé
- A portfolio link or portfolio notes
- The recipient’s name, when known
- The company and role
- The desired format
- Relevant relationship context, when available

The skill should not invent missing relationships, qualifications, or achievements.

## Example request: referral email

```text
Use the referral-outreach-writer skill to draft a referral email for
the attached Senior UX Researcher role.

Analyze the job description, my résumé, and my private candidate
evidence. Retrieve the three strongest matching experiences, including
less prominent past experience when it is more relevant than my current
role.

Mention my attached résumé and portfolio. Use a warm, polite,
confident, and eager tone without sounding demanding.
```

## Example request: LinkedIn message

```text
Use the referral-outreach-writer skill to write a concise LinkedIn
inbox message asking [Name] for a referral to the attached role at
[Company].

Identify the three strongest résumé-to-JD matches. Keep the message
under 150 words, include my portfolio, and offer to share my résumé.

Use a warm and low-pressure tone.
```

## Example request: domain-specific evidence retrieval

```text
Use the referral-outreach-writer skill to analyze this wearable-device
research role.

Do not default only to my current AI experience. Search my résumé,
portfolio notes, and candidate evidence for device, hardware,
prototype-testing, longitudinal, and multimodal-interaction experience.

Draft a referral email using only supported facts.
```

## Output guidelines

### Email

A referral email should generally include:

1. A warm greeting
2. The specific role and company
3. A clear but low-pressure referral request
4. A concise self-introduction
5. Two to four relevant highlights
6. A portfolio link
7. A mention of the attached résumé
8. An appreciative and enthusiastic closing

Recommended length: **180–300 words**

### LinkedIn or Slack message

A short professional message should generally include:

1. A friendly greeting
2. The role and company
3. A concise referral request
4. The strongest one to three matching points
5. A portfolio link
6. An offer to share the résumé
7. A polite closing

Recommended length: **80–150 words**

## Factuality and confidentiality

The skill must:

- Use only experience supported by supplied candidate materials
- Avoid claiming direct experience when only adjacent experience exists
- Avoid inventing impact metrics
- Avoid exposing confidential details
- Use approved external wording when provided
- Distinguish direct, related, and transferable experience
- Prefer concrete examples over unsupported adjectives

When a match is adjacent rather than direct, use language such as:

- Related experience
- Adjacent experience
- Transferable experience
- Closely connected experience

Do not use language such as:

- Perfect candidate
- Uniquely qualified
- Guaranteed fit
- Expert in an area not supported by evidence

## Contributing

Contributions are welcome.

Useful contributions may include:

- Additional anonymized examples
- New JD-to-evidence mappings
- Improved privacy safeguards
- Better referral-language patterns
- Support for additional professional messaging channels

Before submitting a contribution, make sure it contains no personal, confidential, or proprietary information.

## License

This project is licensed under the MIT License.

See the `LICENSE` file for the full license text.
