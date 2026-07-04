# BLOCKSHOT — Tactical Voxel Sniper

A touch-first voxel sniper game built on Three.js. **Single HTML file**, zero external assets — every texture, sound effect and music track is procedurally generated in code. 100% original assets.

**English by default · 한국어 지원** (language toggle on the title screen and in Settings).

## Play

**▶ https://sjidok750-creator.github.io/Snipergame/**

Or open `index.html` in a browser. (Internet required for the Three.js CDN and fonts.)

- Designed for mobile (touch-only controls); works with a mouse on desktop too
- Auto-deployed to GitHub Pages by `.github/workflows/pages.yml` on every push

## Controls

| Input | Action |
|---|---|
| Drag left half | Aim view |
| FIRE (bottom right) | Shoot → bolt action |
| AIM (mid right) | Scope toggle · two-finger pinch = 2x–8x zoom |
| HOLD BREATH (bottom left) | −90% sway (4s gauge, penalty when drained) |

## Content

- **Mission 0 tutorial** (forced on first run) → **5 chapters · 14 mission types** → **Endless mode**
- Projectile ballistics (250 m/s + gravity), wind from chapter 3, night ops in chapter 4, Steel Colossus boss in chapter 5
- Fully destructible blocks with support-loss chain collapse (cut the watchtower mast to drop the whole structure)
- 5 enemy AI types: grunt / sniper / officer / heavy (helmet deflect) / runner (zigzag) — all rendered as **Minecraft-proportioned characters** (pixel faces, hair, faction uniforms, per-soldier variation)
- Wildlife: boar / hen / deer — wander, graze, flee from gunfire
- Gold economy + 8 armory upgrades, 1–3 stars per mission, service record & rank
- Mission briefing overlay with radio chatter, damage direction indicator, kill cam slow-mo
- Settings: sensitivity · aim assist · vibration · volumes · left-handed mode · 30fps battery saver · language (EN/KO)

## UI design

Military-shooter tactical look: gunmetal + amber palette, chamfered panels, Black Han Sans / Noto Sans KR / Rajdhani typography, and a live battlefield drifting behind every menu. One design language across menus, HUD and results.

## Tech notes

- All 16×16 canvas pixel-art textures use `NearestFilter` with mipmaps off
- 8×8 chunk `InstancedMesh` terrain; destruction sets instance scale 0 + dirty-flag batch update
- 100% Web Audio synthesized sound (3-layer gunshot, per-material impacts, distance attenuation/panning, dynamic music with 4s crossfades)
- Multi-touch tracked per `pointerId` — firing never disturbs the aim drag
- iOS vibration fallback (visual feedback), safe-area/notch aware, auto-pause on `visibilitychange`
- No `localStorage` — progress lives in session variables

---

### 한국어 요약

Three.js 기반 복셀 스나이퍼 게임. 단일 HTML 파일, 외부 에셋 0개(텍스처·사운드·음악 전부 절차 생성). 기본 영어 UI이며 타이틀 화면 우상단 버튼 또는 설정에서 한국어로 전환할 수 있습니다. 튜토리얼 → 5개 챕터 · 미션 14종 → 무한 모드, 블록 파괴/연쇄 붕괴, 적 AI 5종(마인크래프트 비율 캐릭터), 야생 동물, 상점 업그레이드 8종을 포함합니다.
