# 1. 리포지토리 내 폴더 및 파일명 규칙
경로: /Papers/YYYY-MM-DD-Paper-Title.md

파일명: 날짜와 논문 키워드를 포함해야 나중에 검색하기 편합니다.

예: 2026-04-14-Deep-Learning-Channel-Estimation.md

# 2. 추천 논문 TIL 템플릿 (개조식)
``` Markdown
# [논문 제목]
> **저자:** Name et al. (연도)  
> **컨퍼런스/저널:** ICASSP, IEEE Trans, etc.  
> **Link:** [DOI or ArXiv Link]

## 1. Motivation (연구 배경)
* 기존 기술의 한계: (예: 통신 채널의 비선형성 해결 불가)
* 이 논문이 해결하려는 핵심 질문 (Research Question)

## 2. Key Idea & Method (핵심 방법론)
* 제안하는 아키텍처/알고리즘의 핵심 원리
* 수식 포인트: (예: Loss Function $L = \lambda_1 L_{MSE} + \lambda_2 L_{REG}$)
* 주요 가정 (Assumptions): (예: AWGN 채널, Rayleigh Fading 가정 등)

## 3. Results (결과)
* 성능 지표: (예: 기존 방식 대비 SNR 3dB 개선)
* 가장 인상 깊은 Figure/Table 요약

## 4. Why it matters (나의 인사이트)
* **내 연구와의 연결고리:** 내 연구의 어떤 부분에 응용 가능한가?
* **한계점 및 후속 연구 아이디어:** 읽으면서 들었던 의문이나 개선점
* **Keywords:** #MIMO #Transformer #Channel_Estimation
3. 논문 TIL 작성 꿀팁
그림 위주로 기록: 텍스트만 적으면 나중에 기억이 안 납니다. 논문의 System Model이나 Main Result 그래프를 캡처해서 반드시 첨부하세요.

수식은 LaTeX로: 통신/AI 논문은 수식이 곧 언어입니다. 중요한 수식 한두 개는 직접 타이핑하며 이해하는 것이 큰 도움이 됩니다.

Abstract 복사 금지: Abstract를 그대로 옮기기보다는, 내가 이해한 대로 한 문장으로 **'한 줄 요약'**을 직접 써보는 연습을 하세요.

태그 활용: 파일 하단에 #Beamforming, #Optimization 같은 태그를 달아두면 GitHub 검색 기능을 통해 나중에 주제별로 모아보기 좋습니다.
```