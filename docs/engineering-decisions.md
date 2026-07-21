# Engineering Decisions

## Overview

This document summarizes important design choices made during the development of Report Builder.

The goal is to explain the engineering reasoning and tradeoffs without exposing proprietary implementation details.

## 1. Local-First Processing

### Decision

Keep OCR, parsing, report construction, and document export on the user's computer.

### Why

Medical worksheets and reports may contain sensitive information. Local processing reduces unnecessary data exposure and avoids making a hosted service a requirement.

### Tradeoff

Local processing places more responsibility on the desktop environment and may require packaging OCR models and native dependencies carefully.

## 2. Human Review Before Final Output

### Decision

Require the clinician to review extracted measurements, findings, and report content before export.

### Why

OCR and automated interpretation can be incomplete or incorrect. The interface is designed to surface uncertainty rather than hide it.

### Tradeoff

The workflow is not fully automatic, but the retained review step improves control, transparency, and safety.

## 3. Deterministic Rules for Critical Measurements

### Decision

Use deterministic interpretation rules for supported measurements instead of relying entirely on free-form language-model output.

### Why

Deterministic rules are easier to test, audit, reproduce, and explain.

### Tradeoff

Rules must be maintained explicitly and validated for each supported study type.

## 4. Structured Intermediate Data

### Decision

Convert extracted worksheet content into structured measurement and finding records before generating report text.

### Why

Structured data separates extraction from presentation and makes it easier to:

- Validate values
- Track review states
- Change report templates
- Test individual workflow stages
- Support future study types

### Tradeoff

The application requires more domain modeling than a simple OCR-to-text pipeline.

## 5. Modular Workflow Layers

### Decision

Separate OCR, alignment, parsing, interpretation, report assembly, interface components, and export behavior.

### Why

Clear boundaries reduce coupling and allow components to be tested or replaced independently.

### Tradeoff

The codebase contains more modules and interfaces than a single-file prototype.

## 6. Explicit Review States

### Decision

Represent values with states such as normal, high, missing, or review.

### Why

A numeric value alone is not enough for a safe review workflow. Explicit states help users identify which fields need attention.

### Tradeoff

State assignment logic must be consistent across parsing, interpretation, and the interface.

## 7. Editable Report Output

### Decision

Generate a report draft that remains editable and can be copied, opened in Microsoft Word, or exported as DOCX.

### Why

Clinicians need control over phrasing, findings, impressions, and formatting before final use.

### Tradeoff

Export behavior must preserve document structure while remaining compatible with external editors.

## 8. Configurable Statements and Templates

### Decision

Use selectable findings and configurable report templates rather than hard-coding one final report.

### Why

Reporting preferences vary across doctors and clinics. Configurable content improves reuse and adaptability.

### Tradeoff

Template and option management add interface and validation complexity.

## 9. Synthetic Public Examples

### Decision

Use synthetic data for screenshots, demonstrations, and public documentation.

### Why

This allows the project to be showcased without exposing patient or clinic information.

### Tradeoff

Synthetic examples demonstrate workflow behavior but do not prove real-world clinical validation.

## 10. Private Production Source

### Decision

Keep the complete production implementation in a private repository and maintain a separate public showcase repository.

### Why

This protects proprietary work while still allowing employers to review:

- Product screenshots
- Architecture
- Testing approach
- Engineering decisions
- Privacy boundaries
- Project scope

### Tradeoff

Public reviewers cannot inspect the full implementation without a private technical review.

## 11. Focused Initial Scope

### Decision

Limit the first version to abdomen ultrasound reporting.

### Why

A narrow initial scope makes it possible to validate the full workflow before expanding into additional study types.

### Tradeoff

The application is not yet a general-purpose radiology reporting platform.

## Future Considerations

Potential future work includes:

- Additional ultrasound study types
- Improved template-layout support
- Expanded synthetic evaluation datasets
- Packaging and installation improvements
- More configurable reference rules
- Broader export customization
- Formal clinical and regulatory validation
