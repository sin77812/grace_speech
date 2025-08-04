# Using Gemini CLI for Large Codebase Analysis

When analyzing large codebases or multiple files that might exceed context limits, use the Gemini CLI with its massive
context window. Use `gemini -p` to leverage Google Gemini's large context capacity.

## File and Directory Inclusion Syntax

Use the `@` syntax to include files and directories in your Gemini prompts. The paths should be relative to WHERE you run the
  gemini command:

### Examples:

**Single file analysis:**
gemini -p "@src/main.py Explain this file's purpose and structure"

Multiple files:
gemini -p "@package.json @src/index.js Analyze the dependencies used in the code"

Entire directory:
gemini -p "@src/ Summarize the architecture of this codebase"

Multiple directories:
gemini -p "@src/ @tests/ Analyze test coverage for the source code"

Current directory and subdirectories:
gemini -p "@./ Give me an overview of this entire project"

# Or use --all_files flag:
gemini --all_files -p "Analyze the project structure and dependencies"

Implementation Verification Examples

Check if a feature is implemented:
gemini -p "@src/ @lib/ Has dark mode been implemented in this codebase? Show me the relevant files and functions"

Verify authentication implementation:
gemini -p "@src/ @middleware/ Is JWT authentication implemented? List all auth-related endpoints and middleware"

Check for specific patterns:
gemini -p "@src/ Are there any React hooks that handle WebSocket connections? List them with file paths"

Verify error handling:
gemini -p "@src/ @api/ Is proper error handling implemented for all API endpoints? Show examples of try-catch blocks"

Check for rate limiting:
gemini -p "@backend/ @middleware/ Is rate limiting implemented for the API? Show the implementation details"

Verify caching strategy:
gemini -p "@src/ @lib/ @services/ Is Redis caching implemented? List all cache-related functions and their usage"

Check for specific security measures:
gemini -p "@src/ @api/ Are SQL injection protections implemented? Show how user inputs are sanitized"

Verify test coverage for features:
gemini -p "@src/payment/ @tests/ Is the payment processing module fully tested? List all test cases"

When to Use Gemini CLI

Use gemini -p when:
- Analyzing entire codebases or large directories
- Comparing multiple large files
- Need to understand project-wide patterns or architecture
- Current context window is insufficient for the task
- Working with files totaling more than 100KB
- Verifying if specific features, patterns, or security measures are implemented
- Checking for the presence of certain coding patterns across the entire codebase

Important Notes

- Paths in @ syntax are relative to your current working directory when invoking gemini
- The CLI will include file contents directly in the context
- No need for --yolo flag for read-only analysis
- Gemini's context window can handle entire codebases that would overflow Claude's context
- When checking implementations, be specific about what you're looking for to get accurate results

메인 컬러: 딥그린 (#06342e).

포인트 컬러: 브라운 (#937258).

Grace Speech 모바일 웹사이트 제작 가이드라인
📋 프로젝트 개요

프로젝트명: Grace Speech (그레이스 스피치) 모바일 홈페이지
클라이언트: 주식회사 달맞이 / 김은혜 대표이사
목표: 모바일 최적화된 심플하고 가독성 좋은 프리미엄 스피치 컨설팅 홈페이지
핵심 목적: 회사/서비스 정보 제공 + 상담 신청 유도
주요 유입 경로: 블로그, 네이버 검색

🎨 디자인 컨셉 & 브랜딩
전반적인 분위기

고급스럽고 모던한 느낌: 과하지 않고 정제된 고급스러움
에르메스 스타일: 루이비통의 화려함보다는 은은한 고급스러움
무로고 컨셉: 빅 로고보다는 무로고에 은은한 아름다움
이보영 이미지: 냉철하고 깔끔하며 일처리 확실하고 신뢰감 최고
최우선 원칙: 심플하고 가독성 좋게

컬러 팔레트

메인 컬러: 딥그린 (#2C5F56 또는 유사 톤)
포인트 컬러: 브라운 계열 (#8B4513 또는 유사한 차분한 브라운)
포인트 컬러 사용처: CTA 버튼, 강조 요소, 액센트

폰트 가이드라인

폰트 스타일: 산세리프 계열 (너무 얇지 않은)
가독성 최우선: 행간과 자간을 충분히 확보
위계질서: 제목, 부제목, 본문의 폰트 크기와 굵기를 명확히 구분
모바일 최적화: 모바일에서 읽기 편한 폰트 크기 적용

📱 레이아웃 & 네비게이션
기본 레이아웃

모바일 퍼스트: 모든 레이아웃은 모바일 환경 최적화
세로형 구성: 모바일에 적합한 세로형 레이아웃
반응형 처리: 컴퓨터와 모바일에서 모두 최적화

네비게이션 구조

햄버거 메뉴: 상단 우측에 삼선 햄버거 버튼
메뉴 애니메이션: 클릭 시 화면 오른쪽에서 세로로 슬라이드
메뉴 항목:

1대1 컨설팅
기업 컨설팅
대표 소개
서비스 소개



고정 버튼 (Fixed Buttons)

위치: 화면 좌측 하단 고정
항상 표시: 스크롤과 관계없이 모든 페이지에서 보임
버튼 구성:

상담신청: 포인트 컬러(브라운) 적용, 문의 양식으로 연결
제안서 다운로드: PDF 파일 다운로드 링크 ('★스피치 교육 제안서_25.7.pdf')



📄 페이지 구조
1. 메인 페이지 (Home)
헤더

로고/업체명 + 우측 햄버거 메뉴

히어로 섹션

배경: 딥그린 컬러 활용
제목: "인생을 바꾸는 스피치 컨설팅"
부제목: "개인 스스로의 삶이 자신이 없거나, 운영하고 계신 조직이 만족스럽지 않다면 올바른 말하기가 필요한 시점입니다."

핵심 가치 섹션

제목: "운명을 바꾸는 말하기의 중요성"
개인과 조직 혜택을 아이콘과 함께 표시

차별점 섹션

제목: "진짜 전문가 GRACE SPEECH가 해결해드리겠습니다"
핵심 강점: 15년차 아나운서 출신, 맞춤형 프리미엄 컨설팅, 1:1 퍼스널 트레이닝

고객 후기 섹션

"3주간의 그레이스 스피치 프로그램이 제 인생을 바꿨어요."
"10억 규모의 투자유치에 성공했습니다."

2. 1대1 컨설팅 페이지
타이틀: "개인의 인생을 바꾸는 스피치"
문제 해결 섹션

PROBLEM vs SOLUTION 대비 구성
독학의 문제 → 맞춤형 커리큘럼
기회의 문제 → 시뮬레이션 경험

기대 효과

자신감 향상, 전문성 강화, 다양한 상황 적응

성공 사례

금융 공기업 면접 합격 사례
전문의 과정 불안도 개선 사례

3. 기업 컨설팅 페이지
타이틀: "법인의 인생을 바꾸는 스피치"
문제 해결 섹션

기업이 겪는 커뮤니케이션 문제
그레이스 스피치의 해결책

기대 효과

영업성과 향상, 신뢰 구축, 조직문화 개선

성공 사례

스타트업 CEO 피칭 성공
세일즈 매니저 교육 사례

4. 대표 소개 페이지
타이틀: "15년 경력, 아나운서 출신 대표 컨설턴트"
대표 프로필

김은혜 대표 경력 사항
경찰인재개발원 최우수 감사상 등 공신력 있는 성과

전문성 섹션

WHY GRACE SPEECH?
맞춤형, 실전형, ONE-STOP 특징

5. 서비스 소개 페이지
타이틀: "제대로 배워야 실력이 향상됩니다"
프로그램 소개

8단계 커리큘럼을 모바일 세로 리스트로 구성
100% 맞춤형 설계 강조

🖼️ 콘텐츠 활용 가이드
이미지 활용

제공된 이미지: KakaoTalk_Photo_2025-08-04-14-24-17.jpg, KakaoTalk_Photo_2025-08-04-14-24-23.jpg 등 활용
반응형 처리: 컴퓨터와 모바일에서 모두 최적화
최적화: 웹에 적합한 형식으로 압축 및 변환

텍스트 처리

약점 최소화: 높은 가격, 부족한 후기 → 프리미엄 컨셉, 프라이빗 컨설팅으로 치환
강점 부각: 아나운서 경력, 맞춤형 서비스, 실제 성과 강조

📞 연락처 정보

주소: 안양시 동안구 엘에스로 금정역 SKV1 2차 1616호
웹사이트: www.gracespeech.com
전화: 0507-1349-1522
이메일: dalmajiroad@gmail.com

⚡ 추가 기술 요구사항

로딩 속도 최적화: 이미지 압축 및 최적화
SEO 친화적: 검색엔진 최적화 고려
접근성: 명확한 색상 대비와 의미적 마크업
