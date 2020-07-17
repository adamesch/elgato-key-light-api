# Change Device Hardware Info

    PUT /accessory-info

## URI Parameters
None

## Body Parameters

| Field               | Data Type | Required  |
| ------------------- | --------- | --------- |
| productName         | string    | ?         |
| hardwareBoardType   | int       | ?         |
| firmwareBuildNumber | int       | ?         |
| firmwareVersion     | string    | ?         |
| serialNumber        | string    | ?         |
| displayName         | string    | ?         |
| features[]          | string    | ?         |

## Example

### Request
    
    curl --location --request PUT 'http://192.168.1.61:9123/elgato/accessory-info' --header 'Accept: application/json' --data-raw '{
        "productName": "MyKeyLight"
    }'

### Response

    {
        "productName": "Elgato Key Light",
        "hardwareBoardType": 53,
        "firmwareBuildNumber": 192,
        "firmwareVersion": "1.0.3",
        "serialNumber": "XXXXXXXXXXXX",
        "displayName": "MyKeyLight",
        "features": [
            "lights"
        ]
    }
