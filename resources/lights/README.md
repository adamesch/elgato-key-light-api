# Lights Object

| Field       | Data Type | Read Only | Description                           |
| ----------- | --------- | --------- | ------------------------------------- |
| on          | int       | N         | power state, `0` \| `1`               |
| brightness  | int       | N         | light brightness , `0` - `100` (*)    |
| temperature | int       | N         | color temperature, `143` - `344` (**) |

## Considerations
(*) Attempting to set a light's brightness to a low value like `2` may not do anything.

(**) The 'Control Center' UI only allows color temperature changes from 2900K - 7000K in 50K increments. To convert the values used by the API to Kelvin (like it is displayed in the Elgato application), divide by 0.05 (e.g. 143 / 0.05 = 2860 ≈ 2900K). To covert from Kelvin to API values, multiply by 0.05 (e.g. 7000K ≈ 6880 * 0.05 = 344)
