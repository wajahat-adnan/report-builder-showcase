# Synthetic Samples

## Overview

This directory is reserved for fabricated examples that demonstrate the Report Builder workflow without exposing real patient or clinic information.

The public repository does not contain production source code, real medical records, or proprietary parsing fixtures.

## Planned Samples

Future public samples may include:

- A synthetic abdomen worksheet image
- A structured extraction summary
- A reviewed measurement table
- An example editable report
- A sample DOCX export created from fabricated data

## Safety Requirements

Every public sample must be checked for:

- Patient names
- Dates of birth
- Medical record numbers
- Phone numbers and email addresses
- Clinic or hospital names
- Embedded file metadata
- Personal Windows usernames or local file paths
- Real diagnostic history
- Real physician information

## Example Workflow

```text
Synthetic Worksheet
        |
        v
Local OCR Analysis
        |
        v
Structured Measurements
        |
        v
Human Review
        |
        v
Editable Synthetic Report
```

## Public Sample Boundary

Public samples should demonstrate outputs and workflow behavior without revealing:

- Exact OCR alignment rules
- Production parsing heuristics
- Complete clinical threshold tables
- Proprietary report-generation logic
- Private evaluation fixtures

## Current Status

Synthetic sample package pending.
