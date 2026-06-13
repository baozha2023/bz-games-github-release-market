# bz-games GitHub Release 市场

为 [bz-games](https://github.com/baozha2023/bz-games) 游戏平台收录通过 GitHub Releases 分发的 Windows 游戏索引仓库。

本市场专注于收录已在 GitHub 上发布 Release 并打包好 `.zip` 游戏文件的 Windows 游戏。平台在下载时会通过 GitHub REST API
自动获取 Release Asset 的 `size`。`sha256` 是否可用取决于 GitHub 是否在上传时提供了 `digest`（仅 GitHub Actions 上传的
asset
会包含此字段），缺失 `sha256` 不影响正常下载使用，仅跳过完整性校验。

## 如何添加新游戏

1. Fork 本仓库
2. 在 `market.json` 的 `games` 数组中新增一个游戏条目
3. 填写关键字段：

   ```json
   {
     "id": "com.bztp.example",
     "name": "示例游戏",
     "type": "singleplayer",
     "latestVersion": "1.0.0",
     "versions": [
       {
         "version": "1.0.0",
         "platformVersion": ">=2.1.5",
         "downloadUrl": "https://github.com/{owner}/{repo}/releases/download/{tag}/{asset}.zip",
         "publishedAt": "2026-05-30T08:00:00.000Z",
         "gameManifest": {
           "entry": "游戏入口.exe",
           "type": "singleplayer"
         }
       }
     ]
   }
   ```

    - **`downloadUrl`**：必须为 GitHub Releases 直链（格式
      `https://github.com/{owner}/{repo}/releases/download/{tag}/{asset}`），平台自动获取 `size`，`sha256` 可选
    - **`gameManifest`**：由于 GitHub 上的游戏压缩包通常不含 `game.json`，需要通过此字段指定入口文件和其他清单信息
4. 提交 Pull Request

## market.json 格式说明

`market.json` 字段填写规范、`gameManifest` 配置说明及完整字段列表详见官方仓库 README：

> **[bz-games-market/README.md](https://github.com/baozha2023/bz-games-market/blob/master/README.md)**

## 版权说明

本仓库中所有游戏版权归原作者所有，本仓库仅提供下载索引和平台适配配置。

## 已有游戏（30 款）

### 射击 / 街机

| 游戏名称         | 版本       | 作者                | 仓库地址                                                                                |
|--------------|----------|-------------------|-------------------------------------------------------------------------------------|
| C-Dogs SDL   | 2.4.0    | Cong Xu           | [cxong/cdogs-sdl](https://github.com/cxong/cdogs-sdl)                               |
| OpenLieroX   | 0.58-rc5 | Albert Zeyer & contributors | [openlierox/openlierox](https://github.com/openlierox/openlierox)                   |
| OpenSpades   | 0.1.3    | yvt               | [yvt/openspades](https://github.com/yvt/openspades)                                 |
| SDL-Ball     | 1.04     | DusteDdk          | [DusteDdk/SDL-Ball](https://github.com/DusteDdk/SDL-Ball)                           |
| Taisei       | 1.4.4    | laochailan        | [laochailan/taisei](https://github.com/laochailan/taisei)                           |
| Teeworlds    | 0.7.5    | Teeworlds Team    | [teeworlds/teeworlds](https://github.com/teeworlds/teeworlds)                       |
| Unvanquished | 0.56.2   | Unvanquished Team | [Unvanquished/Unvanquished](https://github.com/Unvanquished/Unvanquished)           |
| Witch Blast  | 0.7.5    | Cirrus Minor      | [Cirrus-Minor/witchblast](https://github.com/Cirrus-Minor/witchblast)               |
| DungeonRush  | 1.1-beta | yujqiao           | [yujqiao/DungeonRush](https://github.com/yujqiao/DungeonRush)                       |

### Roguelike / RPG

| 游戏名称                       | 版本         | 作者           | 仓库地址                                                                                  |
|----------------------------|------------|--------------|---------------------------------------------------------------------------------------|
| Angband                    | 4.2.6      | Angband Team | [angband/angband](https://github.com/angband/angband)                                 |
| Cataclysm: Dark Days Ahead | 2026-05-30 | CleverRaven  | [CleverRaven/Cataclysm-DDA](https://github.com/CleverRaven/Cataclysm-DDA)             |
| Dungeon Crawl Stone Soup   | 0.34.1     | DCSS Team    | [crawl/crawl](https://github.com/crawl/crawl)                                         |
| Shattered Pixel Dungeon    | 3.3.8      | Evan         | [00-Evan/shattered-pixel-dungeon](https://github.com/00-Evan/shattered-pixel-dungeon) |
| Veloren                    | 2025.9.13  | Veloren Team | [veloren/veloren](https://github.com/veloren/veloren)                               |

### 赛车 / 竞速

| 游戏名称          | 版本    | 作者           | 仓库地址                                                              |
|---------------|-------|--------------|-------------------------------------------------------------------|
| Savage Wheels | 1.6.1 | Petar Petrov | [petarov/savagewheels](https://github.com/petarov/savagewheels)   |

### 沙盒 / 模拟

| 游戏名称              | 版本           | 作者                | 仓库地址                                                                  |
|-------------------|--------------|-------------------|-----------------------------------------------------------------------|
| A/B Street        | 0.3.49       | Dustin Carlino    | [a-b-street/abstreet](https://github.com/a-b-street/abstreet)         |
| Endless Sky       | 0.10.16      | Michael Zahniser  | [endless-sky/endless-sky](https://github.com/endless-sky/endless-sky) |
| Freeminer         | 0.4.14.8     | Freeminer Team    | [freeminer/freeminer](https://github.com/freeminer/freeminer)         |
| Luanti (Minetest) | 5.16.1       | Luanti Team       | [minetest/minetest](https://github.com/minetest/minetest)             |
| Thrive          | 1.1.0       | Revolutionary Games | [Revolutionary-Games/Thrive](https://github.com/Revolutionary-Games/Thrive) |
| Cubyz           | 0.2.0       | PixelGuys          | [PixelGuys/Cubyz](https://github.com/PixelGuys/Cubyz)                       |
| Cultivation World Simulator | 3.5.0 | 4thfever | [4thfever/cultivation-world-simulator](https://github.com/4thfever/cultivation-world-simulator) |
| Egregoria       | 0.6.2       | Uriopass           | [Uriopass/Egregoria](https://github.com/Uriopass/Egregoria)                       |

### 策略 / RTS

| 游戏名称            | 版本       | 作者                   | 仓库地址                                                                          |
|-----------------|----------|----------------------|-------------------------------------------------------------------------------|
| Harris          | 0.4.1    | ec429                | [ec429/harris](https://github.com/ec429/harris)                               |
| Unciv           | 4.20.10  | Yair Morgenstern     | [yairm210/Unciv](https://github.com/yairm210/Unciv)                           |
| Warzone 2100    | 4.7.0    | Warzone 2100 Project | [Warzone2100/warzone2100](https://github.com/Warzone2100/warzone2100)         |

### 平台 / 动作

| 游戏名称     | 版本    | 作者            | 仓库地址                                                              |
|----------|-------|---------------|-------------------------------------------------------------------|
| Minilens | 1.2   | KOBUGE Games  | [KOBUGE-Games/minilens](https://github.com/KOBUGE-Games/minilens) |
| SuperTux | 0.7.0 | SuperTux Team | [SuperTux/supertux](https://github.com/SuperTux/supertux)         |
| Turtle Arena | 0.7.0 | Turtle Arena Team | [Turtle-Arena/turtle-arena-code](https://github.com/Turtle-Arena/turtle-arena-code) |

### 解谜 / 棋牌

| 游戏名称    | 版本    | 作者           | 仓库地址                                                    |
|---------|-------|--------------|---------------------------------------------------------|
| Wizznic | 1.1   | DusteDdk     | [DusteDdk/Wizznic](https://github.com/DusteDdk/Wizznic) |
| Friday Night Funkin' | 0.8.4 | FunkinCrew | [FunkinCrew/Funkin](https://github.com/FunkinCrew/Funkin) |

---

## 推荐但暂无 GitHub Release Windows 版的游戏

以下游戏来自 [leereilly/games](https://github.com/leereilly/games) Native 分类，质量优秀、值得推荐，但目前没有在 GitHub
Releases 中发布 Windows 版本。如果原作者或社区能打包 Windows 版并发布 Release，即可加入本市场。

### 已有 Release 但无 Windows 版（打包即可加入）

| 游戏名称              | 最新版本         | 仓库地址                                                                      | 备注                              |
|-------------------|--------------|---------------------------------------------------------------------------|---------------------------------|
| Duckmarines       | v1.0c        | [SimonLarsen/duckmarines](https://github.com/SimonLarsen/duckmarines)     | ChuChu Rocket 复刻，需补充 Windows 构建 |
| Colobot           | 0.2.2-alpha  | [colobot/colobot](https://github.com/colobot/colobot)                     | 含编程要素的 RTS，有 Win 源码但未打包         |
| KeeperRL          | 1.0-hotfix19 | [miki151/keeperrl](https://github.com/miki151/keeperrl)                   | 矮人要塞风格地牢建造，需补充 Win 构建           |
| OpenDungeons      | 0.7.1        | [OpenDungeons/OpenDungeons](https://github.com/OpenDungeons/OpenDungeons) | 地下城守护者风，仅有源码 tar.xz             |
| Seven Kingdoms AA | 2.15.6       | [the3dfxdude/7kaa](https://github.com/the3dfxdude/7kaa)                   | 经典 RTS，需补充 Win 构建               |
| Blackvoxel        | 2.5          | [Blackvoxel/Blackvoxel](https://github.com/Blackvoxel/Blackvoxel)         | 体素沙盒，需补充 Win 构建                 |

### 高价值但无任何 Release

| 游戏名称                        | 仓库地址                                                                        | 类型        | 推荐理由                                         |
|-----------------------------|-----------------------------------------------------------------------------|-----------|----------------------------------------------|
| 0 A.D.                      | [0ad/0ad](https://github.com/0ad/0ad)                                       | RTS       | 顶级开源 RTS，类似帝国时代 II，有独立安装包但未用 GitHub Releases |
| The Battle for Wesnoth      | [wesnoth/wesnoth](https://github.com/wesnoth/wesnoth)                       | 策略        | 经典奇幻回合制策略，Steam 在售，需补充 GitHub Release        |
| Hedgewars                   | [hedgewars/hw](https://github.com/hedgewars/hw)                             | 策略        | 百战天虫风格，有独立发布渠道，未用 GitHub Releases            |
| Frogatto                    | [frogatto/frogatto](https://github.com/frogatto/frogatto)                   | 平台        | 精美像素动作冒险，有源代码但未打 Release 包                   |
| Gish                        | [blinry/gish](https://github.com/blinry/gish)                               | 平台        | 获奖物理平台游戏，源码开放但无 Release                      |
| The Legend of Edgar         | [riksweeney/edgar](https://github.com/riksweeney/edgar)                     | 平台        | 2D 平台冒险，有持续更新但无 GitHub Release               |
| Commander Genius            | [gerstrong/Commander-Genius](https://github.com/gerstrong/Commander-Genius) | 平台        | Commander Keen 兼容引擎                          |
| Secret Chronicles of Dr. M. | [Secretchronicles/TSC](https://github.com/Secretchronicles/TSC)             | 平台        | 经典 2D 平台，类似超级玛丽                              |
| Stendhal                    | [arianne/stendhal](https://github.com/arianne/stendhal)                     | MMORPG    | 免费 2D 多人在线冒险，有独立发布                           |
| Flare RPG                   | [clintbellanger/flare-game](https://github.com/clintbellanger/flare-game)   | RPG       | 开源 ARPG 引擎+游戏，有独立发布渠道                        |
| NetHack                     | [NetHack/NetHack](https://github.com/NetHack/NetHack)                       | Roguelike | 最经典的 Roguelike 之一，需补充 Win 构建                 |
| OpenMeridian                | [OpenMeridian/Meridian59](https://github.com/OpenMeridian/Meridian59)       | MMORPG    | 史上首款 3D MMORPG（1996），开源运营中                   |

> **提示**：如果你发现以上某款游戏已经发布了 Windows Release，欢迎提交 PR 添加到 `market.json` 中！
