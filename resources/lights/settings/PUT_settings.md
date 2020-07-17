# Change Device Behavior Settings

    PUT /lights/settings

## URI Parameters
None

## Body Parameters

| Field                 | Data Type | Required |
| --------------------- | --------- | -------- |
| colorChangeDurationMs | int       | ?        |
| powerOnBehavior       | int       | ?        |
| powerOnBrightness     | int       | ?        |
| powerOnTemperature    | int       | ?        |
| switchOffDurationMs   | int       | ?        |
| switchOnDurationMs    | int       | ?        |

## Example

### Request
    
    curl --location --request PUT 'http://192.168.1.61:9123/elgato/lights/settings' --header 'Accept: application/json' --data-raw '{
        "powerOnBehavior": 0
    }'

### Response

    {
        "powerOnBehavior": 0,
        "powerOnBrightness": 20,
        "powerOnTemperature": 213,
        "switchOnDurationMs": 100,
        "switchOffDurationMs": 300,
        "colorChangeDurationMs": 100
    }
