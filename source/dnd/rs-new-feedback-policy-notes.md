# Runestone New Feedback Policy

> **Status (2026-07-04):** raw observation record, kept as provenance. The confirmed model
> is encoded in the journal (`ch-item-design.ptx`, `subsec-platform-feedback-policies`):
> graded feedback reads out σ(X)/w(X)/u(X); the check gate is `placed(X) ≥ ℓ₀`; refused
> presses are logged but ungraded; highlighting starts on the third graded check. The
> **legacy** policy (through Spring 2026) was a single layer equivalent to φ3 — counts +
> highlighting from the first check on any state (owner clarification, 2026-07-04).
> Follow-up work: FP-1..FP-4 in `dev/claude-build-tasks/proteus-dnd-alignment-build-checklist.md`.

## Key

| Cards | Slots
| :--   | :--  
| `__`  | `C1` `C2` 
| `__`  | `C3` 
| `__`  | `__` 
| `C4`  |

---
### State 1

| Cards | Slots
| :--   | :--  
| `C1`  | `__` 
| `C2`  | `__` 
| `C3`  | `__` 
| `C4`  |

Check Effect: 
* Highlighting: None
* Message: 
`
Please place all of the cards before checking your answer. You have 3 left to place.
`
* Notes: Pressing check without moving has no effect

---
### State 2

| Cards | Slots
| :--   | :--  
| `__`  | `__` 
| `C2`  | `__` 
| `C3`  | `C1` 
| `C4`  |

Check Effect: 
* Highlighting: None
* Message: 
`
Please place all of the cards before checking your answer. You have 2 left to place.
`
* Note: Pressing check without moving has no effect
* Note: Pressing reset takes you back to **State 1**

---
### State 3

| Cards | Slots
| :--   | :--  
| `__`  | `C1` 
| `C2`  | `__` 
| `C3`  | `__` 
| `C4`  |

Check Effect: 
* Highlighting: None
* Message: 
`
Please place all of the cards before checking your answer. You have 2 left to place.
`

---
### State 4

| Cards | Slots
| :--   | :--  
| `__`  | `C1` 
| `C2`  | `__` 
| `C3`  | `C4` 
| `__`  |

Check Effect: 
* Highlighting: None
* Message: 
`
Please place all of the cards before checking your answer. You have 1 left to place.
`

---
### State 5

| Cards | Slots
| :--   | :--  
| `__`  | `C1` 
| `__`  | `C2` 
| `C3`  | `C4` 
| `__`  |

Check Effect: 
* Highlighting: None
* Message: 
`
Incorrect. Of the cards you have sorted you placed 1 correctly and 2 incorrectly. You have 1 left to place.
`

---
### State 6

| Cards | Slots
| :--   | :--  
| `__`  | `C1` 
| `__`  | `C2` `C3` 
| `__`  | `C4` 
| `__`  |

Check Effect: 
* Highlighting: None
* Message: 
`
Incorrect. Of the cards you have sorted you placed 2 correctly and 2 incorrectly. You have 0 left to place.
`

---
### State 7

| Cards | Slots
| :--   | :--  
| `__`  | `C1` 
| `__`  | `C2` `C3` `C4`
| `__`  |  
| `__`  |

Check Effect: 
* Highlighting: `C2` `C4` 
* Message: 
`
Incorrect. Of the cards you have sorted you placed 2 correctly and 2 incorrectly. You have 0 left to place.
`

---
### State 8

| Cards | Slots
| :--   | :--  
| `__`  | `C1` `C2` 
| `__`  | `C3` `C4`
| `__`  |  
| `__`  |

Check Effect: 
* Highlighting: `C4`
* Message: 
`
Incorrect. Of the cards you have sorted you placed 3 correctly and 1 incorrectly. You have 0 left to place.
`

---
### State 9

| Cards | Slots
| :--   | :--  
| `__`  | `C1` `C2` 
| `__`  | `C3`
| `__`  |  
| `C4`  |

Check Effect: 
* Highlighting:
* Message: 
`
You are correct!
`

---