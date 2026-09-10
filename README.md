# Strategic OS Intake

## Purpose

`strategic-os-intake` is a private temporary intake repository for meeting transcripts that need to be processed through Strategic OS.

Its only purpose is to make it easy to capture a meeting transcript from a browser-accessible work environment and move it into the Strategic OS reasoning workflow.

This repository is not a knowledge repository.

It is not a source of truth.

It is not an archive.

## Operating Model

The intended flow is:

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

```text
strategic-os-intake/
├── README.md
├── incoming/
└── processing/
