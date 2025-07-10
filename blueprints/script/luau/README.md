# Luau Themed Lighting Script

This advanced Home Assistant script cycles each selected RGB light through a unique color from a Luau-inspired palette, creating a festive party atmosphere.

## Features

- Each light gets a different color at each step
- Customizable delay, transition, and total runtime (in minutes)
- Works with any number of RGB lights

## Usage

1. Import the script YAML from `luau_lighting_script.yaml` into Home Assistant as a script.
2. Call the script and provide:
   - A list of RGB light entities
   - (Optional) Delay between color changes, transition time, delay between lights, and total runtime in minutes

## Example Service Call

```yaml
service: script.luau_themed_lighting_script
data:
  lights:
    - light.living_room
    - light.kitchen
  cycle_delay: 15
  light_delay: 1
  transition_time: 5
  runtime_minutes: 20
```

## Dashboard Button to Stop the Script

Add this button to your dashboard to stop the Luau lighting script at any time:

```yaml
type: button
name: Stop Luau Lighting
icon: mdi:stop-circle
entity: script.luau_themed_lighting_script
tap_action:
  action: call-service
  service: script.turn_off
  target:
    entity_id: script.luau_themed_lighting_script
```

## Notes

- The color palette can be customized in the script variables.
- The script will run for approximately the total runtime specified, based on your timing settings.
- This script is not a blueprint, so it must be imported as a script and called directly.
