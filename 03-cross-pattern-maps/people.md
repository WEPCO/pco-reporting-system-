# Cross-Pattern Access Map — People

## Purpose
This map identifies which access paths are:
- Stable across projection patterns
- Pattern-specific
- Inferred vs confirmed

---

## Entity: person

### person.name
- Patterns: P-F-S, P-R-E(H)
- Availability: Stable
- Access Type: Direct Field
- Confidence: High
- Notes: Consistently renders across both patterns

---

### person.photo_url
- Patterns: P-F-S, P-R-E(H)
- Availability: Stable
- Access Type: Direct Field
- Confidence: High
- Notes: Used for visual rendering

---

### person.primary_email
- Patterns: P-F-S
- Availability: Pattern-Specific
- Access Type: Direct Field (string-coercible)
- Confidence: High
- Notes: Renders directly without .address

---

### person.primary_phone_number
- Patterns: P-F-S
- Availability: Pattern-Specific
- Access Type: Direct Field (string-coercible)
- Confidence: High
- Notes: Renders directly without .number

---

### person.primary_address.postal_address
- Patterns: P-F-S
- Availability: Pattern-Specific
- Access Type: Nested Field
- Confidence: High
- Notes: Nested access required

---

### person.custom_tabs.*
- Patterns: P-F-S
- Availability: Pattern-Specific
- Access Type: Dynamic Field
- Confidence: High
- Notes: Structure varies by tab and field slug

---

## Entity: household

### person → households
- Patterns: P-R-E(H)
- Availability: Pattern-Specific
- Access Type: Inferred Relationship
- Confidence: Medium
- Notes: Derived from output showing multiple households per person

---

### household.name
- Patterns: P-R-E(H)
- Availability: Pattern-Specific
- Access Type: Inferred Nested Field
- Confidence: Medium
- Notes: Rendered repeatedly per person in expanded rows

---

## Summary

### Stable Across Patterns
- person.name
- person.photo_url

---

### Pattern-Specific (Flat Projection)
- person.primary_email
- person.primary_phone_number
- person.primary_address.postal_address
- person.custom_tabs.*

---

### Pattern-Specific (Relational Projection)
- person → households
- household.name

---

### Key Insight

Access to data in PCO People is not uniform.

It depends on:
- Projection pattern
- Expansion behavior
- Report design

No single pattern exposes the full data surface.

---

### Usage

Use this map to:
- determine which pattern is required for a report
- avoid assuming field availability across patterns
- guide normalization and report specification design
