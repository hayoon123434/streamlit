# 🎬 영화/드라마 상식 퀴즈 앱

> 오픈소스소프트웨어 중간고사 대체 과제  
> 학번: 2025404021 | 이름: 양하윤

---

## 📌 프로젝트 소개

영화와 드라마를 좋아하는 분들을 위한 **상식 퀴즈 앱**입니다.  
한국 영화/드라마(기생충, 오징어 게임, 이상한 변호사 우영우 등)부터  
할리우드 명작(어벤져스, 인터스텔라, 타이타닉)까지 총 10문제를 풀어볼 수 있습니다.

---

## ✅ 구현 기능

| 기능 | 설명 |
|------|------|
| 로그인 | 미리 정의된 아이디/비밀번호로 로그인, `st.session_state`로 로그인 상태 관리 |
| 캐싱 | `@st.cache_data`로 퀴즈 JSON 데이터를 캐싱하여 불필요한 파일 재로딩 방지 |
| 퀴즈 | 10문제 4지선다, 문제별 정답 확인 + 해설, 최종 점수 및 등급 표시 |

---

## 💡 캐싱을 적용한 이유

Streamlit은 버튼 클릭, 라디오 선택 등 위젯 상호작용이 발생할 때마다 스크립트 전체를 재실행합니다.  
캐싱 없이는 퀴즈를 진행하는 매 순간마다 `quiz_data.json` 파일을 반복해서 읽게 됩니다.  
`@st.cache_data`를 사용하면 최초 1회만 파일을 읽고, 이후에는 저장된 결과를 재사용하기 때문에 불필요한 I/O 작업을 줄일 수 있습니다.

---

## 🚀 실행 방법

```bash
# 1. 저장소 클론
git clone https://github.com/YOUR_USERNAME/movie-quiz-streamlit.git
cd movie-quiz-streamlit

# 2. 가상환경 생성 및 활성화
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate

# 3. 패키지 설치
pip install -r requirements.txt

# 4. 앱 실행
streamlit run app.py
```

---

## 🔐 테스트 계정

| 아이디 | 비밀번호 |
|--------|----------|
| 하윤   | movie123 |
| admin  | admin1234 |
| guest  | 1234 |

---

## 📁 프로젝트 구조

```
movie-quiz-streamlit/
├── app.py              # 메인 실행 파일
├── quiz_data.json      # 퀴즈 문제 데이터
├── requirements.txt    # 필요 패키지 목록
├── .gitignore          # Git 무시 파일 설정
└── README.md           # 프로젝트 설명
```
