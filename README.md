# DuckyPad Health Reminders — Custom Configurator Mod

A community modification of the [duckyPad Configurator](https://github.com/dekuNukem/duckyPad) that adds a **Health Reminders** system. Your duckyPad lights up on a schedule to remind you to take eye breaks, drink water, stretch, stand up, take meds, and more — all configurable from inside the app.

---

## ⚠️ Disclaimer — Please Read

> **USE AT YOUR OWN RISK.**
>
> This is an unofficial, community-made modification and is **not affiliated with, endorsed by, or supported by** the original duckyPad project or its author (dekuNukem). This mod modifies the official duckyPad Configurator source code.
>
> By using this software you agree that the author(s) of this mod are **not responsible** for any damage to your duckyPad device, data loss, software conflicts, or any other issues that may arise. If something breaks, you are on your own.
>
> Always keep a backup of your original duckyPad configuration before making changes.

---

## What This Mod Adds

### Health Reminders Panel

A new **"Health Reminders"** button appears in the Resources section of the configurator. Clicking it opens a panel where you can manage scheduled LED reminders:

| Reminder | Default Interval | Default Color |
|---|---|---|
| Eye Break | Every 20 min | Amber |
| Stretch | Every 30 min | Green |
| Water | Every 45 min | Blue |
| Stand Up | Every 60 min | Pink |
| Meds | Every 4 hours | Purple |

You can also add custom reminders with any name, color, interval, and title/subtitle.

### Features

- **Per-reminder LED color** — pick any RGB color for each reminder
- **Key shape editor** — choose which of the 20 keys light up for each reminder, with per-key custom colors
- **Titles and subtitles** — customize the display name and description for each reminder
- **Enable/disable individually** — toggle any reminder on or off without deleting it
- **Interval control** — set any interval from 1 to 480 minutes
- **Config file** — reminders are saved to `health_reminders.txt` on your duckyPad's SD card and persist across sessions

---

## Installation

This mod patches the duckyPad Configurator Python source. You need a working Python environment and the original configurator dependencies.

### Requirements

- Python 3.10 or later (tested on 3.14)
- The dependencies listed in `duckyPad-Configurator/src/requirements.txt`
- A duckyPad device (any version supported by the upstream configurator)

### Steps

1. **Clone this repo**
   ```bash
   git clone https://github.com/tjproconsulting/duckypad-health-reminders.git
   cd duckypad-health-reminders
   ```

2. **Install dependencies**
   ```bash
   pip install -r duckyPad-Configurator/src/requirements.txt
   ```

3. **Run the configurator**
   ```bash
   python duckyPad-Configurator/src/duckypad_config.py
   ```

4. **Configure your reminders**
   - Connect your duckyPad
   - Click **"Health Reminders"** in the Resources section
   - Set your intervals, colors, and key shapes
   - Click **Save & Close**
   - Sync to your duckyPad as normal

---

## The `health_reminders.txt` Config File

The file lives on your duckyPad's SD card root. Format:

```
# Health Reminders Config
# FORMAT: key enabled(0/1) interval_minutes R G B
eyes     1  20  255 180   0
stretch  1  30    0 220  80
water    1  45    0 120 255
stand    1  60  255  60 180
meds     1 240  180   0 255
```

You can edit this file directly or use the in-app editor.

---

## Credits

- Original duckyPad Configurator: [dekuNukem](https://github.com/dekuNukem/duckyPad) — all core functionality is their work
- Health Reminders mod: community modification

---

## License

The original duckyPad Configurator is licensed under its own terms — see the [upstream repo](https://github.com/dekuNukem/duckyPad). This modification inherits those terms. No additional license is claimed over the modification itself beyond what the upstream project permits.
