# Contextual Access Schema — People

## Pattern: Person · Flat · Singular (P-F-S)

### Root
- person

### Projection Signature
- Iterator: for person in people
- Expansion: none
- Output Unit: 1 person per block/page

### Cardinality
- Person → Output: 1:1

### Access Paths
- person.name (Direct Field)
- person.primary_email (Direct Field, string-coercible)
- person.primary_phone_number (Direct Field, string-coercible)
- person.primary_address.postal_address (Nested Field)
- person.custom_tabs.* (Dynamic Field)

### Notes
- custom_tabs structure partially dynamic
- some fields require `.value`
- direct rendering works for some object types (email, phone)
- empty values suppressed via conditionals

### Confidence
- High

---

## Pattern: Person · Relational · Expanded(Household-Inferred) (P-R-E(H))

### Root
- person

### Projection Signature
- Iterator: for person in people
- Expansion: inferred household expansion
- Output Unit: 1 person with N rows

### Cardinality
- Person → Households: 1:N (inferred)
- Person → Output Rows: 1:N

### Access Paths
- person.name (Direct Field)
- person.photo_url (Direct Field)
- person → households (Inferred Relationship)
- household.name (Inferred Nested Field)

### Notes
- household access inferred from output
- likely nested iteration exists but not directly observed
- output driven by relationship expansion
- duplication possible in rendered rows

### Confidence
- Medium (relationship inferred from output)
