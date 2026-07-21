# Architecture

## Overview

Report Builder is organized as a local-first desktop application with separate layers for document analysis, clinical interpretation, user review, report construction, and export.

The production implementation is private. This document describes responsibilities and data flow only.

## High-Level Flow

Worksheet Image
      |
      v
OCR and Template Alignment
      |
      v
Measurement Parsing
      |
      v
Deterministic Interpretation
      |
      v
Clinician Review
      |
      v
Structured Findings
      |
      v
Report Draft Assembly
      |
      v
Editable Report and DOCX Export

## Main Components

### OCR and Alignment

Responsible for:

- Loading the worksheet image
- Detecting text locally
- Aligning supported worksheet layouts
- Returning extracted text and measurement candidates

### Parsing

Responsible for:

- Locating organ and measurement anchors
- Normalizing extracted values
- Separating measurements from free-text comments
- Creating structured intermediate records

### Measurement Interpretation

Responsible for:

- Validating units and value formats
- Applying deterministic reference rules
- Assigning review states
- Avoiding automatic acceptance of uncertain values

### Review Interface

Responsible for:

- Showing extracted values
- Displaying normal, high, missing, or review states
- Allowing correction before report completion
- Preserving clinician control

### Findings and Report Assembly

Responsible for:

- Managing selectable report statements
- Combining structured findings with measurements
- Incorporating doctor instructions and dictation
- Producing an editable draft

### Export

Responsible for:

- Copying the report
- Opening the report in Microsoft Word
- Exporting a DOCX document
- Keeping the final output editable

## Architectural Principles

- Local processing by default
- Human review before final output
- Deterministic rules for critical interpretation
- Clear separation of concerns
- Structured intermediate data
- Replaceable OCR and transcription components
- Synthetic test data for public demonstrations
- No real patient information in the public repository

## Private Implementation Boundary

The public repository intentionally excludes:

- Production OCR code
- Exact anchor and parsing rules
- Complete clinical reference logic
- Report-generation internals
- Private test fixtures
- Reconstruction scripts
