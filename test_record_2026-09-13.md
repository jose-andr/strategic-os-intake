# Transcript Intake Test Record — 13 September 2026

## Purpose

Validate that `strategic-os-intake` can accept meeting transcripts through either:

- original transcript file upload; or
- pasted transcript text.

The test also validates routing through Make and successful creation of the corresponding source file in `incoming/`.

## Test status

**Result:** Passed

Both supported intake paths were successfully validated end to end.

## Validated workflow

### File upload

Flow:

Browser capture form  
→ Make webhook  
→ File upload route  
→ GitHub Contents API  
→ original transcript file written to `incoming/`

Supported formats tested:

- `.vtt`

Supported formats configured:

- `.vtt`
- `.docx`

The browser converts the uploaded file to Base64 for transport.

Make passes the existing Base64 value directly to the GitHub Contents API.

The file is not re-encoded in Make.

### Pasted transcript

Flow:

Browser capture form  
→ Make webhook  
→ Pasted transcript route  
→ Markdown formatting  
→ GitHub Contents API  
→ `.md` file written to `incoming/`

The Markdown output retains:

- meeting title;
- capture metadata;
- transcript content; and
- `Incoming` status.

## Browser validation

The capture form supports two mutually exclusive transcript methods:

1. upload a transcript file; or
2. paste transcript text.

The browser prevents submission when:

- neither method is provided; or
- both methods are provided.

The browser currently sends these fields to Make:

- `title`
- `date`
- `source`
- `workstream`
- `confirmation`
- `transcript`
- `file_name`
- `file_type`
- `file_extension`
- `file_base64`

## Make validation

The webhook successfully detects all 10 expected fields.

A Router separates the two processing paths.

### File upload route

Routing condition is based on the uploaded file payload.

The route writes the original file to GitHub using the GitHub Contents API.

Validated commit message:

`Capture meeting transcript file`

### Pasted transcript route

Routing condition is based on pasted transcript content.

The route preserves the previously validated Markdown-generation workflow.

Validated commit message:

`Capture meeting transcript`

## File naming

### Uploaded files

Uploaded transcripts use:

`incoming/YYYY-MM-DD-[original-file-name]`

The original extension is retained.

Example:

`incoming/2026-09-13-meeting-transcript.vtt`

This provides a more recognisable source filename than an execution-time-only filename.

### Pasted transcripts

Pasted transcripts continue to use:

`incoming/YYYY-MM-DD-HHMMSS.md`

This provides a unique filename where no original source filename exists.

## Test evidence

Successful test files were created in `incoming/` for both routes.

The VTT test confirmed that:

- the upload reached the correct Make route;
- the GitHub request succeeded;
- the original Base64 payload was accepted;
- the repository created a `.vtt` file; and
- the source remained in VTT format rather than being converted to Markdown.

The pasted-text test confirmed that:

- the submission reached the pasted-transcript route;
- Markdown formatting remained operational; and
- a valid `.md` intake file was created.

## Issues identified and resolved

### Router filtering

Initial `Exists` filtering did not reliably route test submissions as expected.

The routing configuration was adjusted during testing until the appropriate branch executed successfully.

No further routing change is currently required.

### GitHub request URL

An early file-upload request generated a malformed URL because:

- the formatted time contained quotation marks; and
- whitespace appeared before the file extension.

The URL construction was corrected.

### HTTP method

An early test used `GET` rather than `PUT`.

The file-upload GitHub request was corrected to:

`PUT`

### Request body

The file-upload request initially had an empty GitHub request body.

The body was corrected to provide:

- `message`
- `content`

The `content` field maps directly to the Base64 value created by the browser.

## Known behaviour

Re-running an already captured Make bundle can create another copy of the same source transcript when the generated repository path is different.

This was observed during manual testing.

This is currently treated as a test/replay behaviour rather than a production defect because the normal workflow is:

one capture submission  
→ one Make execution  
→ one intake file

Do not add duplicate-detection logic unless repeated real use shows that duplicate submissions occur during normal operation.

## Security note

GitHub access credentials remain configuration secrets and must not be included in repository documentation, test records or shared logs.

Any credential exposed during configuration or debugging must be revoked and replaced.

## Validation outcome

The current intake workflow is considered operational for active use.

Validated capabilities:

- VTT upload;
- DOCX upload configured;
- pasted transcript fallback;
- mutually exclusive capture methods;
- Make webhook receipt;
- route selection;
- GitHub API write;
- preservation of original uploaded file type;
- Markdown generation for pasted transcripts; and
- human-readable intake filenames.

## Current operating rule

Use file upload when an original `.vtt` or `.docx` transcript is available.

Use pasted text as a fallback.

Do not add further automation, duplicate handling or processing complexity unless repeated real use exposes a genuine need.
