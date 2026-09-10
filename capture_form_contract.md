# Strategic OS Transcript Capture Form Contract

## Purpose

Define the minimum browser-based interface for submitting a meeting transcript into `strategic-os-intake`.

The form exists to make meeting capture possible from a work browser without requiring:

- local software installation;
- Git;
- Obsidian desktop;
- direct repository editing; or
- knowledge of the downstream Strategic OS workflow.

The form is an intake surface only.

It does not analyse the meeting, create Strategic OS knowledge or make decisions.

## User Flow

The intended interaction is:

Open capture page  
→ enter minimal meeting context  
→ paste transcript  
→ confirm the material is appropriate to submit  
→ submit  
→ create Markdown file in `incoming/`  
→ show successful capture confirmation

The workflow should require as little manual effort as practical.

## Form Fields

### Meeting title

**Required**

Free text.

Example:

`Intelligent Front Door Discovery Workshop`

Used for:

- file heading;
- filename generation; and
- identifying the transcript during processing.

### Meeting date

**Required**

Date field.

Default to the current date.

The user may change it when processing an earlier meeting.

Format:

`YYYY-MM-DD`

### Source

**Required**

Controlled options:

- Teams transcript
- Meeting notes
- Audio-derived transcript
- Other transcript

The source describes how the text was captured.

It does not establish that the material is validated.

### Workstream

**Optional**

Free text.

Examples:

- Channel Strategy Y2
- Customer Accounts
- Strategic OS
- Service Account

Do not create a controlled workstream taxonomy until repeated use demonstrates a need.

### Transcript

**Required**

Large multi-line text field.

The user pastes the meeting transcript or meeting-derived text here.

The form must preserve:

- paragraph breaks;
- speaker labels where present; and
- source wording.

Do not rewrite, summarise or classify the transcript during capture.

### Submission confirmation

**Required**

Checkbox wording:

`I have checked that this material is appropriate to submit to the Strategic OS intake repository.`

Submission must not proceed unless this is selected.

This confirmation does not replace organisational privacy, security or records requirements.

## Do Not Ask For

The capture form should not ask the user to identify:

- decisions;
- evidence;
- insights;
- assumptions;
- actions;
- owners;
- deadlines;
- stakeholders;
- sentiment;
- themes;
- Strategic OS candidates; or
- agent routing.

These belong in the processing stage.

Capture should remain fast and low-friction.

## File Creation

A successful submission creates one Markdown file under:

`incoming/`

Use the filename pattern:

`YYYY-MM-DD-[meeting-slug].md`

Example:

`2026-09-10-intelligent-front-door-discovery-workshop.md`

### Slug Rules

The meeting slug should:

- use lowercase;
- replace spaces with hyphens;
- remove unsupported special characters;
- avoid participant names unless already essential to the meeting title;
- avoid sensitive information; and
- remain reasonably short.

If a file with the same name already exists, append a short unique suffix rather than overwriting it.

Example:

`2026-09-10-intelligent-front-door-discovery-workshop-02.md`

## Generated Markdown

Each form submission should create:

    # [Meeting title]

    ## Capture metadata

    - Date: YYYY-MM-DD
    - Source: [source]
    - Workstream: [workstream or blank]
    - Status: Incoming

    ## Transcript

    [verbatim submitted transcript]

The capture process must not add interpretation.

## Repository Behaviour

On successful submission:

1. create the Markdown file in `incoming/`;
2. commit the file to the private `strategic-os-intake` repository;
3. return a clear success confirmation to the user.

The user should not need to:

- create a filename;
- format Markdown;
- open GitHub;
- create a commit message; or
- move the file manually.

## Success Confirmation

The browser should confirm:

`Meeting transcript captured successfully.`

Where practical, also show:

- meeting title;
- generated filename; and
- submission status.

Do not expose repository credentials or implementation details.

## Error Behaviour

If submission fails:

- do not claim that the transcript was captured;
- preserve the transcript in the browser where practical so the user does not lose their pasted content;
- show a plain-English error;
- allow the user to retry.

Example:

`The transcript could not be saved. Your text has been kept on this page so you can retry.`

Do not expose:

- authentication tokens;
- stack traces;
- API responses;
- repository secrets; or
- infrastructure details.

## Privacy Boundary

The form must not imply that any transcript is automatically appropriate for submission.

The user remains responsible for checking that the material can be stored in the intake repository.

Do not submit material containing prohibited content defined in `README.md`.

The form should not perform automatic redaction in the first version.

Automatic privacy classification or redaction may be considered later only if repeated use demonstrates a genuine need and the control can be trusted.

## Authentication

Repository credentials must not be exposed in browser code.

The browser form must submit through a secure server-side or serverless endpoint that performs the repository write.

Preferred pattern:

Browser form  
→ secure endpoint  
→ GitHub API  
→ `strategic-os-intake/incoming/`

Do not place a GitHub personal access token directly in HTML, JavaScript or any client-side configuration.

## Processing Boundary

Successful capture ends when the Markdown file exists in `incoming/`.

Version 1 must not automatically:

- invoke Relevance AI;
- classify the transcript;
- create the seven-part extraction;
- promote knowledge to `strategic-os`;
- delete the transcript;
- message stakeholders; or
- trigger multi-agent workflows.

Those are separate processing steps.

## Future Integration Boundary

The form and intake repository should be capable of supporting later integration with:

- ChatGPT Project;
- Make;
- Relevance AI;
- notifications; and
- controlled deletion workflows.

Do not implement those integrations until the basic capture path works reliably.

## Definition Of Done

The first version is complete when José can:

1. open the capture page from a work browser;
2. enter meeting title and date;
3. select the source;
4. optionally enter a workstream;
5. paste a transcript;
6. confirm the submission;
7. press Submit;
8. receive a success message; and
9. see the correctly formatted Markdown file in `strategic-os-intake/incoming/`.

Nothing more is required for the first version.
