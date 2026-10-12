# 🎨 Draw to 3D | Draw to 3D

> 마우스 드로잉·이미지를 3D 릴리프 모델로 변환 — STL/OBJ/GLB 다운로드 + OctoPrint 전송
> Turn drawings and images into 3D relief models — download STL/OBJ/GLB, send to OctoPrint

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen?style=flat-square)](https://metasongi.github.io/draw-to-3d/) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square) ![Three.js](https://img.shields.io/badge/Three.js-000000?style=flat-square)

🌐 **Live:** https://metasongi.github.io/draw-to-3d/

---

마우스로 그린 그림이나 업로드한 이미지를 3D 릴리프 모델로 변환하는 웹 도구입니다.
**STL / OBJ / GLB**로 다운로드하고, OctoPrint가 설치된 3D 프린터로 바로 전송할 수 있습니다.

## 🚀 실행

`index.html`을 브라우저에서 열거나 GitHub Pages로 배포하면 바로 사용 가능합니다.
(Three.js는 CDN importmap으로 불러오므로 온라인 환경이 필요합니다)

## 🖌 사용법

1. **그리기 / 이미지 업로드** — 캔버스에 직접 그리거나 PNG/JPG를 업로드. 밝은 부분이 3D에서 높게 솟아오릅니다. (브러시 크기·밝기 조절, 지우개, 실행 취소 20단계, 샘플 그림 제공)
2. **3D 변환 설정** — 높이(2~50mm), 베이스 두께(0~10mm), 밝기 반전, 스무딩, 메시 해상도(64/128/192) 조절 후 "3D 생성"
3. **3D 미리보기** — 마우스로 회전/줌/이동, 자동 회전·와이어프레임 토글
4. **다운로드** — STL / OBJ / GLB 버튼 클릭
5. **프린터로 전송 (선택)** — OctoPrint URL + API 키 입력 → 연결 테스트 → STL 전송

## 🖨 3D 프린터 안내

- 프린터가 없어도 됩니다. STL을 다운로드해 **Cura / Bambu Studio / OrcaSlicer** 등 슬라이서에서 사용하세요.
- OctoPrint 전송은 프린터와 같은 네트워크에서 사용하세요.
- ⚠ GitHub Pages(HTTPS)에서는 `http://` 프린터 주소가 브라우저 보안 정책에 차단될 수 있습니다. 프린터 전송 시에는 이 파일을 직접 열어(`http://` 또는 `file://`) 사용하세요.

## 📦 FBX 안내

브라우저에서는 FBX를 직접 내보낼 수 없습니다. FBX가 필요하면 **GLB를 Blender에 가져온 뒤
`파일 → 내보내기 → FBX`** 로 변환하세요.

## ⚙ 기술 메모

- 높이맵 → (res+1)² 정점 그리드 + 옆면(skirt) + 바닥면으로 닫힌 솔리드 생성 (슬라이서 호환)
- 출력 크기: 가로 100mm 고정, 단위 mm
- STL은 바이너리 규격(84바이트 헤더 + facet당 50바이트)으로 직접 인코딩

---

## English Summary

Turn mouse drawings and uploaded images into 3D relief models. Download as STL/OBJ/GLB and optionally send to an OctoPrint-connected 3D printer.
