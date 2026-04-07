# Projection Pattern: Person · Flat · Singular (P-F-S)

## Source Artifact
- Report: Spanish Course / Formación Ministerial Report
- Type: Custom People Report (List-based)
- Evidence:
  - Template loops over people → person
  - One visual block per person
  - PDF output confirms 1:1 rendering

## Projection Definition
- Root Entity (Observed): person
- Primary Iterator (Observed): people
- Output Unit: One person per block/page
- Projection Type: Flat
- Expansion: None

## Projection Signature
- Iterator: for person in people
- Expansion: none
- Output Unit: 1 person per block/page

## Cardinality
- Person → Output: 1:1

## Access Paths (Observed)
- person.name
- person.photo_url
- person.primary_email
- person.primary_phone_number
- person.primary_address.postal_address
- person.custom_tabs.ministerio_hispano.comienzo
- person.custom_tabs.ministerio_hispano.animador
- person.custom_tabs.ministerio_hispano.vf.value
- person.custom_tabs.ministerio_hispano.ess.value
- person.custom_tabs.ministerio_hispano.sdm.value
- person.custom_tabs.ministerio_hispano.gp.value

## Observed Behaviors
- primary_email renders directly without .address
- primary_phone_number renders directly without .number
- mixed access patterns for custom fields (some require .value, others do not)
- conditional rendering used heavily with "!= blank"
- empty fields are suppressed in output, not structurally absent

## Rendering Characteristics
- layout is card-based and vertically stacked
- optimized for print (PDF)
- uses @page rules
- includes print-only and screen-only elements

## Output Behavior
- consistent per-person structure
- many fields structurally available but not populated
- sections render even when inner values are empty

## Intent Classification
- Profile / Dossier Report
- Individual-centric visibility

## Notes
- confirms structured custom tab hierarchy
- confirms runtime type coercion behavior
- confirms nullability handling via conditionals
- does not expose relational expansion

## Confidence
- Projection Definition: High
- Access Paths: High
- Relationship Mapping: High (no relational expansion observed)
