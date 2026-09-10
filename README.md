# Strategic OS Intake

## Purpose

`strategic-os-intake` is a private temporary intake repository for meeting transcripts that need to be processed through Strategic OS.

Its only purpose is to make it easy to capture a meeting transcript from a browser-accessible work environment and move it into the Strategic OS reasoning workflow.

This repository is not:

- a knowledge repository;
- a source of truth;
- an archive;
- a general project repository; or
- a replacement for organisational systems of record.

## Operating Model

The intended work flow is:

Teams or approved meeting source  
→ browser transcript capture  
→ `strategic-os-intake`  
→ ChatGPT Project  
→ reasoning and synthesis  
→ human review  
→ safe durable Strategic OS knowledge where warranted  
→ `strategic-os` repository  
→ intake transcript deleted

Personal ideas, observations and reflections may follow a separate path:

Obsidian mobile  
→ ChatGPT Project  
→ reasoning and synthesis  
→ human review  
→ `strategic-os` repository where durable

## Role In Strategic OS

This repository provides a temporary bridge between meeting capture and Strategic OS reasoning.

It exists because work environments may not provide access to local Strategic OS tools.

The repository supports browser-based intake without requiring:

- a local Git installation;
- Obsidian desktop;
- manual repository cloning;
- local development tools; or
- direct interaction with Strategic OS runtime infrastructure.

## Allowed Content

This repository may contain:

- meeting transcripts that are appropriate to process through Strategic OS;
- meeting title;
- meeting date;
- source type;
- workstream or project name;
- minimal processing metadata; and
- processing status.

Only retain the minimum context required to process the transcript accurately.

## Prohibited Content

Do not store:

- customer personal information;
- credentials;
- passwords;
- API keys;
- access tokens;
- client secrets;
- governed datasets;
- customer-level records;
- controlled organisational documents;
- sensitive operational extracts;
- confidential source files;
- unnecessary screenshots;
- raw analytical datasets;
- unrelated project documents;
- permanent Strategic OS knowledge;
- general notes;
- ideas unrelated to a meeting transcript; or
- material that must remain exclusively in an organisational system of record.

Private repository status does not override organisational privacy, information-security or records requirements.

## Source-Of-Truth Boundary

This repository is never authoritative.

For original organisational material:

> The organisational system of record remains authoritative.

For durable Strategic OS knowledge:

> The live `strategic-os` repository remains authoritative.

The transcript stored here is temporary working input only.

## Repository Structure

Keep the repository intentionally small.

    strategic-os-intake/
    ├── README.md
    ├── incoming/
    └── processing/

### `incoming/`

Contains newly captured meeting transcripts awaiting processing.

### `processing/`

Contains transcripts actively being processed when a separate processing state is useful.

Do not create:

- a permanent archive;
- project folders;
- knowledge indexes;
- frameworks;
- templates;
- stakeholder libraries;
- analytics folders; or
- reusable knowledge structures.

Those belong elsewhere.

## File Naming

Use:

`YYYY-MM-DD-[meeting-slug].md`

Example:

`2026-09-10-intelligent-front-door-workshop.md`

File names should:

- use the meeting date;
- use lowercase;
- use hyphens;
- avoid participant names unless genuinely required;
- avoid sensitive information; and
- remain understandable without opening the file.

## Transcript File Pattern

Each intake file should use the minimum structure required for processing.

Example structure:

    # [Meeting title]

    ## Capture metadata

    - Date:
    - Source:
    - Workstream:
    - Status: Incoming

    ## Transcript

    [meeting transcript]

Do not add interpretation during capture.

Do not invent:

- decisions;
- actions;
- owners;
- evidence;
- deadlines; or
- consensus.

Interpretation happens during processing.

## Processing Model

A transcript should normally be processed into:

- decisions;
- evidence;
- insights;
- assumptions;
- open questions;
- actions; and
- Strategic OS candidates.

Processing occurs outside this repository, primarily through ChatGPT Project or another explicitly approved Strategic OS reasoning workflow.

The raw transcript remains evidence for the extraction while processing is active.

## Human Review

Human review is required before any extracted material becomes durable Strategic OS knowledge.

Review should confirm:

- the extraction reflects the transcript;
- decisions were actually made;
- evidence is supported;
- assumptions are labelled;
- actions are not invented;
- owners and deadlines are not inferred without evidence;
- sensitive information has been removed;
- reusable Strategic OS value actually exists; and
- the correct durable storage location has been selected.

## Promotion Rule

Do not move the transcript itself into the main `strategic-os` repository.

Only promote reviewed, privacy-safe and reusable outputs such as:

- decision logic;
- lessons learned;
- stakeholder patterns;
- strategic opportunities;
- project abstractions;
- reusable frameworks;
- analytical caveats;
- career-safe evidence; or
- other appropriate Strategic OS knowledge.

Promotion should follow the structure and governance of the `strategic-os` repository.

## Retention And Deletion

The intake lifecycle is:

Capture  
→ Process  
→ Review  
→ Promote useful knowledge  
→ Delete transcript

Transcripts should remain in this repository only for as long as required to complete processing and review.

Do not retain processed transcripts as an archive.

Once:

- extraction is complete;
- human review is complete; and
- useful durable material has been promoted where appropriate,

delete the transcript from this repository.

Git history and hosting behaviour must be considered when determining whether this repository is appropriate for a particular transcript.

Do not upload material that organisational requirements prohibit from being stored in this environment.

## Privacy Gate

Before submitting a transcript, confirm that it does not contain material that should not be stored in this repository.

If a transcript contains sensitive, restricted or inappropriate material:

- do not upload it unchanged;
- retain the original in the approved organisational system;
- remove or generalise sensitive content where appropriate; or
- use an approved alternative processing path.

When uncertain, preserve the organisational source and do not upload the transcript.

## Automation Boundary

Future automation may support:

- browser transcript submission;
- filename generation;
- metadata capture;
- movement from `incoming/` to `processing/`;
- processing-status updates;
- handoff to approved reasoning workflows;
- processing completion notifications; and
- deletion after confirmed review.

Automation must not:

- infer that upload equals approval;
- automatically promote raw transcript content into Strategic OS;
- create permanent knowledge without review;
- bypass privacy controls;
- retain transcripts indefinitely; or
- make organisational decisions.

## Design Principle

Keep this repository deliberately boring.

Its value is that it provides a simple, reliable and temporary intake mechanism.

Do not expand it into another Strategic OS knowledge layer.

If functionality belongs in the main `strategic-os` repository, ChatGPT Project, Slack, Make, Relevance AI, Obsidian or an organisational system of record, keep it there.
