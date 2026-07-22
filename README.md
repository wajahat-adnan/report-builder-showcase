# Report Builder

A local-first desktop application that converts structured radiology worksheets into editable ultrasound reports while keeping the clinician in control of the final output.

> This repository is a public engineering case study. The production source code is maintained privately because it contains proprietary implementation details. All examples shown here use synthetic or anonymized data.

## Project Overview

Report Builder is designed to reduce repetitive report-writing work for individual doctors and small clinics.

The current version focuses on abdomen ultrasound reporting and supports a workflow built around:

1. Uploading a worksheet image
2. Extracting measurements with local OCR
3. Reviewing detected values and interpretation states
4. Editing structured findings
5. Adding dictation and doctor instructions
6. Generating an editable report
7. Copying or exporting the report to Microsoft Word

## Key Features

- Local OCR processing without uploading patient documents
- Anchor-based extraction of organ measurements
- Deterministic measurement interpretation
- Human review before report completion
- Structured findings and selectable report statements
- Dictation support
- Editable report workspace
- Numbered impressions
- DOCX export and Microsoft Word integration
- Configurable report templates

## System Workflow


Worksheet Image -> Local OCR Extraction -> Anchor-Based Parsing -> Measurement Interpretation -> Clinician Review Structured Report Assembly -> Editable Report / DOCX Export

## Engineering Highlights

- Modular Python desktop application architecture
- Clear separation between OCR, parsing, interpretation, presentation, and export
- Deterministic clinical measurement rules
- Structured domain models for findings and report payloads
- Reusable GUI components
- Local audio recording and transcription workflow
- Synthetic testing fixtures
- Unit and integration testing for critical report behavior
- Privacy-conscious handling of medical documents

## Technology

- Python
- PaddleOCR
- Desktop GUI components
- `python-docx`
- Local audio recording and transcription
- NumPy
- Pytest

## Privacy and Safety

The application is designed around local processing. Patient worksheets do not need to be sent to a hosted OCR or language-model service.

The software assists with report preparation but does not replace clinical review or medical judgment. The doctor remains responsible for verifying extracted measurements, findings, and the final report.

See [Privacy and Safety](docs/privacy-and-safety.md).

## Architecture

The codebase separates:

- OCR extraction
- Template alignment
- Parsing
- Measurement interpretation
- Structured findings
- Report drafting
- Template management
- GUI presentation
- DOCX export

See [Architecture](docs/architecture.md).

## Testing

Testing covers areas including:

- Worksheet parsing
- Measurement extraction
- Measurement interpretation
- Dictation behavior
- Structured report generation
- Report-change highlighting
- End-to-end abdomen workflow behavior

See [Testing Strategy](docs/testing-strategy.md).

## Screenshots

### Initial Workspace

The application opens into a three-stage workflow for extraction review, structured finding selection, and report editing.

![Initial ReportPilot workspace](screenshots/01-initial-workspace.png)

### OCR Analysis and Report Draft

After a synthetic worksheet is analyzed, the application displays extracted measurements, review states, generated findings, and export actions.

![ReportPilot analysis workflow](screenshots/02-analysis-complete.png)

More details are available in the [screenshots documentation](screenshots/README.md).

## Demonstration

A short demonstration using synthetic worksheet data will be added under [`demo`](demo/).

## Source Availability

The production source code is maintained in a private GitHub repository.

Selected implementation details may be reviewed privately during a technical interview or hiring process. This public repository intentionally does not include:

- Production OCR and parsing logic
- Complete clinical interpretation rules
- Proprietary report-building logic
- Private test corpora
- Real patient data
- Reconstructive build scripts

## My Contribution

I designed and implemented the application workflow, including:

- OCR-assisted worksheet analysis
- Measurement parsing and interpretation
- Structured report construction
- Desktop interface components
- Dictation integration
- Report-template handling
- DOCX export
- Automated tests and workflow validation

## Project Status

Active development.

Current scope: abdomen ultrasound reporting.

## Disclaimer

This project is presented as an engineering portfolio case study. It is not presented as a certified medical device and must not be used without appropriate clinical validation and professional review.
