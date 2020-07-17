# Change Current Lighting Profile

    PUT /lights

## URI Parameters
None

## Body Parameters
Any combination of these fields can be passed in the request body

| Field       | Data Type | Required |
| ----------- | --------- | -------- |
| on          | int       | N        |
| brightness  | int       | N        |
| temperature | int       | N        |

## Example 1
Turn a device on, set brightness to 78%, change temperature to 3750K

### Request
    
    curl --location --request PUT 'http://192.168.1.61:9123/elgato/lights' --header 'Accept: application/json' --data-raw '{
        "numberOfLights": 1,
        "lights": [
            {
                "on": 1,
                "brightness": 78,
                "temperature": 266
            }
        ]
    }'

### Response

    {
        "numberOfLights": 1,
        "lights": [
            {
                "on": 1,
                "brightness": 78,
                "temperature": 266
            }
        ]
    }

## Example 2
Turn a device off

### Request
    
    curl --location --request PUT 'http://192.168.1.61:9123/elgato/lights' --header 'Accept: application/json' --data-raw '{
        "numberOfLights": 1,
        "lights": [
            {
                "on": 0
            }
        ]
    }'

### Response

    {
        "numberOfLights": 1,
        "lights": [
            {
                "on": 0,
                "brightness": 78,
                "temperature": 266
            }
        ]
    }
