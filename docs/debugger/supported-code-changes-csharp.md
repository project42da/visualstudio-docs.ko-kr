---
title: "지원되는 코드 변경(C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "편집하며 계속하기[C#], 지원되는 코드 변경"
ms.assetid: c7a48ea9-5a7f-4328-a9d7-f0e76fac399d
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 지원되는 코드 변경(C#)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집하며 계속하기에서는 메서드 본문 내의 코드 변경 유형을 대부분 처리합니다.  그러나 메서드 본문 외부의 변경 내용 대부분과 메서드 본문 내의 몇 가지 변경 내용은 디버깅 중에 적용할 수 없습니다.  이러한 지원되지 않는 변경 내용을 적용하려면 디버깅을 중지하고 새로운 버전의 코드로 다시 시작해야 합니다.  
  
 디버깅 세션 중에 C\# 코드에 적용할 수 없는 변경 내용은 다음과 같습니다.  
  
-   현재 문 또는 다른 모든 활성 문에 대한 변경  
  
     활성 문에는 호출 스택의 함수에서 현재 문을 실행하기 위해 호출된 모든 문이 포함됩니다.  
  
     현재 문은 소스 창에서 노란색 배경으로 표시됩니다.  다른 활성 문은 배경이 회색으로 표시되고 읽기 전용입니다.  이러한 기본 색상은 **옵션** 대화 상자에서 변경할 수 있습니다.  
  
-   형식의 시그니처 변경  
  
-   이전에 캡처하지 않은 변수를 캡처하는 무명 메서드 추가  
  
-   특성 추가, 제거 또는 변경  
  
-   `using` 지시문 추가, 제거 또는 변경  
  
-   활성 문 주위에 `foreach`, `using` 또는 `lock` 추가  
  
## 안전하지 않은 코드  
 안전하지 않은 코드에 대한 변경에는 안전한 코드에 대한 변경과 동일한 제한 사항이 적용되고 한 가지 제한 사항이 추가로 적용됩니다. `stackalloc` 연산자가 포함된 메서드 안에 있는 안전하지 않은 코드에 대한 변경은 편집하며 계속하기에서 지원하지 않습니다.  
  
## 예외  
 편집하며 계속하기는 `catch` 및 `finally` 블록에 대한 변경을 지원합니다. 단 활성 문 주위에 `catch` 또는 `finally` 블록은 추가할 수 없습니다.  
  
## 지원되지 않는 시나리오  
 다음과 같은 디버깅 시나리오에서는 편집하며 계속하기를 사용할 수 없습니다.  
  
-   특정한 경우 LINQ 코드 디버깅.  자세한 내용은 [LINQ 디버깅](../debugger/debugging-linq.md)을 참조하세요.  
  
    -   이전에 캡처하지 않은 변수 캡처  
  
    -   쿼리 식의 형식 변경\(예: select a \=\> select new { A \= a };\)  
  
    -   활성 문을 포함하는 `where` 제거  
  
    -   활성 문을 포함하는 `let` 제거  
  
    -   활성 문을 포함하는 `join` 제거  
  
    -   활성 문을 포함하는 `orderby` 제거  
  
-   혼합 모드\(네이티브\/관리\) 디버깅  
  
-   SQL 디버깅  
  
-   Dr. Watson 덤프  디버깅  
  
-   "**처리되지 않은 예외에 대한 호출 스택 해제**" 옵션을 선택하지 않은 상태에서 처리되지 않은 예외가 발생한 후 코드 편집  
  
-   포함된 런타임 응용 프로그램 디버깅  
  
-   **디버그** 메뉴에서 **시작**을 선택하여 응용 프로그램을 실행하는 대신 **연결 대상**을 사용하여 응용 프로그램 디버깅  
  
-   최적화된 코드 디버깅  
  
-   빌드 오류가 발생하여 새 버전을 빌드하는 데 실패한 후 이전 버전의 코드 디버깅  
  
## 참고 항목  
 [편집하며 계속하기\(Visual C\#\)](../debugger/edit-and-continue-visual-csharp.md)   
 [방법: 편집하며 계속하기 사용\(C\#\)](../debugger/how-to-use-edit-and-continue-csharp.md)