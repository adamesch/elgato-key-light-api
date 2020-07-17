# Get Device Hardware Info

    GET /accessory-info

## URI Parameters
None

## Example

### Request
    
    curl --location --request GET 'http://192.168.1.61:9123/elgato/accessory-info' --header 'Accept: application/json'

### Response

    {
        "productName": "Elgato Key Light",
        "hardwareBoardType": 53,
        "firmwareBuildNumber": 192,
        "firmwareVersion": "1.0.3",
        "serialNumber": "XXXXXXXXXXXX",
        "displayName": "",
        "features": [
            "lights"
        ]
    }
