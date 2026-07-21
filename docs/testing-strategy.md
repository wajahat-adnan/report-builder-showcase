# Testing Strategy

## Overview

Report Builder uses automated tests to validate the most important parts of the worksheet-to-report workflow.

The production test suite is maintained in the private repository. This document describes the testing approach and the types of behavior covered without exposing proprietary fixtures or implementation details.

## Testing Goals

The test strategy is designed to verify that:

- Extracted measurements are normalized consistently
- Unsupported or uncertain values are surfaced for review
- Structured findings are assembled predictably
- Dictation does not corrupt report content
- User edits remain visible and controllable
- Report output stays editable
- Changes to one workflow stage do not silently break another

## Test Layers

### Unit Tests

Unit tests focus on small, deterministic components such as:

- Measurement parsing
- Unit normalization
- Reference-state assignment
- Structured finding construction
- Report payload generation
- Dictation token handling
- Text-change detection and highlighting

### Integration Tests

Integration tests exercise interactions between multiple components, including:

- OCR output flowing into the parser
- Parsed measurements flowing into interpretation
- Reviewed values flowing into report assembly
- Structured findings appearing in the editable report
- Export-ready report payload creation

### Workflow Tests

Workflow tests cover representative abdomen ultrasound scenarios from worksheet input through report preparation.

These tests use synthetic fixtures and verify behavior such as:

- Expected measurements are detected
- Missing measurements remain visible
- Abnormal or uncertain values receive the correct review state
- Findings and impressions remain editable
- Report sections are generated in the expected order

### Regression Tests

Regression tests protect previously corrected behavior, including:

- Dictation control tokens not appearing in the report
- User-modified text remaining distinguishable from generated text
- Changes to parser behavior not altering unrelated report sections
- Interface workflow updates not breaking report generation

## Representative Test Areas

The private repository currently includes tests covering areas such as:

- Abdomen analysis pipeline behavior
- Dictation handling
- Report-change highlighting
- OCR smoke testing
- OCR benchmark support
- End-to-end synthetic worksheet processing

## Test Data Policy

Public demonstrations and documentation use synthetic data only.

The testing approach avoids placing real patient information in:

- Source control
- Public screenshots
- Public fixtures
- Generated example reports
- Documentation

## Deterministic Validation

Critical interpretation behavior is tested with deterministic rules rather than relying only on free-form language-model output.

This makes expected outcomes:

- Repeatable
- Reviewable
- Easier to debug
- Safer to regression-test

## Manual Review

Automated testing is supplemented by manual checks of:

- Desktop layout
- Measurement review states
- Report editing behavior
- Dictation controls
- DOCX export
- Microsoft Word opening behavior

## Private Test Boundary

The public repository intentionally excludes:

- Full test source code
- Proprietary parsing fixtures
- Exact clinical thresholds and rule tables
- Real medical worksheets
- Internal benchmark datasets
- Reconstructive integration harnesses

Selected test examples and results may be reviewed privately during a technical interview.
