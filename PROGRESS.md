# 준호의 로손 토미카 3D 주차장 (Antigravity 연계 가이드)

## 1. 폴더 구조
- `index.html`: Three.js 기반 로손 편의점 3D 주차·출차 및 살펴보기 게임 메인 파일
- `models/byd_sealion_7_ultra_2026.glb`: BYD 씨라이언 7 (1번 칸)
- `models/2024_hyundai_elantra_n.glb`: 현대 아반떼 N (2번 칸)
- `models/2022_lamborghini_countach_lpi_800-4.glb`: 람보르기니 쿤타치 (3번 칸)
- `models/2024_byd_seal.glb`: BYD 씰 (4번 칸)
- `models/porsche_911_gt3.glb`: 포르쉐 911 GT3 (5번 칸)
- `models/2013_audi_rs4_avant.glb`: 아우디 RS4 아반트 (6번 칸)
- `models/2024_hyundai_ioniq_5_n.glb`: 현대 아이오닉 5 N (7번 칸)
- `models/2021_volkswagen_id.4_x.glb`: 폭스바겐 ID.4 X (8번 칸)
- `models/2015_mercedes-benz_g-class_g_63_amg.glb`: 벤츠 G63 AMG (9번 칸)
- `models/2021_bmw_m4_g82_zacoe_carbon_fiber_body_kit.glb`: BMW M4 G82 (10번 칸)

## 2. 로컬 실행 방법 (Antigravity 터미널)
`fetch('./models/...')`가 동작하려면 파일 직접 열기(`file://`) 대신 로컬 웹 서버로 실행해야 합니다.
```bash
python3 -m http.server 8080
```
브라우저에서 `http://localhost:8080` 접속 시 `BYD 씨라이언 7`이 6번 주차 칸에 자동 로드됩니다.

## 3. 추후 작업 및 개선 포인트
1. **새 `.glb` 자동차 추가:** `models/` 폴더에 `.glb` 파일을 넣고 `index.html` 상단의 `PRELOADED_GLB_CARS` 배열에 한 줄씩 추가하세요.
2. **문·트렁크 깔끔히 분리하기 (Blender):**
   - 현재 `byd_sealion_7_ultra_2026.glb`는 외판이 통짜 메쉬라 코드에서 좌표 기준으로 분할하고 있습니다.
   - Blender에서 해당 `.glb`를 열어 문·트렁크·프렁크·선쉐이드를 메쉬로 분리(`Separate -> Selection`)하고 피벗(Origin)을 경첩 위치로 맞춘 뒤 저장하면 경계선 깨짐 없이 완벽하게 열립니다.
3. **실제 사진 기반 로손 편의점/토미카 정교화:** Antigravity에서 메쉬 디테일 및 모바일 터치 UI를 추가 다듬어 Synology NAS(`lastgenius.app`)에 정적 웹으로 배포하세요.
