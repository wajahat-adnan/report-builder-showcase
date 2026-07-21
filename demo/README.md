# Product Demonstration

## Overview

This directory will contain a short demonstration of Report Builder using synthetic data only.

The production source code remains private. The public demo is intended to show the workflow, interface, and engineering outcomes without exposing proprietary implementation details.

## Planned Demo Flow

A concise demonstration should show:

1. Launching the desktop application
2. Viewing the empty three-stage workspace
3. Uploading a synthetic abdomen ultrasound worksheet
4. Running local worksheet analysis
5. Reviewing extracted measurements
6. Showing normal, high, missing, and review states
7. Selecting or editing structured findings
8. Reviewing the generated report draft
9. Editing report content
10. Copying, opening in Microsoft Word, or exporting DOCX

## Suggested Video Length

Target length: 60 to 120 seconds.

A short demo is easier for employers to review and should focus on the complete workflow rather than every interface control.

## Recording Checklist

Before recording:

- Use a synthetic worksheet filename
- Confirm no patient names or identifiers are visible
- Close unrelated applications and notifications
- Hide personal folders, account names, and email addresses
- Use a clean desktop background
- Set the application window to a readable size
- Confirm the report contains fabricated information only
- Check exported document metadata where applicable

## Suggested Narration

### Opening

“Report Builder is a local-first desktop application designed to reduce repetitive abdomen ultrasound reporting work while keeping the clinician in control.”

### Analysis

“A synthetic worksheet is processed locally. Extracted measurements are displayed with explicit states so uncertain or missing values remain visible for review.”

### Report Construction

“Structured findings and reviewed measurements are assembled into an editable report draft rather than an irreversible final output.”

### Export

“The clinician can continue editing, copy the report, open it in Microsoft Word, or export it as a DOCX document.”

### Closing

“The production implementation is private, while this repository documents the architecture, testing strategy, engineering decisions, and privacy boundaries.”

## Public Demo Safety Rules

The demo must not include:

- Real patient data
- Clinic records
- Private email addresses
- API keys or credentials
- Private repository URLs
- Source-code windows
- Proprietary parsing rules
- Internal test fixtures
- Local file paths containing personal information

## Publishing Options

The final recording may be published as:

- An unlisted YouTube video
- A public YouTube portfolio video
- A GitHub-compatible MP4 stored in this directory, if the file remains reasonably small
- A link from the main README

## Current Status

Demo recording pending.
