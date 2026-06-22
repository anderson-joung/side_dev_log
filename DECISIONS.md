# DECISIONS

## Current direction

The game is a survival management simulation, not a company expansion fantasy. The point is to survive the month.

## GitHub structure

Use a simple static web structure: root `index.html` plus `assets/`. No build step.

## Art direction

Room backgrounds should stay character-free. Moving characters should be transparent overlay assets so layout and readability can be controlled in CSS.

## Finance direction

Do not show detailed manufacturing cost every time one unit ships. Small companies do not have that level of clean ERP visibility. Show estimated COGS only in monthly reports.

## Event direction

Events should be short, concrete, and operational. Costs must be believable relative to unit selling price.

## Versioning

This package is named v5.0 because the project title and public direction changed from the earlier prototype branch.
