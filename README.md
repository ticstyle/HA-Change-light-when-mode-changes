# Change Light When Mode Changes

[![Validate Blueprint](https://github.com/ticstyle/HA-Change-light-when-mode-changes/actions/workflows/validate.yml/badge.svg)](https://github.com/ticstyle/HA-Change-light-when-mode-changes/actions/workflows/validate.yml)

A Home Assistant automation blueprint that dynamically adjusts light brightness levels and optional switches whenever your home's mode changes (`Morning`, `Day`, `Evening`, `Night`, `Away`).

---

## 🌟 Features

* **Mode-Driven Lighting:** Automatically sets predefined light brightness percentages matching your active day mode.
* **Optional Switch Control:** Easily enable/disable power switches or outlets alongside your lights for each mode.
* **Network Load Spreading:** Implements a randomized delay (5–31 seconds) to distribute Zigbee/Z-Wave network traffic when running multiple automation instances simultaneously.
* **Away Mode Shutoff:** Automatically turns off targeted lights and switches when mode switches to **Away**.
* **Modern UI Sections:** Organized into collapsible UI configuration sections inside Home Assistant for a clean, intuitive setup.

---

## 📋 Dependencies

This blueprint relies on an entity tracking your active day modes (supporting states `Morning`, `Day`, `Evening`, `Night`, `Away`).

* Recommended Integration: [Day Modes for Home Assistant](https://github.com/ticstyle/Day-Modes) (Available via HACS).
* *Alternative:* Any standard `input_select` or `sensor` entity returning matching state values.

---

## 🚀 Installation

### Option 1: Direct Import via My Home Assistant
Click the button below to import the blueprint directly into your Home Assistant instance:

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fticstyle%2FHA-Change-light-when-mode-changes%2Fblob%2Fmain%2Fchange_light_when_mode_changes.yaml)

### Option 2: Manual Import
1. In Home Assistant, go to **Settings** > **Automations & Scenes** > **Blueprints**.
2. Click **Import Blueprint** in the bottom right corner.
3. Paste the blueprint URL:
   ```text
   [https://github.com/ticstyle/HA-Change-light-when-mode-changes/blob/main/change_light_when_mode_changes.yaml](https://github.com/ticstyle/HA-Change-light-when-mode-changes/blob/main/change_light_when_mode_changes.yaml)
   ```
4. Click **Preview** and then **Import**.

---

## ⚙️ Configuration Inputs

| Section | Input | Description | Default |
|---|---|---|---|
| **General** | `mode` | Sensor or input_select tracking day modes | `sensor.day_modes` |
| **General** | `light_target` | Target light entity, device, or area | `{}` |
| **General** | `control_switches` | Master toggle to enable switch/outlet control | `false` |
| **General** | `switch_target` | Target switch entity, device, or area | `{}` |
| **Morning** | `morning_toggle` | Enable processing for Morning mode | `true` |
| **Morning** | `morning_brightness` | Light brightness percentage (0–100%) | `10%` |
| **Morning** | `morning_switch_on` | Turn switches ON or OFF during Morning | `true` |
| **Day** | `day_toggle` | Enable processing for Day mode | `true` |
| **Day** | `day_brightness` | Light brightness percentage (0–100%) | `75%` |
| **Day** | `day_switch_on` | Turn switches ON or OFF during Day | `true` |
| **Evening** | `evening_toggle` | Enable processing for Evening mode | `true` |
| **Evening** | `evening_brightness` | Light brightness percentage (0–100%) | `35%` |
| **Evening** | `evening_switch_on` | Turn switches ON or OFF during Evening | `true` |
| **Night** | `night_toggle` | Enable processing for Night mode | `true` |
| **Night** | `night_brightness` | Light brightness percentage (0–100%) | `0%` |
| **Night** | `night_switch_on` | Turn switches ON or OFF during Night | `false` |
| **Away** | `away_toggle` | Enable processing for Away mode | `true` |
| **Away** | `away_switch_on` | Turn switches ON or OFF during Away | `false` |

---

## 📄 License

This project is open-source and licensed under the [MIT License](LICENSE).
