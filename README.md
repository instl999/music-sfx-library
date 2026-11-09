# 音乐音效库 · Music & SFX Library

面向 AI 与短视频剪辑流程的 BGM + 音效素材库。所有音频统一转码为 **MP3 192 kbps**（原始 WAV 母版保留在本地，不入库），便于直接检索、试听与下载。

- 配乐 BGM：**26** 首
- 音效 SFX：**2227** 个，分 **12** 个音效包
- 机器可读清单：`manifest.csv`（`pack,name,path,format,duration_sec,size_bytes`）

## 目录结构

```
bgm/                       配乐，文件名即标签：<情绪/用途> - <曲名> - <作者>.mp3
sfx/<音效包>/              音效，按类型分包
manifest.csv               全量清单（含时长/大小）
```

## 给 AI 的检索指引

1. 先读 `manifest.csv`，按 `pack`（类型）和 `name`（关键词）过滤，再用 `duration_sec` 判断是否适合当前镜头长度。
2. BGM 的 `name` 前缀就是情绪/用途标签，可直接按前缀匹配：

   `Aftermath` · `Anxiety` · `Calm` · `Crisis` · `Doubt` · `Doubt Explanation` · `Ending Elevation` · `Ending Joy` · `Explanation` · `Opening Loss` · `Opening Tension` · `Propose Solution` · `Solution` · `Strong Rhythm Calm` · `Tension` · `Tension Crisis` · `Turning Point`

3. 音效按包的用途选：转场用 `Transition Whoosh`，紧张爬升用 `Risers`，落点重击用 `Hits`，故障感用 `Signal Interference Glitch SFX`。
4. 常用命令：

```bash
git ls-files | grep -i whoosh            # 按关键词找文件
grep -i 'tension' manifest.csv           # 按情绪标签找 BGM
cut -d, -f1 manifest.csv | sort | uniq -c # 统计各音效包数量
```

## BGM 速查表

| 情绪/用途 | 曲目 | 文件 | 时长 |
|---|---|---|---|
| Aftermath | Rescue Mission - Lupus Nocte | `bgm/Aftermath - Rescue Mission - Lupus Nocte.mp3` | 3:04 |
| Anxiety | Aware - Adrián Berenguer | `bgm/Anxiety - Aware - Adrián Berenguer.mp3` | 3:15 |
| Anxiety | Riddles - Fable Forte | `bgm/Anxiety - Riddles - Fable Forte.mp3` | 2:01 |
| Calm | Keep on the Sunny Side - Iwasaki Taisei | `bgm/Calm - Keep on the Sunny Side - Iwasaki Taisei.mp3` | 2:10 |
| Crisis | Now We Fight - Bonnie Grace | `bgm/Crisis - Now We Fight - Bonnie Grace.mp3` | 1:51 |
| Crisis | Tempt Scandal - Audiomachine | `bgm/Crisis - Tempt Scandal - Audiomachine.mp3` | 2:12 |
| Doubt | Bon Voyage - Jo Blankenburg | `bgm/Doubt - Bon Voyage - Jo Blankenburg.mp3` | 2:50 |
| Doubt | Holding Court - Audiomachine | `bgm/Doubt - Holding Court - Audiomachine.mp3` | 2:04 |
| Doubt Explanation | Yumeji's Theme - Umebayashi Shigeru | `bgm/Doubt Explanation - Yumeji's Theme - Umebayashi Shigeru.mp3` | 2:29 |
| Ending Elevation | Bulls - Mary Riddle | `bgm/Ending Elevation - Bulls - Mary Riddle.mp3` | 2:14 |
| Ending Elevation | Unbound Spirit - Duke Herrington | `bgm/Ending Elevation - Unbound Spirit - Duke Herrington.mp3` | 2:31 |
| Ending Joy | Shake Down - Jules Gaia | `bgm/Ending Joy - Shake Down - Jules Gaia.mp3` | 2:34 |
| Explanation | Secret Room - Soundroll | `bgm/Explanation - Secret Room - Soundroll.mp3` | 1:26 |
| Opening Loss | IV - AK,Mapps | `bgm/Opening Loss - IV - AK,Mapps.mp3` | 3:25 |
| Opening Loss | Jazzguitar Lucky - Xinxinjun | `bgm/Opening Loss - Jazzguitar Lucky - Xinxinjun.mp3` | 1:05 |
| Opening Tension | Dans la maison (Thème) - Philippe Rombi | `bgm/Opening Tension - Dans la maison (Thème) - Philippe Rombi.mp3` | 2:29 |
| Propose Solution | Closest to Home - Toby Tranter | `bgm/Propose Solution - Closest to Home - Toby Tranter.mp3` | 2:52 |
| Solution | Melody (Original mix) - A s h | `bgm/Solution - Melody (Original mix) - A s h.mp3` | 3:48 |
| Strong Rhythm Calm | Match My Vibe - Damma Beatz | `bgm/Strong Rhythm Calm - Match My Vibe - Damma Beatz.mp3` | 2:30 |
| Tension | counting the days - cody high | `bgm/Tension - counting the days - cody high.mp3` | 1:34 |
| Tension | Kill Drill - Robert Ruth | `bgm/Tension - Kill Drill - Robert Ruth.mp3` | 2:15 |
| Tension | preeminence - audiomachine | `bgm/Tension - preeminence - audiomachine.mp3` | 2:42 |
| Tension | Weapons of Impact - Bonnie Grace | `bgm/Tension - Weapons of Impact - Bonnie Grace.mp3` | 1:48 |
| Tension | Will of the People - Audiomachine | `bgm/Tension - Will of the People - Audiomachine.mp3` | 2:10 |
| Tension Crisis | Dismantle - Peter Sandberg | `bgm/Tension Crisis - Dismantle - Peter Sandberg.mp3` | 1:56 |
| Turning Point | The Grinch - Cushy | `bgm/Turning Point - The Grinch - Cushy.mp3` | 2:36 |

## 音效包

| 音效包 | 文件数 | 用途 | 路径 |
|---|---|---|---|
| Ambient SFX | 564 | 环境音与生活音效：街道/人群/动物/天气/室内氛围/婴儿啼哭等。 | `sfx/Ambient SFX/` |
| Atmosphere SFX | 373 | 氛围铺底音效：直升机、心跳、风声、空间感、低频铺底。 | `sfx/Atmosphere SFX/` |
| Fast and Slow | 4 | 变速类音效：加速/减速/快慢转换。 | `sfx/Fast and Slow/` |
| Food SFX | 65 | 食物音效：烧烤、沸腾、煎炸、咀嚼、倒水。 | `sfx/Food SFX/` |
| Hits | 195 | 打击/重击：预告片 hit、定音鼓式重击、冲击落点。 | `sfx/Hits/` |
| Momentum TVC SFX Library | 50 | 广告片(TVC)节奏音效：trailer hit、code black、段末收束音。 | `sfx/Momentum TVC SFX Library/` |
| Risers | 288 | 上升音效 riser：紧张递进、情绪拉升、段落转折前铺垫。 | `sfx/Risers/` |
| Signal Interference Glitch SFX | 185 | 故障/信号干扰 glitch：数码失真、卡顿、断电、数据传输。 | `sfx/Signal Interference Glitch SFX/` |
| Special Effects SFX | 16 | 特殊音效与片头引入（ambient intro 等）。 | `sfx/Special Effects SFX/` |
| Transition Whoosh | 387 | 转场 whoosh / 划过声 / 空气流动转场，适合镜头切换。 | `sfx/Transition Whoosh/` |
| Variety Show SFX | 50 | 综艺音效：鼓掌、欢呼、笑声、罐头掌声。 | `sfx/Variety Show SFX/` |
| Vintage Film SFX Pack | 50 | 复古胶片音效：相机快门、开关、机械按键、胶片质感。 | `sfx/Vintage Film SFX Pack/` |

各包示例（完整列表见对应目录或 `manifest.csv`）：

- **Ambient SFX**（564）：0764-Baby Cry (wav)、0764-Baby Cry、11000 Game Common SFX-Shy 1、13535、19000 SFX Library-Move Magnetic Levitation Bearing City Traffic Loop-Ambience、3624、502339、5979fb42e8d72 …
- **Atmosphere SFX**（373）：01 Above the Earth、01 Bright Winds、01 Chopper A、01 Heartbeat A、01 Pin Points、01 Rumble Swell、01 Sail Away、02 Chopper B …
- **Fast and Slow**（4）：Speed Change 1、Speed Change 2、Speed Change 3-Slow、Speed Change 4 …
- **Food SFX**（65）：BBQ-Flame Grill Food、Boiling Bubbling、Brushing Teeth、Burning Leaves、Burning Wood 01、Burning Wood 02、Champagne、Chewing Bone …
- **Hits**（195）：01 Moment of Truth、01 The Arrival、01. Future World Music-Hit 1、02 Bold Hit、02 Trailer Hit A、03 Trailer Hit B、03 Whoosh Hit、03. Future World Music-Hit 3 …
- **Momentum TVC SFX Library**（50）：01 Code Black A、02 Trailer Hit A、1219、122、149 full eternal-damnation 0166 preview、46 Slow Flap、8. Transition SFX-Surround、BGM Sound Wave 01(1) …
- **Risers**（288）：01 Dark Riser A、01 Epic Riser、01 New World、02 Close Riser、02 Dark Riser B、02 Dream、02. Future World Music-Hit 2、03 Escalate …
- **Signal Interference Glitch SFX**（185）：01 Code Black A、02 Code Black B、03 Code Black C、04 Fat Glitch、05 Chatter Gate、06 Flutter Glitch、07 Erase、08 Dark Order A …
- **Special Effects SFX**（16）：Ambient Intro 1、Ambient Intro 2、Ambient Intro 3、Ambient Intro 4、Bell、Fluid SFX 1、Fluid SFX 2、Katana …
- **Transition Whoosh**（387）：01 Air Dock、01 Deep Whoosh A、01 Simple Whoosh A、02 Deep Whoosh B、02 Simple Whoosh B、02 Velocity Whoosh、03 Exhale Long、03 Simple Whoosh C …
- **Variety Show SFX**（50）：1、2、Applause Cheer 2010-10-01（18 Second）、Applause-02、Applause-1、Applause-2、Applause-Cheer、Applause …
- **Vintage Film SFX Pack**（50）：Camera Shutter 1、Camera Shutter 2、Camera Shutter 3、Film Reel-1、Film Reel-2、Film Reel-3、Film Reel-4、Film Reel-5 …

## 说明

- SFX 与 BGM 文件名保持一致，仅把所有 `.wav` 转码为同名 `.mp3`；若同名冲突则加 ` (wav)` 后缀。
- 未入库：`Momentum TVC SFX Library/Honda-6(music2)-3.m4v`（视频文件，127 MB，超 GitHub 单文件限制）。
- 素材版权归原作者所有，仅限本项目内部使用。
