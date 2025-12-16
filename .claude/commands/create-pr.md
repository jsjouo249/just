티켓 번호: $ARGUMENTS
티켓 접두사: FCLXP-
지라 베이스 URL: https://fastcampus.atlassian.net/browse

위 티켓 번호들(쉼표로 구분된 경우 각각)에 접두사를 붙여서 티켓 ID를 만들어주세요.
예: 10512, 10513 → FCLXP-10512, FCLXP-10513

각 티켓에 대해 다음을 수행해주세요:

1. 각 티켓의 이슈 정보를 MCP(Jira)를 통해 조회하여 티켓 제목을 반드시 가져올 것
2. ./PULL_REQUEST_TEMPLATE.md 파일을 읽어서 템플릿 구조 확인
3. Issue 섹션에 아래 형식으로 모든 티켓 나열 (반드시 티켓 제목 포함):
   - [TICKET-ID: 이슈제목](https://fastcampus.atlassian.net/browse/TICKET-ID)
   - 예시: [FCLXP-10575: [BE] 데이터 비교 후, 누락 없으면 extras 코드 변경](https://fastcampus.atlassian.net/browse/FCLXP-10575)
4. 변경사항 커밋 및 푸시:
   - `git status`로 변경사항 확인
   - `git diff`로 코드 변경 내용 분석
   - 변경사항이 있으면 `git add .`로 스테이징
   - 코드 변경 내용을 분석하여 Conventional Commit 형식으로 커밋 메시지 작성
     - 형식: `<type>: <변경 내용 요약>`
     - type: feat(새 기능), fix(버그 수정), refactor(리팩토링), docs(문서), style(코드 스타일), test(테스트) 등
     - 주의: Co-Authored-By나 Generated with Claude 등의 서명을 커밋 메시지에 포함하지 말 것
   - `git commit`으로 커밋
   - `git push -u origin <현재브랜치>`로 원격에 푸시
5. `gh pr create` 명령어로 PR 생성
   - title: 첫 번째 티켓의 제목 사용 (여러 개면 적절히 요약)
   - body: PULL_REQUEST_TEMPLATE.md 기반으로 작성하되, Issue 섹션에 위에서 만든 티켓 링크들(제목 포함) 포함
