# Lights Object

| Field       | Data Type | Read Only | Description                           |
| ----------- | --------- | --------- | ------------------------------------- |
| on          | int       | N         | power state, `0` \| `1`               |
| brightness  | int       | N         | light brightness , `0` - `100` (*)    |
| temperature | int       | N         | color temperature, `143` - `344` (**) |

## Considerations
(*) Attempting to set a light's brightness to a low value like `2` may not do anything.

(**) The color temperature in the API is expressed in units of mired. The 'Control Center' UI only allows color temperature changes from 2900K - 7000K in 50K increments. To convert from Kelvins to mireds, divide 1,000,000 by degrees Kelvin, (e.g. 1,000,000 / 7000K ≈ 143). To convert from mireds to Kelvin, divide 1,000,000 by mireds. (e.g., 2900K ≈ 1,000,000 / 344).
