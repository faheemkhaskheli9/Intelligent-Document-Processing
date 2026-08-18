# Architecture Notes: Universal Document Processing Pipeline

## Pipeline

```text
Document -> Classification -> Parsing/OCR -> Field Extraction -> Validation + Confidence Scoring -> Auto-Accept or Human Review
```

## Components

- Document classification
- PDF parsing
- Scanned document handling
- OCR extraction
- Field extraction
- Validation rules
- Confidence scoring
- Human review routing for low-confidence cases

## Design Notes

- Keep provider/model choices swappable behind interfaces (see `multi-llm-router`
  and similar projects in this portfolio for the general pattern).
- Prefer configuration-driven pipelines (YAML/JSON in `configs/`) over hardcoded
  parameters so experiments are reproducible.
