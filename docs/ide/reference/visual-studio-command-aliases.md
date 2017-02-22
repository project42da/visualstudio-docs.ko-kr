---
title: "Visual Studio 명령 별칭 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "별칭, Visual Studio 명령"
  - "명령 별칭"
  - "명령, 별칭"
  - "미리 정의된 명령 별칭"
  - "미리 정의된 명령 별칭"
  - "Visual Studio 명령"
  - "Visual Studio, 명령"
ms.assetid: de8bb378-8c1c-4087-a9a5-537fa8314c19
caps.latest.revision: 17
caps.handback.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Visual Studio 명령 별칭
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

별칭은 명령을 실행하는 데 필요한 텍스트를 짧게 만들어 **찾기\/명령** 입력란 또는 **명령** 창에 해당 명령을 입력할 수 있도록 합니다.  예를 들어, **파일 열기** 대화 상자를 표시하려면 `>File.OpenFile`을 입력하는 대신 미리 정의된 별칭인 `>of`를 사용하면 됩니다.  
  
 **명령** 창에 `alias`를 입력하면 현재 별칭 및 해당 정의 목록이 표시되고  `>cls`를 입력하면 **명령** 창의 내용이 지워집니다.  특정 명령에 대한 별칭을 참조하려면 `alias <command name>`을 입력하십시오.  
  
 Visual Studio 명령 \(인자 포함 혹은 포함하지 않고\) 중 하나에 대한 사용자 고유 별칭을 쉽게 만들 수 있습니다.  예를 들어, 별칭에 대한 구문은 다음과 같습니다. `File.NewFile MyFile.txt`는 `alias MyAlias File.NewFile MyFile.txt`.  별칭은 `alias <alias name> /delete`를 이용하여 삭제할 수 있습니다.  
  
 다음 표에 미리 정의된 Visual Studio 명령 별칭 목록이 포함되어 있습니다.  어떤 명령은 두 개 이상의 미리 정의된 별칭을 사용하기도 합니다.  이러한 명령에 대한 올바른 구문, 인수 및 스위치를 설명하는 자세한 항목을 보려면 아래에 있는 명령 이름에 대한 링크를 클릭합니다.  
  
|명령 이름|Alias|전체 이름|  
|-----------|-----------|-----------|  
|[인쇄 명령](../../ide/reference/print-command.md)|?|디버그.인쇄|  
|[간략한 조사식 명령](../../ide/reference/quick-watch-command.md)|??|디버그.간략한조사식|  
|새 프로젝트 추가|AddProj|파일.새프로젝트추가|  
|[별칭 명령](../../ide/reference/alias-command.md)|Alias|도구.별칭|  
|자동 창|Autos|디버그.자동|  
|중단점 창|bl|디버그.중단점|  
|중단점 설정\/해제|bp|디버그.중단점설정해제|  
|호출 스택 창|CallStack|디버그.호출스택|  
|책갈피 지우기|ClearBook|편집.책갈피지우기|  
|닫기|닫기|파일.닫기|  
|모든 문서 닫기|CloseAll|창.모든문서닫기|  
|모두 지우기|cls|편집.모두지우기|  
|명령 모드|cmd|보기.명령창|  
|코드 보기|코드|보기.코드보기|  
|[메모리 목록 표시 명령](../../ide/reference/list-memory-command.md)|d|디버그.메모리목록표시|  
|ANSI로서 [메모리 목록 표시 명령](../../ide/reference/list-memory-command.md)|da|디버그.메모리목록표시 \/Ansi|  
|[메모리 목록 표시 명령](../../ide/reference/list-memory-command.md) 1바이트 형식|db|디버그.메모리목록표시 \/Format:OneByte|  
|4 바이트 형식의 으로 ANSI로 [메모리 목록 표시 명령](../../ide/reference/list-memory-command.md)|dc|디버그.메모리목록표시 \/Format:FourBytes \/Ansi|  
|[메모리 목록 표시 명령](../../ide/reference/list-memory-command.md) 4바이트 형식|dd|디버그.메모리목록표시 \/Format:FourBytes|  
|BOL까지 삭제|DelBOL|편집.BOL까지삭제|  
|EOL까지 삭제|DelEOL|편집.EOL까지삭제|  
|가로 공백 삭제|DelHSp|편집.가로공백삭제|  
|뷰 디자이너|designer|보기.디자이너보기|  
|[메모리 목록 표시 명령](../../ide/reference/list-memory-command.md) 부동 소수점 형식|df|디버그.메모리목록표시 \/Format:Float|  
|디스어셈블리 창|disasm|디버그.디스어셈블리|  
|[메모리 목록 표시 명령](../../ide/reference/list-memory-command.md) 8 바이트 형식|dq|디버그.메모리목록표시 \/Format:EightBytes|  
|유니코드로 [메모리 목록 표시 명령](../../ide/reference/list-memory-command.md)|du|디버그.메모리목록표시 \/Unicode|  
|[문 실행 명령](../../ide/reference/evaluate-statement-command.md)|eval|디버그.문실행|  
|끝내기|끝내기|파일.끝내기|  
|선택 영역 서식|format|편집.선택영역서식|  
|전체 화면|FullScreen|보기.전체화면|  
|[시작 명령](../../ide/reference/start-command.md)|g|디버그.시작|  
|[이동 명령](../../ide/reference/go-to-command.md)|GotoLn|편집.이동|  
|중괄호로 이동|GotoBrace|편집.중괄호로이동|  
|F1도움말|도움말|도움말.F1도움말|  
|직접 실행 모드|immed|도구.직접실행모드|  
|파일을 텍스트로 삽입|InsertFile|편집.파일을텍스트로삽입|  
|[호출 스택 목록 표시 명령](../../ide/reference/list-call-stack-command.md)|kb|디버그.호출스택목록표시|  
|소문자로|Lcase|편집.소문자로|  
|줄 잘라내기|LineCut|편집.줄잘라내기|  
|줄 삭제|LineDel|편집.줄삭제|  
|멤버 목록|ListMembers|편집.멤버목록|  
|지역 창|Locals|디버그.지역|  
|[명령 창 출력 로그 명령](../../ide/reference/log-command-window-output-command.md)|로그|도구.명령창출력로그|  
|명령 창 표시 모드|mark|도구.명령창표시모드|  
|메모리 창|Memory Memory1|디버그.메모리1|  
|메모리 창 2|Memory2|디버그.메모리2|  
|메모리 창 3|Memory3|디버그.메모리3|  
|메모리 창 4|Memory4|디버그.메모리4|  
|[기수 설정 명령](../../ide/reference/set-radix-command.md)|n|디버그.기수설정|  
|[웹 브라우저 표시 명령](../../ide/reference/showwebbrowser-command.md)|nav navigate|보기.웹브라우저표시|  
|다음 책갈피|NextBook|편집.다음책갈피|  
|[새 파일 명령](../../ide/reference/new-file-command.md)|nf|파일.새파일|  
|새 프로젝트|np NewProj|파일.새프로젝트|  
|[파일 열기 명령](../../ide/reference/open-file-command.md)|of Open|파일.파일열기|  
|[프로젝트 열기 명령](../../ide/reference/open-project-command.md)|op|파일.프로젝트열기|  
|정의 부분만 보이기\/개요 만들기 중지|OutlineDefs StopOutlining|편집.정의부분만보이기|  
|프로시저 단위 실행|p|디버그.프로시저단위실행|  
|매개 변수 정보|ParamInfo|편집.매개변수정보|  
|프로시저 나가기|pr|디버그.프로시저나가기|  
|이전 책갈피|PrevBook|편집.이전책갈피|  
|파일 인쇄|print|파일.인쇄|  
|속성 창|props|보기.속성창|  
|Stop|q|디버그.디버깅중지|  
|다시 실행|redo|편집.다시실행|  
|레지스터 창|registers|디버그.레지스터|  
|커서까지 실행|rtc|디버그.커서까지실행|  
|선택한 항목 저장|save|파일.선택한항목저장|  
|모두 저장|SaveAll|파일.모두저장|  
|다른 이름으로 저장|SaveAs|파일.다른이름으로선택한항목저장|  
|[셸 명령](../../ide/reference/shell-command.md)|shell|도구.셸|  
|파일에서 찾기 중지|StopFind|편집.파일에서찾기 \/중지|  
|앵커 바꾸기|SwapAnchor|편집.앵커바꾸기|  
|한 단계씩 코드 실행|t|디버그.한단계씩코드실행|  
|선택 영역 탭으로 변환|tabify|편집.선택영역의공백을탭으로|  
|작업 목록 창|TaskList|보기.작업목록|  
|스레드 창|스레드|디버그.스레드|  
|가로 바둑판식 배열|TileH|창.가로바둑판식배열|  
|세로 바둑판식 배열|TileV|창.세로바둑판식배열|  
|책갈피 설정\/해제|ToggleBook|편집.책갈피설정해제|  
|도구 상자 창|toolbox|보기.도구상자|  
|[디스어셈블리 목록 표시 명령](../../ide/reference/list-disassembly-command.md)|u|디버그.디스어셈블리목록표시|  
|대문자로|Ucase|편집.대문자로|  
|실행 취소|undo|편집.실행취소|  
|선택 영역의 탭을 공백으로|Untabify|편집.선택영역의탭을공백으로|  
|조사식 창|Watch|디버그.조사식N|  
|자동 줄 바꿈 설정\/해제|WordWrap|편집.자동줄바꿈설정해제|  
|프로세스 나열|&#124;|Debug.ListProcesses|  
|[스레드 목록 표시 명령](../../ide/reference/list-threads-command.md)|~ ~\*k ~\*kb|Debug.ListThreads Debug.ListTheads \/AllThreads|  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)