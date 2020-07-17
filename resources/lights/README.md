# Lights Object

| Field       | Data Type | Read Only | Description                           |
| ----------- | --------- | --------- | ------------------------------------- |
| on          | int       | N         | power state, `0` \| `1`               |
| brightness  | int       | N         | light brightness , `0` - `100` (*)    |
| temperature | int       | N         | color temperature, `143` - `344` (**) |

## Considerations
(*) Attempting to set a light's brightness to a low value like `2` may not do anything.

(**) The 'Control Center' UI only allows color temperature changes from 2900K - 7000K in 50K increments. The Key Light API maps those values to a somewhat strange range of integers that may differ light to light. Values less than `143` or greater than `344` will automatically be changed to the appropiate extreme. If attempting to set a light's temperature to something specific, the easiest way to find the correct value to send would be
1. set the desired color temperature manually in the 'Control Center' app
2. query the value of that color temperature using `GET /lights`
