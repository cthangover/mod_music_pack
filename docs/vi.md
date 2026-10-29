# Music Pack — nhạc nền cho game của bạn

**22 bản nhạc** cho khám phá, chiến đấu và menu chính. Dùng chung bản nhạc nền giữa các game cthangover mà không cần chép âm thanh vào từng mod cốt truyện.

![Ba bối cảnh âm nhạc: khám phá, chiến đấu và menu chính](assets/playlists.png)

## Người chơi nghe thấy gì

- **Khám phá:** 8 bản nhạc cho các cảnh không có danh sách phát riêng, kể cả bản đồ RPG.
- **Chiến đấu:** 12 bản nhạc trong danh sách phát `Battle`. Danh sách dự phòng `default` cũng có `Empty Save Room`, tổng cộng 13 bản.
- **Menu chính:** `Serpent's Lament`.

> Music Pack cung cấp âm thanh và danh sách phát. Nó không thêm địa điểm, nhiệm vụ hay cơ chế chơi.

## Có cần cấu hình gì không

Nếu game của bạn đã dùng Music Pack, bạn không cần cài hay chọn từng bản nhạc. Việc phát do hệ thống `audio_base` đảm nhiệm.

Gói này được menu chính, Cthangover, mẫu tiểu thuyết và các game RPG của dự án dùng. Nó không cần nội dung cốt truyện của game chính mới chạy được.

## Dùng trong game của bạn

1. Cài `music_pack` và phần phụ thuộc của nó, `audio_base`.
2. Thêm `music_pack>=1` vào danh sách `depends` sẵn có trong `manifest.json` của mod nội dung.
3. Dùng các danh sách phát có sẵn, hoặc thêm một tệp JSON trong thư mục `music/playlists/` của mod nếu muốn tự chọn nhạc.

Ví dụ về phụ thuộc:

```jsonc
// Thêm phụ thuộc vào danh sách có sẵn:
"depends": ["music_pack>=1"]
```

Vị trí ví dụ cho một danh sách phát riêng:

```filestree
my_game/
├── manifest.json
└── music/
    └── playlists/
        └── my_scene.json  # Nhạc cho cảnh của bạn
```

Ví dụ danh sách phát cho cảnh tên `my_scene`:

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

Tên bản nhạc viết **không có đuôi `.ogg`**, giữ nguyên chữ hoa chữ thường và khoảng trắng. Thay `my_scene` bằng tên cảnh của bạn.

## Các danh sách phát có sẵn

- `default` — nhạc khám phá (`Ambient`) và nhạc chiến đấu dự phòng (`Combat`).
- `Battle` — nhạc chiến đấu cho cả hai hệ thống chiến đấu.
- `MainMenu` — giai điệu menu chính.

Danh sách phát `town_entry` vẫn nằm trong mod cốt truyện `cthangover_game` và không thuộc gói này.

## Cả 22 bản nhạc

### Khám phá

Abyssal Void · Airborne Melody · Binary Prelude · Cinders of Dawn · Melancholic Journey · Nebula Pulse Echoes · Quantum Archive · Twilight Interlude.

### Chiến đấu và danh sách dự phòng

Aura of Decay · Circuit Dreams II · Crimson Echoes · Crimson Horizon · Empty Save Room · Glass Symphony · Hex Doom Cart · Iron Resonance · Iron Resonance II · Luminous Twilight · Rusty Frequencies · Skull Resonance · Venom's Embrace.

### Menu chính

Serpent's Lament.

## Khi nhạc không phát

- Kiểm tra `music_pack` và `audio_base` đã được cài và bật.
- Kiểm tra âm lượng nhạc trong phần cài đặt của game.
- Nếu chỉ một cảnh bị ảnh hưởng, kiểm tra danh sách phát riêng của cảnh đó và tên chính xác của từng bản nhạc.
- Một mod phụ thuộc nạp sau có thể thay việc chọn nhạc cho cùng cảnh và cùng loại nhạc.
