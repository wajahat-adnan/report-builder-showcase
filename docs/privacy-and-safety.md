# Privacy and Safety

## Overview

Report Builder is designed around local processing and clinician review.

The application assists with report preparation, but it does not replace medical judgment, clinical validation, or professional responsibility.

## Local-First Processing

The intended workflow keeps sensitive worksheet and report data on the user's computer.

Core design goals include:

- Local OCR processing
- Local report construction
- Local document export
- No required upload of patient worksheets to a hosted service
- No public storage of medical documents

## Human Review

The system is designed to support, not bypass, clinical review.

Before a report is finalized, the clinician can:

- Review extracted measurements
- Correct missing or inaccurate values
- Review interpretation states
- Edit findings
- Modify impressions
- Add instructions or dictation
- Verify the final report before export

## Deterministic Interpretation

Critical measurement handling uses deterministic rules where appropriate.

This helps make behavior:

- Predictable
- Reviewable
- Testable
- Easier to audit
- Less dependent on free-form model output

Uncertain or incomplete values should remain visible for human review rather than being silently accepted.

## Data Used in This Public Repository

This public showcase repository contains only:

- Synthetic screenshots
- High-level architecture documentation
- General testing descriptions
- Non-sensitive project information

It does not contain:

- Real patient names
- Patient identifiers
- Clinic records
- Real medical reports
- Private worksheet images
- Production databases
- OCR model files
- Proprietary parsing fixtures

## Public Demonstration Policy

Any public demonstration should use fabricated or fully anonymized data.

Before publishing a screenshot, video, fixture, or report, it should be checked for:

- Patient names
- Dates of birth
- Medical record numbers
- Contact information
- Clinic names
- Embedded document metadata
- File paths containing personal information
- Real diagnostic details

## Medical Safety Boundary

Report Builder is an engineering project and is not presented as a certified medical device.

The software must not be treated as a substitute for:

- Clinical training
- Independent diagnosis
- Measurement verification
- Professional review
- Regulatory validation

The clinician remains responsible for the accuracy and appropriateness of the final report.

## Source-Code Boundary

The production source code is private because it contains proprietary implementation details.

The public repository intentionally excludes:

- Complete OCR and parsing logic
- Exact measurement rules
- Clinical threshold tables
- Production report-generation logic
- Private test corpora
- Reconstructive build scripts

## Security Practices

Repository preparation includes checks for:

- Environment files
- API keys
- Passwords
- Tokens
- Private keys
- Local databases
- Generated reports
- Downloaded models
- Sensitive images
- Personal email addresses in commit history

## Responsible Use

The project should only be used in settings where:

- A qualified clinician reviews the output
- Local privacy requirements are respected
- Synthetic data is used for public demonstrations
- Sensitive files are excluded from source control
- The software is validated appropriately before real-world deployment
