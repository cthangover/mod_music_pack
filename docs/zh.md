# Music Pack — 为你的游戏配乐

**22 首曲目**，覆盖探索、战斗和主菜单。在 cthangover 的各个游戏之间共用这套配乐，无需把音频复制进每个剧情模组。

![三种音乐情境：探索、战斗和主菜单](assets/playlists.png)

## 玩家会听到什么

- **探索：** 8 首曲目，供没有专属播放列表的场景使用，包括 RPG 地图。
- **战斗：** `Battle` 播放列表中的 12 首曲目。备用战斗列表 `default` 还包含 `Empty Save Room`，合计 13 首。
- **主菜单：** `Serpent's Lament`。

> Music Pack 提供音频和播放列表，不添加地点、任务或玩法机制。

## 需要配置什么吗

如果你的游戏已经在用 Music Pack，就无需单独安装或挑选曲目。播放由 `audio_base` 系统负责。

主菜单、Cthangover、小说模板和项目的 RPG 游戏都在使用这个素材包。加载它不需要主游戏的剧情内容。

## 在自己的游戏中使用

1. 安装 `music_pack` 及其依赖 `audio_base`。
2. 在内容模组 `manifest.json` 已有的 `depends` 列表中加入 `music_pack>=1`。
3. 直接使用自带的播放列表，或者想自定义选曲时，在你模组的 `music/playlists/` 目录下添加一个 JSON 文件。

依赖示例：

```jsonc
// 把依赖加入已有的列表：
"depends": ["music_pack>=1"]
```

自定义播放列表的存放位置示例：

```filestree
my_game/
├── manifest.json
└── music/
    └── playlists/
        └── my_scene.json  # 你的场景的音乐
```

场景 `my_scene` 的播放列表示例：

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

曲目名**不带 `.ogg` 扩展名**，大小写和空格都要保持原样。把 `my_scene` 换成你的场景名。

## 自带的播放列表

- `default` — 探索音乐（`Ambient`）和备用战斗音乐（`Combat`）。
- `Battle` — 两套战斗系统共用的战斗音乐。
- `MainMenu` — 主菜单主题曲。

播放列表 `town_entry` 仍属于剧情模组 `cthangover_game`，不在本素材包内。

## 全部 22 首曲目

### 探索

Abyssal Void · Airborne Melody · Binary Prelude · Cinders of Dawn · Melancholic Journey · Nebula Pulse Echoes · Quantum Archive · Twilight Interlude.

### 战斗与备用战斗列表

Aura of Decay · Circuit Dreams II · Crimson Echoes · Crimson Horizon · Empty Save Room · Glass Symphony · Hex Doom Cart · Iron Resonance · Iron Resonance II · Luminous Twilight · Rusty Frequencies · Skull Resonance · Venom's Embrace.

### 主菜单

Serpent's Lament.

## 音乐不播放时

- 检查 `music_pack` 和 `audio_base` 是否已安装并启用。
- 检查游戏设置中的音乐音量。
- 如果只有某个场景有问题，检查它自己的播放列表和确切的曲目名。
- 后加载的依赖模组可以覆盖同一场景、同一音乐类型的选曲。
