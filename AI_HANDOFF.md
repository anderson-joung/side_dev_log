# AI_HANDOFF

## Project

- Korean title: 이번 달까지만 버텨주세요
- English title: Please Let Us Survive This Month
- Genre: Korean SME manufacturing survival management simulation
- Current baseline: v5.0 GitHub-ready cleanup

## Current gameplay identity

A browser-based management prototype about surviving month to month as a small Korean manufacturer. The player manages production, cash flow, receivables, payables, design fixes, delivery pressure, and recurring absurd shop-floor incidents.

## Current rooms

1. 현장
2. 조립실
3. 사무실
4. 설계실

## Current production model

Order backlog flows through production stages. Overproduction should increase frame/production throughput, not magically increase orders. Idle/ready units ship out in small daily batches, and each shipped unit creates revenue using a unit price in the 50M-70M KRW range.

## Current finance model

- Revenue is recorded when units ship.
- Cash collection and receivables are split.
- COGS is estimated monthly only, using 75% +/- 5%.
- Monthly report includes simplified income statement, balance sheet, and manufacturing cost statement.
- Payables are intentionally dragged for 6-12 months.

## Current event direction

Events should be short, concrete, and operational. Avoid long VN-style dialogue. Good events are: label typo, tax invoice correction, outsourced manager death, Windows update PLC/programming issue, sales spec mistake causing overseas CS trip, Chinese competitor undercutting, industrial accident handling, rush snack costs.

## UI constraints

- Mobile first enough to play on a phone.
- Modals must scroll.
- Top bar must not hide event choices.
- Event cards must stay until user confirms.
- Text should be short.

## Important naming rule

Do not use old private branding or specific equipment-branding wording in user-facing game text. The current public-facing title is only:

- 이번 달까지만 버텨주세요
- Please Let Us Survive This Month
