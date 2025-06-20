
# Emoting - Rotation Based Dating Service

## 📌 프로젝트 개요

Emoting은 사용자의 비언어적 표현(포즈 및 표정)을 실시간으로 감지하여,
각 행동과 표정을 횟수 단위로 카운팅하고 가중치를 적용하여 최종 점수를 산출하는 소개팅 지원 시스템입니다.

- 비언어적 커뮤니케이션 분석 → 호감도 점수화
- 소개팅 인터랙션 분석에 최적화
- 실시간 분석 / 실시간 피드백 가능

---

## 🎯 프로젝트 목표

- 실시간 포즈 및 표정 감지
- 행동 및 표정별 횟수 기록
- 가중치 기반 점수화 시스템 구축
- Raspberry Pi를 활용한 휴대형 디바이스 개발

---

## 🗓 프로젝트 기간

- 2025.02.19 ~ 2025.03.17

---

## 🔎 데이터 수집 및 전처리

### 포즈 데이터

- 이미지 크롤링 → Mediapipe를 활용해 33개 관절 좌표 추출
- 총 7가지 행동 라벨 구축:  
  `다리꼬기, 팔짱끼기, 머리넘기기, 턱만지기, 입가리며 웃기, 마시기, 먹기`

### 표정 데이터

- FER-2013 표정 데이터셋 활용 (16만장)
- Mediapipe 얼굴 좌표 추출 → 25개 랜드마크 사용
- 7가지 표정 라벨:  
  `Happy, Sad, Neutral, Fear, Surprise, Disgust, Angry`

### 전처리

- 잘못된 데이터 제거
- 라벨 불균형 보정

---

## 🤖 모델 학습 및 성능

### 포즈 인식 모델
- **XGBoost**
- 정확도: 87.03%

### 표정 인식 모델
- **CNN**
- 정확도: 40.67%

### 점수화 방식

- 횟수 카운팅 → 행동·표정별 가중치 적용 → 실시간 점수 산출
- 시간 구간별 피드백 문장 생성

---

## 🛠 시스템 아키텍처

- Mediapipe → XGBoost & CNN 예측 → 점수화 → 실시간 리포트
- Raspberry Pi + 웹캠 실시간 촬영 및 처리
- 추후 DB 확장성 고려한 설계

---

## 📊 시연 장면

> 📌 시연 영상 및 실제 영상 데모는 영상 파일 또는 링크로 별도 제공

- 시스템 구동 시뮬레이션 캡처 및 실시간 분석 화면
- https://drive.google.com/file/d/1myhZz2go-v_shcjXiCg-9TNe5S2_IYIx/view?usp=sharing

---

## 👥 팀 소개

| 이름 | 역할 |
| ---- | ---- |
| 김정원 | 서비스 기획 |
| 박시원 | 서비스 기획 |
| 이정인 | 데이터 분석 |
| 신지민 | 데이터 분석 |
| 하승주 | 데이터 분석 |

---

## 📚 발표자료
- https://drive.google.com/file/d/16Fm-cmtNECwjJWlFwpKmbAHDLOVA2TNG/view?usp=sharing

---

## 📚 참고자료

- Mediapipe: [https://developers.google.com/mediapipe](https://developers.google.com/mediapipe)
- FER-2013: [https://www.kaggle.com/datasets/msambare/fer2013](https://www.kaggle.com/datasets/msambare/fer2013)
