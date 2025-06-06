# 인터넷 기초[04] 두 번째 과제 - 나만의 인공지능 서비스

## 개요
 - 서비스 이름 : <span style="background-color:rgb(182,0,80)">나만의 운동법</span>
 - 서비스 설명 : 사용자로부터 **나이**와 **몸무게** 그리고 **날씨**를 입력받으면, <span style="background-color:rgb(182,0,80)">나만의 운동법</span>는 그날의 날씨와 함께 나에게 맞는 운동법을 알려준다. 마지막에 힘내라는 메세지를 함께 보내준다.
 - 서비스 접속 주소 : [https://youjin20240752.github.io/duksung-exercise](https://youjin20240752.github.io/duksung-exercise)


## 첫 번째 구성 요소 - Gemini API
- <span style="background-color:rgb(174, 226, 61)">나만의 운동법</span>이 알려주는 오늘의 운동법은 구글의 LMM 모델인 Gemini의 API를 활용해 생성한다.
- 활용 모델 : [Gemini-2.0-flash](https://cloud.google.com/vertex-ai/generative-ai/docs/models/gemini/2-0-flash?hl=ko)
- 시스템 프롬프트 주안점
  - 나에게 맞는 운동법을 알려주는 인공지능에게 50년 경력을 가진 헬스 트레이너라고 역할을 부여했다.
  - 답변은 너무 길지 않게 제한했다.
  - 단순히 운동법을 알려주는 것이 아니라 그날의 날씨와 함께 알려주도록 지정했다.
  - 마지막에는 힘내라는 메세지를 보내도록 했다.

## 두 번째 구성 요소 - 프론트엔드
- <span style="background-color:rgb(174,226,61)">나만의 운동법</span> 서비스 페이지는 **HTML, CSS, JavaScript**를 사용하여 간단하게 구성하였다.
- CSS 스타일 시트는 [style.css](style.css)파일로 따로 분리하였다.
- 검색해서 나온 AI가 만들어준 운동하는 별의 이미지를 사용하였다.<br>
<img src="./image/exercise.png" width="200px" height="200px">

## 세 번째 구성 요소 - 백엔드
- 구글 Gemini API 호출을 위한 API 키가 노출되지 않도록, 프론트엔드의 요청을 받아서 Gemini API를 호출해주는 간단한 API 백엔드를 구성하였다.
- 해당 백엔드 로직은 서버리스(Severless) 함수 기능을 제공하는 Vercel에 배포했다.
- 코드 및 구현 내용은 [https://github.com/youjin20240752/duksung-exercise-api](https://github.com/youjin20240752/duksung-exercise-api)를 참고한다.