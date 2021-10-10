---
title: "[Git] Good Commit Message"
layout: single
categories: Git
tag: [git, commit]
comments: true
---

### 이름 짓는것에 대해...
코딩 과정에서 함수, 변수, class, id 등 네이밍을 하게 된다. <br />
초반에는 네이밍에대한 부담이 많이 없지만, 코드의 내용이 많아지고 복잡해 질수록 네이밍에 많은 생각을 하게된다. <br />
commit 메시지 또한 이런 고민을 피할 수 없다.  <br />
특히 협업과 이후 관리에 있어서 좋은 커밋메시지를 작성해야함에는 틀림이 없다.


<br />

## 좋은 Commit Message의 7가지 규칙

1. 제목과 본문을 한 줄 띄워 분리
2. 제목은 영문 기준 **50자 이내**
3. 제목의 첫글자는 **대문자**로
4. 제목에 "." 금지
5. 제목은 **명령어**로
6. 영문 72자 마다 줄바꾸기
7. 본문은 어떻게 보다 **무엇을, 왜** 에 맞춰 작성

<br />

## Commit Message 제목 짓기
형식은 "태그: 제목" 입니다.

|  **태그 이름**   | **설명**                                                     |
| :--------------: | :----------------------------------------------------------- |
|       Feat       | 새로운기능을 추가할 경우                                     |
|       Fix        | 버그를 고친경우                                              |
|      Design      | CSS등 사용자 UI 디자인 변경                                  |
| !BREAKING CHANGE | 커다란API 변경                                               |
|     !HOTFIX      | 급하게 치명적인 버그를 초쳐야하는 경우                       |
|      Style       | 코드 포맷 변경, 세미콜론 누락 등 코드 수정이 없는 경우       |
|     Refactor     | 프로덕션 코드 리팩토링                                       |
|     Comment      | 필요한 주석 추가 및 변경                                     |
|       Docs       | 문서를 수정한 경우                                           |
|       Test       | 테스트 추가, 테스트 리팩토링(프로덕션 코드변경X)             |
|      Chore       | 빌드 테스트 업데이트, 패키지 메니저를 설정하는 경우(프로덕션 코드 변경X) |
|      Rename      | 파일 혹은 폴더명을 수정하거나 옮기는 작업만 있는 경우        |
|      Remove      | 파일을 삭제하는 작업만 수행한 경우                           |


<br />
이후에도 다시 볼 수도 있을 것 같다는 내용들만 간단히 가져왔습니다. <br />
추가적인 설명을 보고 싶은 분들은 아래 링크를 참고서 하시고 길 바랍니다.<br />



**< Refer to >**<br />
<span class="link">
[How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)<br />
[협업을 위한 git 커밋컨벤션 설정하기](https://overcome-the-limits.tistory.com/entry/%ED%98%91%EC%97%85-%ED%98%91%EC%97%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B8%B0%EB%B3%B8%EC%A0%81%EC%9D%B8-git-%EC%BB%A4%EB%B0%8B%EC%BB%A8%EB%B2%A4%EC%85%98-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0)
</span>

