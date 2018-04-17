---
title: Visual Studio 디버거에서 호출 스택을 보려면 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/06/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.callstack
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a55f940c6310300b458f4497f8659bfc0897d4b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="view-the-call-stack-and-use-the-call-stack-window-in-the-visual-studio-debugger"></a>호출 스택 보기 및 Visual Studio 디버거에서 호출 스택 창 사용

사용 하 여는 **호출 스택** 창 현재 스택에 있는 함수 또는 프로시저 호출을 볼 수 있습니다. **호출 스택** 창에 있는 메서드 및 함수 호출 되는 순서를 가져오는 표시 합니다. 호출 스택은 검토 하 고 응용 프로그램의 실행 흐름을 이해 하는 좋은 방법입니다.
  
때 [디버깅 기호가](#bkmk_symbols) 호출 스택의 일부에 대해 사용할 수 없는 **호출 스택** 창 호출 스택의 해당 부분에 대 한 올바른 정보를 표시 하지 못할 수 있습니다. 이 경우 다음과 같이 출력이 됩니다.  
  
`[Frames below may be incorrect and/or missing, no symbols loaded for name.dll]`

>  [!NOTE]
> **호출 스택** 창은 Eclipse와 같은 일부 Ide에서 디버그 관점 비슷합니다. 

> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 여기서 설명하는 것과 다를 수 있습니다. 설정을 변경 하려면 선택 **설정 가져오기 및 내보내기** 에 **도구** 메뉴.  참조 [IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)
  
## <a name="view-the-call-stack-while-in-the-debugger"></a>디버거 내에서 호출 스택 보기 
  
-   디버깅 하는 동안는 **디버그** 메뉴 선택 **Windows > 호출 스택**합니다.

 ![호출 스택 창](../debugger/media/dbg_basics_callstack_window.png "CallStackWindow")

노란색 화살표는 현재 실행 포인터가 있는 스택 프레임을 나타냅니다. 기본적으로이 소스에 해당 정보가 표시 되는 스택 프레임은 **지역**, **자동**, **조사식**, 및 **디스어셈블리** windows . 스택의 다른 프레임 디버거 컨텍스트를 변경 하려는 경우 할 수 있는 하 [다른 스택 프레임으로 전환](#bkmk_switch)합니다.   
  
## <a name="display-non-user-code-in-the-call-stack-window"></a>호출 스택 창에서 사용자가 아닌 코드 표시  
  
-   마우스 오른쪽 단추로 클릭는 **호출 스택** 창과 선택 **외부 코드 포시**합니다.

사용자 이외의 모든 코드가 표시 되지 않는 경우 됩니다 [내 코드만](../debugger/just-my-code.md) 를 사용할 수 있습니다. 관리 코드에서 사용자 코드가 아닌 프레임 기본적으로 숨겨집니다. 사용자 코드가 아닌 프레임 대신 같이 출력이 됩니다.  
  
**[\<외부 코드 >]**  
  
## <a name="bkmk_switch"></a> 다른 스택 프레임 (디버거 컨텍스트 변경)으로 전환
  
1.  에 **호출 스택** 창, 해당 코드와 데이터를 보려는 스택 프레임을 마우스 오른쪽 단추로 클릭 합니다.

    또는에서 프레임을 두 번 클릭 수는 **호출 스택** 창에 선택한 프레임으로 전환 합니다. 
  
2.  선택 **프레임으로 전환**합니다.  
  
     선택한 스택 프레임 옆에 끝이 굽은 녹색 화살표가 나타납니다. 실행 포인터는 여전히 노란색 화살표로 표시되어 있는 원래 프레임에 그대로 있습니다. 선택 하는 경우 **단계** 또는 **계속** 에서 **디버그** 선택한 프레임이 아닌, 메뉴, 원래 프레임에서 실행이 계속 됩니다.  
  
## <a name="view-the-source-code-for-a-function-on-the-call-stack"></a>호출 스택에 있는 함수의 소스 코드 보기  
  
-   에 **호출 스택** 창, 소스 코드를 보려는 함수를 선택 하려면 마우스 오른쪽 단추로 클릭 **소스 코드로 이동**합니다.

## <a name="run-to-a-specific-function-from-the-call-stack-window"></a>호출 스택 창에서 특정 함수까지 실행  
  
-  에 **호출 스택** 창 함수를 선택 합니다. 마우스 오른쪽 단추로 클릭 하 고 선택 **커서까지 실행**합니다.  
  
## <a name="set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>함수 호출의 종료 지점에 중단점을 설정 합니다.  
  
-   참조 [호출 스택 함수에 중단점을 설정](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_the_call_stack_window)합니다.

## <a name="display-calls-to-or-from-another-thread"></a>나 다른 스레드로 호출 표시  
  
-   마우스 오른쪽 단추로 클릭는 **호출 스택** 창과 선택 **다른 스레드로 호출 / 다른 스레드에서 호출 포함**합니다.   
  
## <a name="visually-trace-the-call-stack"></a>호출 스택을 시각적으로 추적  

Visual Studio Enterprise (전용)를 사용 하는 경우 디버그 하는 동안 호출 스택에 대 한 코드 맵을 볼 수 있습니다.

- 에 **호출 스택** 창 바로 가기 메뉴를 엽니다. 선택 **호출 스택 코드 맵에 표시**합니다. (키보드: **CTRL** + **SHIFT** + **`**)  
  
    자세한 내용은 참조 [디버깅 하는 동안 호출 스택의 메서드 매핑할](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)합니다.

![호출 스택 코드 맵에 표시](../debugger/media/dbg_basics_show_call_stack_on_code_map.gif "ShowCallStackOnCodeMap")
  
## <a name="view-the-disassembly-code-for-a-function-on-the-call-stack"></a>호출 스택에 있는 함수의 디스어셈블리 코드 보기  
  
-   에 **호출 스택** 창을 마우스 오른쪽 단추로 클릭 디스어셈블리 코드를 보려는 함수를 보고 선택 **디스어셈블리로 이동**합니다.    

## <a name="change-the-optional-information-displayed"></a>표시 되는 선택적 정보를 변경 합니다.  
  
-   마우스 오른쪽 단추로 클릭는 **호출 스택** 창 및 세트나 clear **표시 \< ***정보를***>**합니다.  
  
## <a name="bkmk_symbols"></a> 모듈에 대 한 기호 로드
에 **호출 스택** 창에서 기호가 로드 현재 되어 하지 않은 코드에 대 한 디버깅 기호를 로드할 수 있습니다. 이러한 기호는 Microsoft 공용 기호 서버에서 다운로드한 .NET Framework 또는 시스템 기호일 수도 있고 디버깅 중인 컴퓨터의 기호 경로에 있는 기호일 수도 있습니다.  
  
참조 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
### <a name="to-load-symbols"></a>기호를 로드하려면  
  
1.  에 **호출 스택** 창 오른쪽 단추로 클릭 하는 기호에 대 한 스택 프레임은 로드 되지 않습니다. 프레임이 흐리게 표시됩니다.  
  
2.  가리킨 **기호 로드** 클릭 하 고 **Microsoft 기호 서버** (있는 경우) 하거나 기호 경로를 찾습니다.  
  
### <a name="to-set-the-symbol-path"></a>기호 경로를 설정하려면  
  
1.  에 **호출 스택** 창 선택 **기호 설정** 바로 가기 메뉴에서.  
  
     **옵션** 대화 상자가 열립니다 및 **기호** 페이지가 표시 됩니다.  
  
2.  클릭 **설정을 기호**합니다.  
  
3.  에 **옵션** 대화 상자에서 폴더 아이콘을 클릭 합니다.  
  
     에 **기호 파일 (.pdb) 위치** 상자 커서가 표시 됩니다.  
  
4.  디버깅 중인 컴퓨터의 기호 위치에 대한 디렉터리 경로 이름을 입력합니다. 로컬 및 원격 디버깅을 위해 로컬 컴퓨터의 경로입니다.
  
5.  **확인**을 클릭하여 **옵션** 대화 상자를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 스택 창의 혼합 코드 및 누락된 정보](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [중단점 사용](../debugger/using-breakpoints.md)