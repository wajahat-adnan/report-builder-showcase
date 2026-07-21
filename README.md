# Report Builder





A local-first desktop application that converts structured radiology worksheets into editable ultrasound reports while keeping the clinician in control of the final output.



> This repository is a public engineering case study. The production source code is maintained privately because it contains proprietary implementation details. All examples shown here use synthetic or anonymized data.



\## Project Overview



Report Builder is designed to reduce repetitive report-writing work for individual doctors and small clinics.



The current version focuses on abdomen ultrasound reporting and supports a workflow built around:



1\. Uploading a worksheet image

2\. Extracting measurements with local OCR

3\. Reviewing detected values and interpretation states

4\. Editing structured findings

5\. Adding dictation and doctor instructions

6\. Generating an editable report

7\. Copying or exporting the report to Microsoft Word



\## Key Features



\- Local OCR processing without uploading patient documents

\- Anchor-based extraction of organ measurements

\- Deterministic measurement interpretation

\- Human review before report completion

\- Structured findings and selectable report statements

\- Dictation support

\- Editable report workspace

\- Numbered impressions

\- DOCX export and Microsoft Word integration

\- Configurable report templates



\## System Workflow





Worksheet Image

&#x20;     |

&#x20;     v

Local OCR Extraction

&#x20;     |

&#x20;     v

Anchor-Based Parsing

&#x20;     |

&#x20;     v

Measurement Interpretation

&#x20;     |

&#x20;     v

Clinician Review

&#x20;     |

&#x20;     v

Structured Report Assembly

&#x20;     |

&#x20;     v

Editable Report / DOCX Export
