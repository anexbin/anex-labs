# System Failure Analysis

## Original Design Assumptions
- Input follows the documented grammar
- Valid structure implies safe intent
- Parser and interpreter agree on meaning
- Edge cases are rare

## What the System Trusts
- Syntax over semantics
- Validation over context
- Format correctness over intent

## What the System Does NOT Expect
- Inputs that are valid but malicious
- Ambiguous grammar abuse
- Meaning shifts between layers
- Inputs designed to exploit interpretation gaps

## Common Failure Modes
1. Ambiguous grammar (multiple valid interpretations)
2. Partial validation (syntax checked, semantics ignored)
3. Context loss during parsing
4. Double interpretation of the same input
5. Type confusion between components

## Failure Chains
Minor ambiguity → incorrect parse → unintended interpretation → logic misuse → trust boundary crossed

These failures look like “normal behavior,” not crashes.
