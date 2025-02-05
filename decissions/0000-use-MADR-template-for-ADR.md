# 0000 Use MADR full template for to reflect decisions in a consistent ADR format

## Context and Problem Statement

ADRs are practically a requirement for an Architecture Kata.

## Decision Drivers (Why)

* Clarity (judge criteria). Probably appreciated after reviewing N git repos
* Should have a trade-offs section
* Fast decision. (avoid bikeshedding and start with the hard stuff)

## Considered Options

* Custom template
* MADR
    * Full
    * Minimal
* ISO/IEC/IEEE 42010, 5.2

## Decision Outcome

Use the MADR full template but customize by removing the following optional elements

* Status
* Date
* Decision makers
* Confirmation

Also: 
* Adjusted a few titles with parenthesis explanations 
* Moved Trade-Offs a level in importance

## Consequences (Trade-Offs)

* Good
    * We use a standard format and consistent format
    * Designed for markdown
    * Removing non-applicable fields should improve clarity. (Nice after evaluating 100 projects)

* Price to pay:
    * If anybody ever wants to check the evolution of ADRs, the info will only be on git history.
    * No status is handled. (proposed, approved). But we need to decide very fast.
    * We Will have to explain our decisions in a straitjacketed format. 
