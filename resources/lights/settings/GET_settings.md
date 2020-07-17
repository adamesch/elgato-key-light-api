# Get Device Behavior Settings

    GET /lights/settings

## URI Parameters
None

## Example

### Request
    
    curl --location --request GET 'http://192.168.1.61:9123/elgato/lights/settings' --header 'Accept: application/json'

### Response

    {
        "powerOnBehavior": 1,
        "powerOnBrightness": 20,
        "powerOnTemperature": 213,
        "switchOnDurationMs": 100,
        "switchOffDurationMs": 300,
        "colorChangeDurationMs": 100
    }
