# Transcript Processing Contract

## Purpose

Define what happens after a meeting transcript is captured in `strategic-os-intake`.

This repository is a temporary intake surface.

It is not:

- the Strategic OS source of truth;
- a meeting archive;
- a project documentation repository; or
- a permanent store of organisational transcripts.

The purpose of processing is to extract useful decision signal while keeping raw source material temporary.

## Standard Flow

Meeting  
→ transcript captured  
→ `incoming/`  
→ ChatGPT Project processing  
→ structured extraction  
→ human review  
→ operational information returned to the appropriate organisational system  
→ reusable Strategic OS knowledge promoted when justified  
→ raw intake transcript deleted

## 1. Capture

A transcript enters:

`incoming/`

The captured Markdown should contain only:

- meeting title;
- meeting date;
- source;
- optional workstream;
- status; and
- transcript content.

Do not manually interpret the meeting during capture.

Capture and interpretation are separate steps.

## 2. Process

Bring the transcript into the relevant ChatGPT Project.

Process it using:

`10_templates/meeting_transcript_extraction.md`

The standard extraction contains:

1. Decisions
2. Evidence
3. Insights
4. Assumptions
5. Open questions
6. Actions
7. Strategic OS candidates

The transcript remains the source evidence.

The extraction must not silently convert:

- discussion into decisions;
- suggestions into commitments;
- assumptions into evidence;
- implied ownership into assigned ownership; or
- approximate timing into deadlines.

## 3. Review

Human review is required before extracted material is acted on or retained as durable knowledge.

Review should confirm:

- decisions are supported by the transcript;
- evidence and interpretation are distinguishable;
- assumptions remain visible;
- owners and deadlines have not been invented;
- sensitive information is handled appropriately;
- the output is useful for the work; and
- any proposed Strategic OS candidate is genuinely reusable.

## 4. Route the Outputs

Different information belongs in different systems.

### Organisational material

Operational project information should normally return to its appropriate organisational system.

Examples include:

- project actions;
- Jira tasks;
- formal decisions;
- Confluence documentation;
- delivery commitments;
- organisational records; and
- source evidence.

`strategic-os-intake` does not become the system of record for these items.

### Strategic OS material

Only reviewed, privacy-safe and reusable knowledge should be considered for promotion into the main `strategic-os` repository.

Possible examples include:

- reusable decision patterns;
- lessons learned;
- stakeholder patterns;
- analytical caveats;
- strategic opportunities;
- frameworks;
- templates; and
- operating-model improvements.

A meeting does not need to produce a Strategic OS artefact.

## 5. Promotion Rule

Do not promote the raw transcript.

Promote only the reusable abstraction.

Before promotion ask:

**Will retaining this improve a future strategic decision, reusable capability or quality of reasoning?**

If not, do not add it to Strategic OS.

GitHub in the main `strategic-os` repository remains authoritative for durable Strategic OS knowledge.

## 6. Delete the Intake Transcript

Once:

- processing is complete;
- required organisational information has been routed;
- any Strategic OS candidate has been reviewed; and
- the raw transcript is no longer required for the intake workflow,

delete the transcript from `incoming/`.

Do not retain transcripts merely because storage is available.

Deletion from the repository does not necessarily remove content from Git history.

Sensitive organisational material should therefore only enter this workflow where its use and temporary storage are appropriate.

## Status Model

Use these working states:

`Incoming → Processing → Reviewed → Complete`

The state describes intake processing only.

It does not represent project delivery status or organisational approval.

## Operating Rule

Keep this workflow lightweight.

Do not introduce:

- automated strategic judgement;
- automatic promotion into Strategic OS;
- additional processing stages;
- transcript databases;
- permanent archives; or
- agent orchestration

unless repeated real use demonstrates a genuine need.

The human remains responsible for deciding what matters and what becomes durable knowledge.
