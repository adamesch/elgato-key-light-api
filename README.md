# Elgato Key Light API

## Introduction
The Elgato [Key Light](https://www.elgato.com/en/gaming/key-light) and [Key Light Air](https://www.elgato.com/en/gaming/key-light-air) are edge-lit LED video lights that are popular with live streamers on platforms like Twitch. These lights are IoT devices and are normally controlled with Elgato's 'Control Center' app or through one of the Stream Deck devices (also manufactered by Elgato). The Key Light devices do not natively support third-party integration, but they can be controlled by directly interfacing with the lights' built-in API.

## API Discovery
The 'Control Center' app sends commands to Key Light devices it has been associated to over HTTP. The API requests defined in this document were found using Wireshark and reference version 1.1.2 of the Elgato 'Control Center' app (Windows 10).

## Endpoints

### Device IP Address
After being added to a network, Key Light devices likely receive IP addresses from a router via DHCP. Specific IP addresses can be pulled from the DHCP server / network router, but they are also easily accessible in the 'Control Center' app. To do this:
1. Launch / Open the 'Control Center' app
2. Click on the `Accessory settings` icon (shaped like a slider) next to a device's name
3. Expand the `Advanced` section. **IP Address** will be presented under **Power On Behavior** and **Firmware Version**

### Device Port
Key Light devices listen for commands on port **9123**.

### Base URL
All requests should be sent to `/elgato`.

### Example
Get a device's current settings:

    curl --location --request GET 'http://192.168.1.61:9123/elgato/lights' --header 'Accept: application/json'

## Authentication
Key Light devices do not require authentication.

## Responses
Key Light devices only return two HTTP status codes:
- `200 OK` The request has succeeded.
- `400 Bad Request` The request was not understood by the device (likely because of malformed syntax)

Additionally, any data returned by a device will be JSON-formatted.

## Resources
There are only three resources implemented by the Key Light API
- `lights` lights objects contain information related to a Key Light device's current state, brighness, and color temperature
- `accessory-info` accessory-info objects contain information related to a Key Light device's physical hardware specifications
- `settings` settings objects contain information related to a Key Light device's behavior

## Functions
There is one 'action' implemented by the Key Light API:
- `identify` sending a HTTP POST requst to this endpoint will cause the given light to flash a few times 
