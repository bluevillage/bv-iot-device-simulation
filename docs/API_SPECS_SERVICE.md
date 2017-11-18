API specifications - Service
============================

## Service status

Request:
```
GET /v1/status
```

Response:
```
200 OK
Content-Type: application/JSON
```
```json
{
    "Name": "DeviceSimulation",
    "Status": "OK:Alive and well|ERROR:...msg...",
    "CurrentTime": "2017-08-22T00:27:30+00:00",
    "StartTime": "2017-08-22T00:26:32+00:00",
    "UpTime": "88",
    "UID": "779e748b-fc97-4eb4-adcd-2fbe51df619c",
    "Properties": {
        "Simulation": "on|off"
    },
    "Dependencies": {
        "IoTHub": "OK|ERROR:...msg...",
        "Storage": "OK:...msg...|ERROR:...msg..."
    },
    "$metadata": {
        "$type": "Status;v1",
        "$uri": "/v1/status"
    }
}
```

* Status: the message is optional
* UpTime: value specific to the process running, i.e. in case of multiple
  deployments each instance has a different uptime
* UID: a unique value in each instance, used mostly for logging correlation
* Properties: used only for debugging, free form entries
* Dependencies: health status of the internal dependencies, values used
  only for debugging