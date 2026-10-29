# Music Pack — 게임을 위한 사운드트랙

탐험, 전투, 메인 메뉴를 위한 **22곡**. 오디오를 스토리 모드마다 복사하지 않고도 cthangover의 여러 게임이 사운드트랙을 함께 씁니다.

![세 가지 음악 상황: 탐험, 전투, 메인 메뉴](assets/playlists.png)

## 플레이어가 듣는 것

- **탐험:** 자체 재생 목록이 없는 장면을 위한 8곡. RPG 맵도 포함됩니다.
- **전투:** `Battle` 재생 목록의 12곡. 예비 전투 목록 `default`에는 `Empty Save Room`도 있어 총 13곡입니다.
- **메인 메뉴:** `Serpent's Lament`.

> Music Pack은 오디오와 재생 목록을 제공합니다. 장소, 퀘스트, 게임 메커니즘은 추가하지 않습니다.

## 설정이 필요한가

게임이 이미 Music Pack을 쓰고 있다면 곡을 따로 설치하거나 고를 필요가 없습니다. 재생은 `audio_base` 시스템이 맡습니다.

이 팩은 메인 메뉴, Cthangover, 노벨 템플릿, 프로젝트의 RPG 게임이 사용합니다. 메인 게임의 스토리 콘텐츠 없이도 로드됩니다.

## 내 게임에서 쓰기

1. `music_pack`과 그 의존성인 `audio_base`를 설치합니다.
2. 콘텐츠 모드의 `manifest.json`에 있는 기존 `depends` 목록에 `music_pack>=1`을 추가합니다.
3. 제공되는 재생 목록을 쓰거나, 직접 고른 곡을 쓰려면 자신의 모드의 `music/playlists/` 디렉터리에 JSON 파일을 추가합니다.

의존성 예:

```jsonc
// 기존 목록에 의존성을 추가합니다:
"depends": ["music_pack>=1"]
```

자작 재생 목록의 위치 예:

```filestree
my_game/
├── manifest.json
└── music/
    └── playlists/
        └── my_scene.json  # 내 장면의 음악
```

`my_scene` 장면용 재생 목록 예:

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

곡 이름은 **`.ogg` 확장자 없이**, 대소문자와 공백을 그대로 지켜 씁니다. `my_scene`은 자신의 장면 이름으로 바꾸세요.

## 포함된 재생 목록

- `default` — 탐험 음악(`Ambient`)과 예비 전투 음악(`Combat`).
- `Battle` — 두 전투 시스템 모두를 위한 전투 음악.
- `MainMenu` — 메인 메뉴 테마.

재생 목록 `town_entry`는 스토리 모드 `cthangover_game`에 남아 있으며 이 팩에 포함되지 않습니다.

## 전체 22곡

### 탐험

Abyssal Void · Airborne Melody · Binary Prelude · Cinders of Dawn · Melancholic Journey · Nebula Pulse Echoes · Quantum Archive · Twilight Interlude.

### 전투와 예비 전투 목록

Aura of Decay · Circuit Dreams II · Crimson Echoes · Crimson Horizon · Empty Save Room · Glass Symphony · Hex Doom Cart · Iron Resonance · Iron Resonance II · Luminous Twilight · Rusty Frequencies · Skull Resonance · Venom's Embrace.

### 메인 메뉴

Serpent's Lament.

## 음악이 나오지 않을 때

- `music_pack`과 `audio_base`가 설치되어 있고 켜져 있는지 확인하세요.
- 게임 설정에서 음악 볼륨을 확인하세요.
- 한 장면만 문제라면 그 장면의 자체 재생 목록과 곡 이름의 정확한 철자를 확인하세요.
- 나중에 로드된 의존 모드는 같은 장면과 같은 음악 유형에 대해 곡 선택을 바꿀 수 있습니다.
