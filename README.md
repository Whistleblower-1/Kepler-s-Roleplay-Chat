# Roleplay Chat Mod - Build 42.13+ Update

A roleplay-focused chat mod for Project Zomboid Build 42.13+. This mod adds RP-focused chat commands with range-based messaging, language systems, and character customization.

**Original mod by:** buffy (github.com/buffyuwu/PZ-roleplaychat)

## Features

### Chat Commands
- `/me` - Emote action (e.g., "/me waves hello")
- `/melong` - Long-range emote (50 tile radius)
- `/melow` - Low-volume emote (4 tile radius)
- `/do` - Environment description
- `/dolong` - Long-range environment description
- `/dolow` - Low-volume environment description
- `/name` or `/act` - Change your displayed RP name
- `/low` - Low-volume speaking
- `/whisper` or `/w` - Whisper range (2 tiles)
- `/whisperme` or `/wme` - Whispered emote
- `/looc` or `/l` - Local OOC chat
- `/say` or `/s` - Normal speech
- `/yell` or `/shout` - Shout at long range

### Language System
Players can learn additional languages via "Buffetta Stone" books:
- Spanish, Russian, Ukrainian, German, French, Mandarin, Japanese, ASL

Messages in languages you don't know will appear scrambled with occasional words visible.

### Character Customization
Access via the chat gear icon:
- Clean blood and dirt
- Set hair color
- Toggle ASL animations
- Set custom emote colors
- Set custom name colors

### Range-Based Chat
Messages are only visible within certain tile ranges:
- Say: Configurable (default 16 tiles)
- Me/Emote: Configurable (default 20 tiles)
- Long-range: Configurable (default 48 tiles)
- Low: Configurable (default 4 tiles)
- Whisper: Configurable (default 2 tiles)
- Shout: Configurable (default 48 tiles)

## Installation

1. Copy the `roleplaychat` folder to your Project Zomboid mods directory:
   - Windows: `C:\Users\[Username]\Zomboid\mods\`
   - Linux: `~/.local/share/Zomboid/mods/`
   - Mac: `~/Library/Application Support/Zomboid/mods/`

2. Enable the mod in Project Zomboid's mod menu

## Server Configuration

Sandbox options can be configured in server settings:
- Toggle Global OOC (`/all`, `//`)
- Toggle Local OOC (`/looc`)
- Toggle name changing (`/name`)
- Enable/disable character customization
- Enable anti-starve QoL buff for emotes
- Enable "Over Radio" messages in chat
- Configure range values for each chat type

## Build 42.13 Compatibility

This update implements the new registry system introduced in Build 42.13:

### New File Structure
```
roleplaychat/
├── media/
│   ├── registries.lua          <- NEW: Required for 42.13+
│   ├── lua/
│   │   ├── client/
│   │   │   ├── Chat/ISChat.lua
│   │   │   ├── Context/Inventory/InvContextLanguageBooks.lua
│   │   │   └── ISUI/AdminPanel/ISMiniScoreboardUI.lua
│   │   └── shared/
│   │       └── Translate/EN/
│   ├── scripts/
│   │   └── LanguageBookitems.txt
│   └── sandbox-options.txt
├── mod.info
└── README.md
```

### Key Changes for 42.13
- **registries.lua**: Registers custom item types using the new `namespace:path` format
- **Module namespace**: Changed from `Language` to `roleplaychat` to match mod ID
- **Item identifiers**: Now use `roleplaychat:ItemName` format
- **Safe SandboxVars access**: Uses `~= nil` check to properly handle false/zero values

### Migration Notes
- Saves from before 42.13 are NOT compatible with 42.13+
- The mod now uses the `roleplaychat` namespace for all custom items
- Language books are now registered as `roleplaychat:SpanishBook`, etc.

## Credits

- Original mod: buffy
- B42.13 Update: Based on the original codebase

## License

See original repository for license information.
