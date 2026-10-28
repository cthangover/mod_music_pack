# Music Pack — a soundtrack for your game

**22 music tracks** for exploration, combat and the main menu. Reuse the soundtrack across cthangover games without copying the audio into every story mod.

![Three music contexts: exploration, combat and the main menu](assets/playlists.png)

## What players hear

- **Exploration:** 8 tracks for scenes without their own playlist, including RPG maps.
- **Combat:** 12 tracks in the `Battle` playlist. The fallback `default` combat playlist also includes `Empty Save Room`, for a total of 13.
- **Main menu:** `Serpent's Lament`.

> Music Pack provides audio and playlists. It does not add locations, quests or gameplay mechanics.

## Do I need to configure anything?

If your game already uses Music Pack, you do not need to install or select individual tracks. The `audio_base` system handles playback.

The pack is used by the main menu, Cthangover, the novel template and the project's RPG games. It does not require the main game's story content to load.

## Using it in your own game

1. Install `music_pack` and its dependency, `audio_base`.
2. Add `music_pack>=1` to the existing `depends` list in your content mod's `manifest.json`.
3. Use the supplied playlists, or add a JSON file under your mod's `music/playlists/` directory for a custom selection.

Dependency example:

```jsonc
// Add the dependency to your existing list:
"depends": ["music_pack>=1"]
```

Example location for a custom playlist:

```filestree
my_game/
├── manifest.json
└── music/
    └── playlists/
        └── my_scene.json  # Music for your scene
```

Example playlist for a scene named `my_scene`:

```json
{
  "Scene": "my_scene",
  "Musics": [
    {
      "MusicType": "Ambient",
      "MusicNames": ["Airborne Melody", "Twilight Interlude"]
    }
  ]
}
```

Use track names **without the `.ogg` extension**, preserving capitalization and spaces. Replace `my_scene` with your scene's name.

## Included playlists

- `default` — exploration (`Ambient`) and fallback combat music (`Combat`).
- `Battle` — combat music for both battle systems.
- `MainMenu` — the main menu theme.

The `town_entry` playlist remains in the story mod `cthangover_game` and is not part of this pack.

## All 22 tracks

### Exploration

Abyssal Void · Airborne Melody · Binary Prelude · Cinders of Dawn · Melancholic Journey · Nebula Pulse Echoes · Quantum Archive · Twilight Interlude.

### Combat and fallback combat

Aura of Decay · Circuit Dreams II · Crimson Echoes · Crimson Horizon · Empty Save Room · Glass Symphony · Hex Doom Cart · Iron Resonance · Iron Resonance II · Luminous Twilight · Rusty Frequencies · Skull Resonance · Venom's Embrace.

### Main menu

Serpent's Lament.

## Troubleshooting

- Check that `music_pack` and `audio_base` are installed and enabled.
- Check music volume in the game settings.
- If only one scene is affected, check its custom playlist and exact track names.
- A later dependent mod can replace the music selection for the same scene and music type.
