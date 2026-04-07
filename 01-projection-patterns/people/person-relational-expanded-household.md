# Projection Pattern: Person · Relational · Expanded (Household-Inferred) (P-R-E(H))

## Source Artifact
- Report: Multiple Household Report (HTML)
- Type: Custom People Report
- Evidence:
  - Output shows “is a part of X households”
  - Multiple household rows per person
  - HTML-rendered output (not PDF-only)

## Projection Definition
- Root Entity (Observed): person
- Primary Iterator (Observed): people (implicit)
- Output Unit: Person with multiple related household rows
- Projection Type: Relational
- Expansion: Household (inferred)

## Projection Signature
- Iterator: for person in people
- Expansion: inferred household expansion
- Output Unit: 1 person with N rows

## Cardinality
- Person → Households: 1:N (inferred)
- Person → Output Rows: 1:N

## Access Paths (Observed / Inferred)
- person.name
- person.photo_url
- person → households (inferred multi-valued relationship)
- household.name (rendered repeatedly per person)

## Observed Behaviors
- same person appears once with multiple household rows
- relationship expansion drives structure, not flat attributes
- household names may repeat (no enforced deduplication)
- conditional logic likely controls single vs multiple household cases
- output reflects raw relationship iteration

## Rendering Characteristics
- layout is table-based with grouped sections per person
- repeated row structure for households
- rendered as HTML inside platform environment
- styled with CSS classes for grouping and formatting

## Output Behavior
- relationship-driven output
- clear expansion per household
- visual grouping by person
- repetition possible within expanded rows

## Intent Classification
- Exception / Audit Report
- Relationship visibility
- Multi-household detection

## Notes
- confirms relational expansion as a first-class projection pattern
- demonstrates 1:N expansion within People reports
- highlights difference between attribute-based and relationship-based reports
- suggests presence of nested iteration even if not directly visible

## Confidence
- Projection Definition: High
- Access Paths: Medium (partially inferred)
- Relationship Mapping: Medium (inferred from output)
