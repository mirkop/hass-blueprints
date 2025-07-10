# Luau Themed Lighting Automation

This Home Assistant blueprint creates a Luau party atmosphere by cycling multiple RGB lights through a vibrant, customizable palette of tropical colors. It supports advanced per-light color cycling, randomization, and is designed for easy triggering and stopping from the dashboard or automations.

## Features

- Select multiple RGB lights for the effect
- Advanced color cycling: each light gets a random color from the palette, always different from its current color
- Customizable Luau-inspired color palette (edit in the blueprint)
- Adjustable delay between lights and between cycles
- Set the total runtime in minutes (automatically calculates cycles)
- Adjustable transition time for smooth color changes
- Robust error handling (e.g., empty light list or palette)
- Easy to start and stop from dashboard buttons or automations
- Well-documented for both users and contributors

## How It Works

- The automation triggers a script that cycles each selected RGB light through the chosen palette.
- Each light is assigned a random color (never the same as its current color) on each cycle.
- Delays between lights and cycles create a dynamic, party-like effect.
- The script can be stopped at any time from the dashboard.

## Setup Instructions

1. **Import the Blueprint**
   - Copy the YAML from `luau_lighting_automation.yaml` and import it as a blueprint in Home Assistant.
2. **Create an Automation**
   - Use the blueprint to create an automation, selecting your RGB lights and customizing options as desired.
3. **Add Dashboard Buttons**
   - **Start Button:** Add a button card to your dashboard to start the effect.
   - **Stop Button:** Add a button card to stop the effect (calls the script's `turn_off` service).

### Example Start Button YAML (Manual Card)

```yaml
type: button
name: Start Luau Lighting
icon: mdi:party-popper
tap_action:
  action: call-service
  service: automation.trigger
  target:
    entity_id: automation.luau_lighting
```

Replace `automation.YOUR_LUAU_AUTOMATION_ENTITY_ID` with the actual entity ID of your Luau automation (e.g., `automation.luau_lighting`).

### Example Stop Button YAML (Manual Card)

```yaml
type: button
name: Stop Luau Lighting
icon: mdi:stop-circle
tap_action:
  action: call-service
  service: script.turn_off
  target:
    entity_id: script.luau_themed_lighting_script
```

## Customization

- **Color Palette:** Edit the palette in the blueprint YAML to match your preferred Luau colors.
- **Delays & Transition:** Adjust the delay between lights, delay between cycles, and transition time for different effects.
- **Total Runtime:** Set how many minutes the effect should run (cycles are calculated automatically).

## Usage Notes

- The automation and script are designed to work together. The automation triggers the script, which handles the color cycling logic.
- You can trigger the automation from any event, schedule, or dashboard button.
- The script can be stopped at any time using the stop button or by calling `script.turn_off`.
- All logic is robust against empty lists and invalid input.

## For Contributors

- See `docs/CONTRIBUTING.md` for contribution guidelines.
- All blueprints are documented and commented for clarity.
- Please keep user and contributor documentation up to date with any changes.

## Related Files

- `blueprints/automation/luau/luau_lighting_automation.yaml` – The automation blueprint
- `blueprints/script/luau/luau_lighting_script.yaml` – The script blueprint (core color cycling logic)
- `docs/USAGE.md` – Detailed usage and integration instructions

---

Enjoy your Luau party lighting! For questions or suggestions, see the main project README or open an issue on GitHub.
