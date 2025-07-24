# 🤖 KoBot Backend

OpenWebUI 호환 법률/내규 RAG 챗봇 백엔드 API

## 📋 OVERVIEW

법률 문서와 내규 문서에 대한 질의응답을 제공하는 RAG(Retrieval-Augmented Generation) 시스템입니다. OpenAI API와 완전 호환되어 OpenWebUI 등 다양한 클라이언트에서 사용할 수 있습니다.

## ✨ FUNCTION

### 🎯 **OpenAI API 호환**
- `/v1/chat/completions` - 채팅 완성 API (스트리밍 지원)
- `/v1/models` - 사용 가능한 모델 목록
- `/v1/embeddings` - 임베딩 생성 API
- `/v1/health` - 헬스 체크

### 🧠 **다중 모드 RAG 시스템**
- **법률 모드**: 법률 문서 기반 질의응답
- **정책 모드**: 내부 정책/규정 기반 질의응답  
- **일반 모드**: 컨텍스트 없는 일반 대화

### 🔄 **LangGraph 워크플로우**
- 쿼리 재작성을 통한 검색 성능 향상
- 멀티쿼리 검색으로 포괄적 문서 수집
- 문서 압축을 통한 컨텍스트 최적화
- 스트리밍 응답 지원

### 🎛️ **OpenWebUI 전용 기능**
- 채팅 태그 자동 생성
- 채팅 제목 자동 생성
- Follow-up 질문 제안
- 한국어 응답 강제 적용

## 🏗️ ARCHITECTURE

<img width="1200" height="676" alt="Image" src="https://github.com/user-attachments/assets/392bb39e-adfa-4e01-8b20-8fcdddf94003" />

<img width="821" height="618" alt="Image" src="https://github.com/user-attachments/assets/da6f1402-d9ca-43a1-9cd7-5147e8266025" />

## 📁 PROJECT STRUCTURE

```
backend/
├── app/
│   ├── core/           # 핵심 설정
│   │   ├── config.py   # 환경 설정
│   │   └── logging.py  # 로깅 설정
│   ├── chains.py       # LangChain 체인 정의
│   ├── nodes.py        # LangGraph 노드 구현
│   ├── services.py     # 비즈니스 로직
│   ├── states.py       # 상태 관리
│   ├── retrievers.py   # 문서 검색기
│   ├── openai_api.py   # OpenAI 호환 API
│   ├── openai_schemas.py # API 스키마
│   ├── law_rag.py      # 법률 RAG 체인
│   ├── policy_rag.py   # 정책 RAG 체인
│   ├── main.py         # FastAPI 애플리케이션
│   ├── chroma_db/      # ChromaDB 데이터
│   └── models/         # 임베딩 모델
└── requirements.txt    # Python 의존성
```

## 🛠️ TECH STACK
```
Backend
    - Framework: FastAPI
    - Runtime: Python 3.11, Uvicorn
    - AI: Langchain & LangGraph
    - Vector DB: ChromaDB

Frontend
    - Interface: Open WebUI(Svelte, JavaScripts)
    - Document Processing: Docling Server

InfraStructure
    - Containerization: Docker, Docker Compose
```
