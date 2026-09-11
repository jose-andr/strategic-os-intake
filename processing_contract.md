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

```text
Meeting
→ transcript captured
→ incoming/
→ ChatGPT Project processing
→ structured extraction
→ human review
→ operational information returned to the appropriate organisational system
→ reusable Strategic OS knowledge promoted when justified
→ raw intake transcript deleted
