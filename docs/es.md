# Music Pack — una banda sonora para tu juego

**22 pistas de música** para exploración, combate y el menú principal. Reutiliza la banda sonora en los juegos de cthangover sin copiar el audio en cada mod de historia.

![Tres contextos musicales: exploración, combate y menú principal](assets/playlists.png)

## Lo que oye el jugador

- **Exploración:** 8 pistas para escenas sin playlist propia, incluidos los mapas RPG.
- **Combate:** 12 pistas en la playlist `Battle`. La playlist de reserva `default` también incluye `Empty Save Room`: 13 en total.
- **Menú principal:** `Serpent's Lament`.

> Music Pack aporta audio y playlists. No añade ubicaciones, misiones ni mecánicas de juego.

## ¿Hay que configurar algo?

Si tu juego ya usa Music Pack, no necesitas instalar ni seleccionar pistas individuales. La reproducción la lleva el sistema `audio_base`.

El paquete lo usan el menú principal, Cthangover, la plantilla de novela y los juegos RPG del proyecto. No necesita el contenido de la historia del juego principal para cargar.

## Cómo usarlo en tu juego

1. Instala `music_pack` y su dependencia, `audio_base`.
2. Añade `music_pack>=1` a la lista `depends` existente en el `manifest.json` de tu mod de contenido.
3. Usa las playlists incluidas, o añade un archivo JSON bajo el directorio `music/playlists/` de tu mod para una selección propia.

Ejemplo de dependencia:

```jsonc
// Añade la dependencia a tu lista existente:
"depends": ["music_pack>=1"]
```

Ubicación de ejemplo para una playlist propia:

```filestree
my_game/
├── manifest.json
└── music/
    └── playlists/
        └── my_scene.json  # Música para tu escena
```

Ejemplo de playlist para una escena llamada `my_scene`:

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

Usa los nombres de pista **sin la extensión `.ogg`**, respetando mayúsculas y espacios. Sustituye `my_scene` por el nombre de tu escena.

## Playlists incluidas

- `default` — exploración (`Ambient`) y música de combate de reserva (`Combat`).
- `Battle` — música de combate para ambos sistemas de batalla.
- `MainMenu` — el tema del menú principal.

La playlist `town_entry` sigue en el mod de historia `cthangover_game` y no forma parte de este paquete.

## Las 22 pistas

### Exploración

Abyssal Void · Airborne Melody · Binary Prelude · Cinders of Dawn · Melancholic Journey · Nebula Pulse Echoes · Quantum Archive · Twilight Interlude.

### Combate y reserva de combate

Aura of Decay · Circuit Dreams II · Crimson Echoes · Crimson Horizon · Empty Save Room · Glass Symphony · Hex Doom Cart · Iron Resonance · Iron Resonance II · Luminous Twilight · Rusty Frequencies · Skull Resonance · Venom's Embrace.

### Menú principal

Serpent's Lament.

## Si algo no suena

- Comprueba que `music_pack` y `audio_base` estén instalados y activados.
- Revisa el volumen de la música en los ajustes del juego.
- Si solo una escena está afectada, revisa su playlist propia y los nombres exactos de las pistas.
- Un mod dependiente cargado después puede sustituir la selección musical para la misma escena y el mismo tipo de música.
