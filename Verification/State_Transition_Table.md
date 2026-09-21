| Transition_ID | FromState | Event | ToState | Req_ID |
| ------------- | --------- | ----- | ------- | ------ |
| T-01 | IDLE | Delivery Request Received | NAVIGATING | R-02 |
| T-02 | NAVIGATING | Obstacle Detected | AVOIDING_OBSTACLE | R-04 |
| T-03 | AVOIDING_OBSTACLE | Obstacle Avoided | NAVIGATING | R-05 |
| T-04 | NAVIGATING | Destination Reached | DELIVERING | R-06 |
| T-05 | DELIVERING | Delivery Successful | RETURNING | R-08 |
| T-06 | NAVIGATING | Critical Battery | RETURNING | R-09 |
| T-07 | RETURNING | Warehouse Reached | IDLE | R-10 |
