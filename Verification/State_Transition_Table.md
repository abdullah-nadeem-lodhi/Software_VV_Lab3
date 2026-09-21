| Transition_ID | FromState | Event | ToState | Req_ID |
| ------------- | --------- | ----- | ------- | ------ |
| T-01 | IDLE | Delivery Request Received | NAVIGATING | R-02 |
| T-02 | NAVIGATING | Obstacle Detected | AVOIDING_OBSTACLE | R-04 |
| T-03 | AVOIDING_OBSTACLE | Obstacle Avoided | NAVIGATING | R-05 |
| T-04 | NAVIGATING | Destination Reached | DELIVERING | R-06 |
| T-05 | DELIVERING | Delivery Successful | RETURNING | R-08 |
| T-06 | NAVIGATING | Critical Battery | RETURNING | R-09 |
| T-07 | RETURNING | Warehouse Reached | IDLE | R-10 |

# Verification Findings

## Check 1 — Invalid Transition

**Check:** `IDLE → DELIVERING`

**Result:** INVALID.

**Violated requirement:** **R-07**.

The robot must first receive a delivery request and navigate toward the destination before entering `DELIVERING`. The transition table contains no direct `IDLE → DELIVERING` transition.

## Check 2 — Missing Transition

**Check:** `NAVIGATING → AVOIDING_OBSTACLE`

If there were no `AVOIDING_OBSTACLE → NAVIGATING` transition, this would be a missing transition. The robot could become stuck in obstacle-avoidance mode and would not continue toward its destination.

The missing transition should be:

- **Transition:** `AVOIDING_OBSTACLE → NAVIGATING`
- **Event:** `Obstacle Avoided`
- **Requirement:** `R-05`

This transition is present in the transition table as **T-03**.

## Check 3 — Obstacle During Delivery

**Check:** `AVOIDING_OBSTACLE → DELIVERING`

**Result:** INVALID.

The robot must return to `NAVIGATING` after avoiding the obstacle and must reach the destination before entering `DELIVERING`. The transition table contains no direct `AVOIDING_OBSTACLE → DELIVERING` transition.

**Related requirement:** **R-07**.

## Final Verification Summary

| Check                                  | Result       | Requirement/Issue |
| -------------------------------------- | ------------ | ----------------- |
| IDLE → DELIVERING                      | INVALID      | R-07              |
| Missing AVOIDING_OBSTACLE → NAVIGATING | DEFECT FOUND | R-05              |
| AVOIDING_OBSTACLE → DELIVERING         | INVALID      | R-07              |
