# Luau Themed Lighting Automation

This blueprint creates a Luau party atmosphere by slowly cycling multiple RGB lights through tropical colors. It is designed to be triggered from a dashboard button or any event in Home Assistant.

## Features

- Select multiple RGB lights for the effect
- Customizable color change delay and number of cycles
- Easy to trigger from a dashboard button
- Luau-inspired color palette

## Setup Instructions

1. **Import the Blueprint**
   - Copy the YAML from `luau_lighting.yaml` and import it as a blueprint in Home Assistant.
2. **Create an Automation**
   - Use the blueprint to create an automation, selecting your RGB lights and customizing options as desired.
3. **Add a Dashboard Button**
   - Add a new button card to your dashboard.
   - Set the button action to **Call Service**.
   - Service: `event.fire`
   - Service Data:
     ```yaml
     event_type: luau_lighting_start
     ```
   - (Optional) Set an icon and label for your Luau button.

## Example Button YAML (Manual Card)

```yaml
type: button
name: Start Luau Lighting
icon: mdi:party-popper
tap_action:
  action: call-service
  service: event.fire
  data:
    event_type: luau_lighting_start
```

## Can this be automated?

You can trigger the event from any automation, script, or dashboard element. For example, you could trigger it at sunset or when a party mode is activated by firing the `luau_lighting_start` event.

## Notes

- The automation will cycle through the color palette for the selected number of cycles.
- You can edit the color palette in the blueprint if you want to customize the effect.
