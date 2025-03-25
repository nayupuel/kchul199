# MCP (Message Communication Protocol) Project

## 프로젝트 소개
이 저장소는 Cursor IDE의 설정을 관리하기 위한 MCP(Message Communication Protocol) 구현체입니다.
MCP를 통해 Cursor의 다양한 설정을 효율적으로 관리할 수 있습니다.

## 구현된 기능
1. Cursor 설정 관리
   - 테마 설정 (theme)
   - 폰트 크기 설정 (font_size)
   - 탭 크기 설정 (tab_size)
   - 자동 저장 설정 (auto_save)

## API 명세
### 엔드포인트
1. 모든 설정 조회
   - 경로: GET /cursor/settings
   - 응답: 현재 설정된 모든 값 반환

2. 설정 업데이트
   - 경로: POST /cursor/settings
   - 요청 본문: JSON 형식의 설정 값
   - 응답: 업데이트된 설정 값

3. 특정 설정 조회
   - 경로: GET /cursor/settings/{key}
   - 응답: 요청한 키에 해당하는 설정 값

### 기본 설정 값
```json
{
    "theme": "default",
    "font_size": 14,
    "tab_size": 4,
    "auto_save": true
}
```

## 사용 방법
1. 서버 실행:
```bash
python cursor_settings_mcp.py
```

2. API 사용 예시:
```bash
# 모든 설정 조회
curl http://localhost:8000/cursor/settings

# 설정 업데이트
curl -X POST http://localhost:8000/cursor/settings \
  -H "Content-Type: application/json" \
  -d '{"theme": "dark", "font_size": 16, "tab_size": 2, "auto_save": true}'

# 특정 설정 조회
curl http://localhost:8000/cursor/settings/theme
```

## 개발 환경
- Python 3.10 이상
- FastAPI
- Pydantic

## 라이선스
MIT License 