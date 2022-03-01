# Lights Object

| Field       | Data Type | Read Only | Description                           |
| ----------- | --------- | --------- | ------------------------------------- |
| on          | int       | N         | power state, `0` \| `1`               |
| brightness  | int       | N         | light brightness , `0` - `100` (*)    |
| temperature | int       | N         | color temperature, `143` - `344` (**) |

## Considerations
(*) Attempting to set a light's brightness to a low value like `2` may not do anything.

(**) The 'Control Center' UI only allows color temperature changes from 2900K - 7000K in 50K increments. To convert the values used by the API to Kelvin (like it is displayed in the Elgato application), you simply have to divide 1.000.000 by the given value and round the result to the nearest number divisable by 50.  
When a value higher than the minimum or maximum (`143` or `344`) is sent, the value will be set to the closer extreme.  
To convert values from Kelvin back to the API format, just divide 1.000.000 by the amount of Kelvin and round to the closest natural number.
