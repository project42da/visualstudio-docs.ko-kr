---
title: 편집 하며 계속 하기 오류 메시지 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 01cd34aacb4abea5f2f3ce29fcb53ba34aaeaf21
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="edit-and-continue-error-message-dialog-box"></a>편집하며 계속하기 오류 메시지 대화 상자
편집 하며 계속 하기, 지원 되는 언어로 디버깅할 때이 대화 상자가 나타납니다 하지만 **편집 하며 계속 하기** 를 코드 변경 내용을 유형에 대해 사용할 수 없습니다. 대화 상자 안의 오류 메시지에서 보다 자세한 설명을 제공합니다. 이 대화 상자가 표시될 수 있는 원인은 다음과 같습니다.  

-   SQL Server 코드를 편집하려고 한 경우

-   최적화된 코드를 편집하려고 한 경우 (디버그 빌드를 릴리스 빌드로 전환 할 수 있습니다.)

-   실행 하는 동안 코드를 편집 하려고 한 (대신 디버거에서 일시 중지 된 동안). 시도 [중단점 설정](../debugger/using-breakpoints.md) 및 일시 중지 된 동안 코드를 편집 합니다.

-   관리되지 않는 디버깅을 사용하도록 설정된 상태에서 관리 코드를 편집하려고 한 경우. 편집 하며 계속 하기에서 작동 하지 않습니다 [혼합 모드 디버깅](../debugger/how-to-debug-in-mixed-mode.md)합니다.

-   코드 변경 프로그래밍 언어의 편집 하며 계속 하기에서 지원 되지 않는 내용을. 자세한 정보에 대 한 지원 되지 않는 코드 변경에 대 한 항목을 참조 [C#](../debugger/supported-code-changes-csharp.md), [Visual Basic](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md), 및 [c + +](../debugger/supported-code-changes-cpp.md)합니다.
  
-   시작 하는 대신에 연결 하는 프로그램에서 코드를 편집 하려고는 **디버그** 메뉴.  
  
-   Dr. Watson 덤프를 디버깅하는 동안 코드를 편집하려고 한 디버깅  
  
-   처리 되지 않은 예외가 발생 한 후 코드 및 옵션을 편집 하려는 "**처리 되지 않은 예외에 대 한 호출 스택 해제**"를 선택 하지 않았습니다.  
  
-   포함된 런타임 응용 프로그램을 디버깅하는 동안 코드를 편집하려고 한 경우
  
-   4.5.1 이전의.NET Framework 버전을 사용 하 여 관리 되는 코드를 편집 하 려 고 대상이 64 비트 응용 프로그램입니다. 편집하며 계속하기를 사용하려면 대상을 x86으로 설정해야 합니다. (*p r o j* **속성**, **컴파일** 탭 **고급 컴파일러** 설정 합니다.).  
  
-   디버깅하는 동안 수정하여 다시 로드한 어셈블리의 코드를 편집하려고 한 경우  
  
-   로드하지 않은 어셈블리의 코드를 편집하려고 한 경우  
  
-   새 버전에 빌드 오류가 있으므로 이전 버전의 응용 프로그램을 디버깅하기 시작한 경우
  
## <a name="uielement-list"></a>UI 요소 목록  
 **그래**  
 대화 상자를 종료하고 바로 전에 시도한 편집을 취소합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + 편집 하며 계속 하기 블로그 게시물](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/)  
 [지원되는 코드 변경(C++)](../debugger/supported-code-changes-cpp.md)