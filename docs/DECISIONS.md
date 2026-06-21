# Design Decisions

## Four-Room Structure

The one-screen company map became too visually noisy.

Decision:
Use four visitable rooms instead.

Rooms:

- 현장
- 조립실
- 사무실
- 설계실

Reason:
Each room should carry a different emotional role.

- 현장 = tension
- 조립실 = progress
- 사무실 = fear
- 설계실 = hope

## Bright UI

The game subject is heavy: cashflow pressure, labor risk, debt, bankruptcy, supplier tension, and legal risk.

Decision:
Keep the UI bright and readable.

Reason:
If both content and UI are dark, the game becomes exhausting too quickly.

## Cute Animal Workers

Decision:
Use cats, dogs, and owls.

Reason:
They soften the harsh subject matter and create black-comedy contrast.

The characters should look tired, not purely cheerful.

## 36-Unit Assembly System

Decision:
Use a 36-unit SMT screen printer batch.

Batch structure:

- 12 frame units
- 12 internal assembly / PLC units
- 12 idle run units

Reason:
The player needs visible progress, not only financial stress.

## Future Character Animation

Current:
Fake motion with layered PNGs.

Future:
Character-free backgrounds plus transparent character sprites or sprite sheets.

Reason:
If characters are baked into the background, real animation becomes difficult.

## GitHub Structure

Decision:
Use GitHub as the source of truth.

Reason:
ChatGPT conversations are good for iteration, but GitHub is better for version control and recoverability.
