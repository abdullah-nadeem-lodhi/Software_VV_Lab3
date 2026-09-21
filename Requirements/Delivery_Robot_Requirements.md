| Req ID | Description | Priority |
| ------ | ----------- | -------- |
| R-01   | The robot shall remain in an idle state when no valid delivery request is active and shall wait for a new request. | High |
| R-02   | When a valid delivery request is received, the robot shall accept the request and initiate navigation to the specified destination. | High |
| R-03   | The robot shall navigate from its current position to the assigned destination using a safe and continuous route and shall not deviate from the intended path without a valid reason. | High |
| R-04   | The robot shall detect obstacles in its path using onboard sensing devices and shall identify the obstacle location and distance before continuing movement. | High |
| R-05   | When an obstacle is detected, the robot shall stop and shall perform an obstacle avoidance action, such as rerouting or pausing until the path is clear. | High |
| R-06   | After obstacle avoidance is completed and the path is clear, the robot shall resume navigation toward the destination without requiring manual intervention. | High |
| R-07   | When the robot reaches the destination, it shall stop at the target location and shall confirm that the destination has been reached before starting the delivery action. | High |
| R-08   | Upon confirmation of destination arrival, the robot shall complete the delivery by releasing or handing over the item to the destination and shall mark the delivery as completed. | High |
| R-09   | If the battery level falls below the critical threshold during navigation or delivery, the robot shall immediately halt the current task and initiate return-to-warehouse behavior. | High |
| R-10   | The robot shall not transition to delivery, destination-reached, or completed-delivery status unless a valid delivery request has been accepted and navigation was active; invalid delivery transitions while idle, during obstacle avoidance, or during return-to-warehouse shall be prevented. | High |
