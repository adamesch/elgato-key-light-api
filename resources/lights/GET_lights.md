# Get Current Lighting Profile

    GET /lights

## URI Parameters
None

## Example

### Request
    
    curl --location --request GET 'http://192.168.1.61:9123/elgato/lights' --header 'Accept: application/json'

### Response

    {
        "numberOfLights": 1,
        "lights": [
            {
                "on": 0,
                "brightness": 25,
                "temperature": 166
            }
        ]
    }
