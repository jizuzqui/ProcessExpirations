jBPM showcase regarding process and tasks expirations.
=======================

It includes:
- A BPMN process showing global expiration with a event subprocess
- A BPMN process showing subprocess expiration.
- A BPMN process showing user task expiration
- A BPMN process showing DueDate usage for informative user tasks SLA's.

To reschedule a timer, you should invoke following endpoint:

PUT http://localhost:8080/kie-server/services/rest/server/containers/<container-id>/processes/instances/<process-instance-id>/timers/<timer-id>
-d   
'{
  "delay" : 180
}'
  
--> The specified timer will be fired in 180 seconds
  
To get all timers in a process instance:
  
  
GET http://localhost:8080/kie-server/services/rest/server/containers/<container-id>/processes/instances/<process-instance-id>/timers/<timer-id>
  
{
  "timer-instance": [
    {
      "name": "Inform Payment Data-Expires after 1 minute",
      "id": 1,
      "timer-id": 1,
      "activation-time": {
        "java.util.Date": 1626272737412
      },
      "last-fire-time": null,
      "next-fire-time": {
        "java.util.Date": 1626272797412
      },
      "delay": 60000,
      "period": 0,
      "repeat-limit": -1,
      "process-instance-id": 127,
      "session-id": 935
    }
  ]
}
