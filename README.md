# DDJ-FLX4 MIDI Mapping for djay Pro

A custom MIDI mapping configuration for the Pioneer DDJ-FLX4 controller in djay Pro, optimized for DJ performance with enhanced FX controls and deck-specific mappings.

## Overview

This MIDI mapping provides a comprehensive control scheme for the DDJ-FLX4 controller in djay Pro 5.4.4, with custom optimizations:

- **Neural Mix toggle** - Cue buttons now toggle Neural Mix (Unmixer EQ Mode) for each deck
- **FX1 controls** - Smart Fader and Release FX buttons toggle FX1 for Deck 1 and Deck 2
- **Crossfader FX** - Middle button toggles Crossfader FX
- **Filter controls** - Dedicated filter knobs for each deck
- **Cue points** - Full 8-cue point support per deck
- **Loop controls** - Comprehensive looping functionality
- **Library navigation** - Full music library control

## Controller

- **Model**: Pioneer DDJ-FLX4
- **USB ID**: 728956997
- **Software**: djay Pro 5.4.4

## Installation

1. **Locate your djay Pro MIDI Mappings folder:**
   - macOS: `~/Music/djay/MIDI Mappings/`

2. **Copy the mapping file:**
   ```bash
   cp "DDJ-FLX4 (DJ_Raion).djayMidiMapping" ~/Music/djay/MIDI\ Mappings/
   ```

3. **Load in djay Pro:**
   - Open djay Pro
   - Go to Preferences → MIDI Configuration
   - Select "DDJ-FLX4 (DJ_Raion)" from the dropdown menu
   - The mapping will be active immediately

## Key Features

### 🎛️ Custom Button Mappings

This mapping includes several customizations that differ from the default DDJ-FLX4 mapping:

#### Cue Buttons → Neural Mix Toggle
- **Deck 1**: Toggles Neural Mix (Unmixer EQ Mode) for Deck 1
- **Deck 2**: Toggles Neural Mix (Unmixer EQ Mode) for Deck 2
- The traditional Cue buttons now control Neural Mix separation

#### Smart Fader & Release FX Buttons → FX1 Toggle
- **Deck 1**: Toggles FX1 Enabled state for Deck 1
- **Deck 2**: Toggles FX1 Enabled state for Deck 2
- Quick access to enable/disable FX1 on each deck independently

#### Middle Button → Crossfader FX Toggle
- Toggles Crossfader FX mode
- Allows FX to be applied via the crossfader position

### Deck-Specific Mappings

All controls are mapped per-deck to allow independent operation:
- **Deck 1**: Primarily uses MIDI Channel 0, 4, 6, 7, 8
- **Deck 2**: Primarily uses MIDI Channel 1, 5, 9, 10

### Supported Features

- ✅ Crossfader and line volume controls
- ✅ EQ controls (Low, Mid, High) per deck
- ✅ Gain and filter knobs
- ✅ Jog wheel scratching and pitch bend
- ✅ Play/Pause controls
- ✅ Neural Mix toggle (via Cue buttons)
- ✅ 8 cue points per deck with pitch play support
- ✅ Loop controls (in, out, reloop, auto-loop)
- ✅ FX1 controls (select, enable, parameter, wet/dry)
- ✅ FX1 toggle via Smart Fader and Release FX buttons
- ✅ Crossfader FX toggle
- ✅ BPM sync and tap tempo
- ✅ Library navigation and queue management
- ✅ Sampler controls (8 players per deck)
- ✅ Looper tracks (4 tracks, 2 samples each)
- ✅ View mode switching
- ✅ Tools panel toggle

## File Structure

```
DDJ-FLX4 (DJ_Raion).djayMidiMapping
├── controls          # Array of MIDI input mappings
│   ├── keyPath       # Target action (e.g., turntable1.fx1Enabled)
│   ├── midiChannel   # MIDI channel (0-15)
│   ├── midiData      # MIDI note/CC number
│   ├── midiMessageType # 1=Note, 3=Control Change
│   └── output        # Optional feedback configuration
└── outputs           # Array of MIDI output mappings (LED feedback)
```

## Customization

### Editing the Mapping

The mapping file is an XML plist that can be edited with any text editor. Key fields:

- **`keyPath`**: The target action (e.g., `turntable1.fx1Enabled`, `turntableSelected.fxActive`)
- **`midiChannel`**: MIDI channel (0-15)
- **`midiData`**: MIDI note number (0-127) or CC number (0-127)
- **`midiMessageType`**: `1` = Note On/Off, `3` = Control Change
- **`buttonMode`**: `toggle` or `hold` for button behavior
- **`output`**: Dictionary for LED feedback (includes `midiMaxValue`)

### Common KeyPaths

- `turntable1.*` / `turntable2.*` - Deck-specific controls
- `turntableSelected.*` - Active deck controls
- `mixer.*` - Mixer controls
- `musicLibrary.*` - Library navigation
- `application.*` - Application-level controls

## Troubleshooting

### Button Not Working
- Check that the correct MIDI channel and note/CC are assigned
- Ensure no duplicate mappings exist for the same channel/note combination
- Verify the button is sending MIDI (use a MIDI monitor)

### LED Feedback Not Working
- Ensure the `output` dictionary is present with `midiMaxValue`
- Check that your controller supports MIDI output/feedback
- Verify the MIDI channel matches between input and output

### Both Decks Triggering
- Use deck-specific keyPaths (`turntable1.*`, `turntable2.*`) instead of `turntableSelected.*`
- Ensure different MIDI channels for deck-specific controls

## Related Resources

- [Algoriddim Community Forum - Issues remapping on DDJ-FLX4](https://community.algoriddim.com/t/issues-remapping-on-ddj-flx4/23804) - Discussion about custom DDJ-FLX4 mappings, featuring Michael_Wisniewski's original Unofficial mapping

## Contributing

Contributions are welcome! Please feel free to:
- Report bugs or issues
- Suggest improvements
- Submit pull requests with enhancements

## License

This MIDI mapping is provided as-is for use with djay Pro. Feel free to modify and share.

## Credits

- **Original MIDI Mapping Developer**: [Michael_Wisniewski](https://community.algoriddim.com/t/issues-remapping-on-ddj-flx4/23804) - Sole developer of the DDJ-FLX4 (Unofficial2.9) MIDI mapping 3.0
- **Customizations**: DJ_Raion - Minor personal customizations to the original mapping
- **Controller**: Pioneer DDJ-FLX4
- **Software**: djay Pro by Algoriddim

### Note on Customizations

This mapping is based on Michael_Wisniewski's excellent work on the DDJ-FLX4 (Unofficial2.9) mapping. The customizations made by DJ_Raion include:
- Remapping Cue buttons to toggle Neural Mix for each deck
- Remapping Smart Fader and Release FX buttons to toggle FX1 for Deck 1 and Deck 2
- Remapping the middle button to Crossfader FX toggle

These are personal preferences and may differ from the original mapping.

## Version History

- **Current Version**: Compatible with djay Pro 5.4.4
- **Custom Mappings**:
  - Cue buttons remapped to toggle Neural Mix for each deck
  - Smart Fader and Release FX buttons remapped to toggle FX1 for Deck 1 and Deck 2
  - Middle button remapped to Crossfader FX toggle
- Optimized for quick access to Neural Mix and FX1 controls

---

**Note**: This mapping is specifically designed for the DDJ-FLX4 controller. For other controllers, you may need to adjust MIDI channels and note assignments.

