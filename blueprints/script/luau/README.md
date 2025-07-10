# Luau Themed Lighting Script

This advanced Home Assistant script cycles each selected RGB light through a unique color from a Luau-inspired palette, creating a festive party atmosphere.

## Features

- Each light gets a different color at each step
- Customizable delay, transition, and repeat count
- Works with any number of RGB lights

## Usage

1. Import the script YAML from `luau_lighting_script.yaml` into Home Assistant as a script.
2. Call the script and provide:
   - A list of RGB light entities
   - (Optional) Delay between color changes, transition time, and repeat count

## Example Service Call

```yaml
service: script.luau_themed_lighting_script
data:
  lights:
    - light.living_room
    - light.kitchen
  cycle_delay: 15
  repeat_count: 30
  transition_time: 5
```

## Notes

- The color palette can be customized in the script variables.
- This script is not a blueprint, so it must be imported as a script and called directly.
